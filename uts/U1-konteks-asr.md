# U1. Konteks dan ASR (Architectural Significant Requirements)

## 1. Ringkasan Layanan Rusunawa Terpadu
Sistem Informasi Layanan Rusunawa Terpadu merupakan subsistem Academic Management yang dirancang untuk mengelola seluruh operasional hunian mahasiswa, mencakup pendaftaran calon penghuni, visualisasi katalog dan tarif kamar 4 lantai, pembayaran sewa, serta manajemen tiket pengaduan kerusakan fasilitas.

## 2. Masalah Utama Layanan & Bukti Empiris
* **Deskripsi Masalah Utama:** 
  Sistem mengalami kegagalan total (*crash / HTTP 504 Gateway Timeout*) dan *race condition* data saat pembukaan serentak kuota pendaftaran kamar rusunawa pada jam beban puncak (*peak traffic load*). Hal ini menyebabkan calon penghuni gagal menyelesaikan proses formulir dan status kamar menjadi tidak valid.
  
* **Bukti Empiris (Wawancara Responden R1 - Calon Penghuni):**
  > *"Saat jam 08.00 WITA pendaftaran dibuka, situs langsung lurus tidak bisa dibuka dan keluar tulisan Error 504 Gateway Timeout. Pas halaman berhasil di-refresh 10 menit kemudian, kuota kamar sudah dinyatakan habis padahal formulir saya belum sempat terkirim."*  
  *(Responden R1: Mahasiswa Calon Penghuni Rusunawa)*

## 3. Pemangku Kepentingan (Stakeholders)
1. **Pengelola Rusunawa (Key Player):** Mengontrol alokasi kamar, verifikasi pendaftaran, dan menerima laporan operasional.
2. **Pimpinan Kampus / Rektorat (Keep Satisfied):** Mengawasi pemanfaatan aset rusunawa dan laporan keuangan sewa berkala.
3. **Mahasiswa Penghuni & Calon Penghuni (Keep Informed):** Mengakses informasi kamar, mendaftar serentak, dan melaporkan kerusakan fasilitas.
4. **Tim Pengembang & IT Support (Monitor):** Memelihara ketersediaan server, infrastruktur basis data, dan kode aplikasi.

## 4. Karakteristik Pendorong Mutu (Quality Drivers)
1. **Performance Efficiency (Capacity & Time Behaviour):** Menangani lonjakan *traffic concurrency* pendaftaran serentak tanpa menghentikan layanan.
2. **Usability (Operability):** Menyajikan transparansi status ketersediaan kamar dan tarif sewa dengan navigasi sederhana (< 3 kali klik).
3. **Reliability (Fault Tolerance & Data Persistence):** Memastikan seluruh data pendaftaran dan tiket pengaduan tersimpan secara konsisten tanpa ada data yang hilang.

## 5. Kebutuhan Signifikan Arsitektur (ASR)
* **ASR-1 (Performa Concurrency):** Saat 500 calon penghuni mengakses pendaftaran secara serentak (beban puncak), sistem harus menampung antrean permintaan melalui *Message Queue* dengan waktu tanggap < 2 detik dan *zero downtime*.
* **ASR-2 (Kebergunaan Informasi):** Saat pengguna mencari kamar kosong dan rincian tarif 4 lantai, sistem harus menampilkan data secara visual di *dashboard* utama dalam waktu tanggap < 1,5 detik.
* **ASR-3 (Keandalan Pencatatan):** Saat penghuni mengajukan tiket keluhan fasilitas, sistem harus menyimpan status laporan secara otomatis ke basis data terelasi dengan keandalan pencatatan 99,99%.
