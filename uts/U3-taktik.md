
# BAB III. TAKTIK DAN POLA ARSITEKTUR (U3 & U4)

## Bagian U3: Taktik Arsitektur (Architectural Tactics)

Taktik arsitektur merupakan keputusan desain berskala kecil yang digunakan untuk mengontrol dan memenuhi atribut kualitas spesifik pada Sistem Informasi Layanan Rusunawa Terpadu. Berikut adalah penjelasannya berdasarkan tiga ASR utama.

---

### 1. Taktik Skenario 1: Performance Efficiency (Performa Concurrency Pendaftaran)

- **Nama Taktik:** **Manage Demand (Message Queueing / Asynchronous Processing)**
- **Atribut Kualitas:** Performance Efficiency (Capacity & Time Behaviour)

- **Cara Kerja:**

  Ketika 500 calon penghuni mengakses pendaftaran secara serentak pada jam pembukaan kuota, *Web Frontend* tidak langsung mengeksekusi penulisan (*write*) ke basis data utama. Permintaan diteruskan sebagai *event message* ke dalam antrean **RabbitMQ Message Queue**.

  Komponen *Registration Worker Service* kemudian memproses antrean pendaftaran satu per satu secara asinkron di belakang layar (*background process*).

- **Harga yang Dibayar (Trade-off / Cost):**

  - **Kompleksitas Infrastruktur:** Memerlukan pemeliharaan server tambahan untuk *Message Broker* (RabbitMQ) dan *worker daemon process*.

  - **Jeda Konfirmasi (Eventual Consistency Delay):** Pengguna tidak menerima status konfirmasi penetapan kamar secara instan, melainkan harus menunggu beberapa detik hingga *worker* selesai memproses antrean.

---

### 2. Taktik Skenario 2: Usability (Kemudahan Akses Katalog & Tarif 4 Lantai)

- **Nama Taktik:** **Support User Initiative & Maintain Data Copies (Read-Model Caching)**
- **Atribut Kualitas:** Usability (Operability & Learnability)

- **Cara Kerja:**

  Untuk memastikan halaman utama menampilkan ketersediaan kamar empat lantai dan rincian tarif dalam waktu kurang dari 1,5 detik serta maksimal tiga kali klik, sistem menyalin data ketersediaan kamar dari basis data ke **Redis In-Memory Cache**.

  Saat mahasiswa mengakses *dashboard*, *Web Frontend* langsung membaca data dari Redis tanpa perlu melakukan *query join* yang berat ke basis data utama.

- **Harga yang Dibayar (Trade-off / Cost):**

  - **Overhead Invalidation Cache:** Memerlukan penerapan logika pembersihan *cache* (*cache invalidation logic*) yang tepat. Setiap kali pengelola mengubah data kamar atau kuota terisi, sistem harus langsung memperbarui *cache* Redis agar informasi yang ditampilkan tetap terbaru dan tidak menggunakan data lama (*stale data*).

---

### 3. Taktik Skenario 3: Reliability (Keandalan Pencatatan Tiket Pengaduan Kerusakan)

- **Nama Taktik:** **State Persistence & Transaction Control (ACID Database Transaction)**
- **Atribut Kualitas:** Reliability (Fault Tolerance & Data Persistence)

- **Cara Kerja:**

  Saat penghuni mengirimkan tiket pengaduan kerusakan fasilitas, seperti keran bocor atau gangguan listrik, sistem membungkus proses penyimpanannya menggunakan mekanisme transaksi **MySQL RDBMS (ACID Compliance)**.

  Setiap tiket yang masuk secara otomatis diberikan nomor tiket unik, status awal (`Diterima`), serta mencatat *timestamp* transaksional untuk menjaga keandalan data sebesar 99,99% dan mengurangi risiko kehilangan laporan.

- **Harga yang Dibayar (Trade-off / Cost):**

  - **Penurunan Write Throughput Maksimum:** Penggunaan kuncian transaksi (*database locking*) dapat sedikit menurunkan kecepatan penulisan apabila terjadi ribuan penulisan tiket secara bersamaan dalam satu milidetik.
