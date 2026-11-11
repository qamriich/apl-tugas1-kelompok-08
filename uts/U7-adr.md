# U7. Architectural Decision Records (ADR)

Dokumen *Architectural Decision Record* (ADR) ini mencatat keputusan-keputusan arsitektur penting yang diambil dalam perancangan Sistem Informasi Layanan Rusunawa Terpadu. Setiap ADR memuat konteks permasalahan, keputusan yang ditetapkan, serta konsekuensi teknis yang ditimbulkan.

---

## ADR-001: Penerapan Message Queue (RabbitMQ) untuk Handling Concurrency Pendaftaran Rusunawa

* **Title:** ADR-001: Implementasi Message Queueing berbasis RabbitMQ untuk Menangani Beban Concurrency Pendaftaran Serentak
* **Status:** Accepted
* **Context:**  
  Proses pendaftaran kamar Rusunawa Putri sebelumnya belum memiliki platform terintegrasi dan berpotensi mengalami kelebihan beban puncak (*traffic spike*) saat pembukaan kuota diakses serentak oleh 500 calon penghuni (ASR-1). Jika pemrosesan dilakukan secara langsung (*synchronous write*), sistem berisiko mengalami *HTTP 504 Gateway Timeout* dan *race condition* stok kamar.
* **Decision:**  
  Mengimplementasikan **RabbitMQ** sebagai *Message Broker* dengan pola *Event-Driven Architecture* (EDA). Seluruh permintaan pendaftaran dari *frontend* akan ditampung terlebih dahulu ke dalam antrean asinkron (*message queue*) sebelum diproses bertahap oleh *background worker* ke dalam basis data.
* **Consequences:**  
  * **Positif:** Sistem terbebas dari risiko *crash* saat pendaftaran serentak, waktu tanggap *frontend* tetap konsisten < 2,0 detik, dan mampu menampung 500+ pengguna serentak dengan *downtime* 0%.
  * **Negatif:** Terdapat jeda waktu pemrosesan akhir (*eventual consistency delay*) beberapa detik sebelum pengguna mendapatkan notifikasi konfirmasi pendaftaran resmi.

---

## ADR-002: Separasi Read-Model (Redis Caching) dan Relational Database Transaction (ACID) untuk Layanan Rusunawa

* **Title:** ADR-002: Penggunaan Redis Caching untuk Katalog Kamar & Transaksi RDBMS (ACID) untuk Tiket Pengaduan Kerusakan
* **Status:** Accepted
* **Context:**  
  Sistem membutuhkan performa pencarian informasi kamar 4 lantai dan tarif yang cepat (< 1,5 detik dan <= 3 klik) (ASR-2). Di sisi lain, sistem harus menjamin keandalan pencatatan tiket pengaduan kerusakan fasilitas agar tidak ada laporan yang hilang (*reliability* 99,99%) (ASR-3)[cite: 5].
* **Decision:**  
  1. Menggunakan **Redis In-Memory Caching** untuk melayani *query* pembacaan katalog kamar 4 lantai dan tarif sewa secara terpisah (*read-model*).
  2. Menggunakan **Relational Database Management System (RDBMS)** dengan dukungan transaksi ACID untuk modul pencatatan tiket pengaduan dan transaksi pembayaran.
* **Consequences:**  
  * **Positif:** Halaman katalog dan tarif dapat diakses dengan cepat (< 1,5 detik) tanpa membebani basis data utama. Data tiket pengaduan dan pembayaran tersimpan secara permanen dan terstruktur tanpa risiko kehilangan data (99,99% *persistence*)[cite: 5].
  * **Negatif:** Memerlukan mekanisme pembersihan *cache* (*cache invalidation logic*) pada Redis setiap kali terjadi pembaruan status ketersediaan kamar oleh pengelola.
