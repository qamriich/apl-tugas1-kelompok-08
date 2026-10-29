
# B2. Atribut Kualitas yang Terukur

<!-- Penanggung jawab: Nurul Qamri Ramadhina -->

Berdasarkan Kebutuhan Signifikan Arsitektur (ASR) dan temuan wawancara *stakeholder*, berikut adalah skenario atribut kualitas yang diukur untuk memastikan arsitektur memenuhi kebutuhan layanan rusunawa:

**1. Skenario Performa (Menangani Lonjakan Akses)**
* **Sumber Stimulus:** Ratusan mahasiswa secara serentak.
* **Stimulus:** Mengakses halaman pendaftaran kamar dan memilih kamar pada hari pembukaan.
* **Artefak:** Sistem pendaftaran (Web Server dan *Database*).
* **Lingkungan:** Kondisi beban puncak (*peak load*).
* **Respons:** Sistem memproses permintaan melalui *queue system* tanpa mengalami *crash* atau *race condition*.
* **Pengukuran Respons:** Waktu henti (*downtime*) sistem adalah 0 menit, dan 100% permintaan pendaftaran berhasil dimasukkan ke dalam antrean.

**2. Skenario Kebergunaan (Pencarian Informasi)**
* **Sumber Stimulus:** Mahasiswa (calon penghuni).
* **Stimulus:** Mencari informasi ketersediaan kamar dan rincian tarif sewa untuk keempat lantai yang berbeda.
* **Artefak:** Antarmuka Pengguna (UI) platform *web*.
* **Lingkungan:** Operasi normal.
* **Respons:** Sistem menampilkan informasi kamar dan harga per lantai secara terpusat di halaman utama.
* **Pengukuran Respons:** Pengguna dapat menemukan rincian tarif dan kamar kosong dalam waktu kurang dari 3 kali klik sejak membuka situs.

**3. Skenario Keandalan (Pelacakan Pengaduan)**
* **Sumber Stimulus:** Mahasiswa (penghuni).
* **Stimulus:** Mengirimkan formulir pengaduan kerusakan fasilitas rusunawa.
* **Artefak:** Modul Pengaduan dan *Database*.
* **Lingkungan:** Operasi normal.
* **Respons:** Sistem menyimpan data laporan, mengubah status menjadi "Diterima", dan mengirimkan notifikasi.
* **Pengukuran Respons:** 99,99% data laporan pengaduan tersimpan dengan aman tanpa ada data yang hilang (seperti yang sering terjadi di grup WhatsApp).
