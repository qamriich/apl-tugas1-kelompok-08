
# U1. Konteks dan ASR (Architectural Significant Requirements)

## 1. Ringkasan Layanan Rusunawa Terpadu

Sistem Informasi Layanan Rusunawa Terpadu merupakan bagian dari *Academic Management* yang dirancang untuk mempermudah pengelolaan hunian mahasiswa. Sistem ini mencakup pendaftaran, informasi ketersediaan dan tarif kamar pada empat lantai, pembayaran sewa, serta pengaduan kerusakan fasilitas.

Dengan adanya sistem ini, mahasiswa dapat memperoleh informasi hunian dengan lebih mudah, sementara pengelola dapat memberikan pelayanan secara lebih teratur dan efisien.

## 2. Masalah Utama Layanan dan Bukti Empiris

### 2.1 Deskripsi Masalah Utama

Permasalahan utama pada layanan Rusunawa Putri adalah belum adanya sistem informasi resmi yang menghubungkan seluruh proses pelayanan, mulai dari pendaftaran, informasi kamar dan tarif, pembayaran, hingga pengaduan.

Berdasarkan hasil wawancara, pendaftaran masih dilakukan dengan menghubungi staf secara langsung. Staf menjelaskan biaya sewa, mengecek kamar yang tersedia, kemudian memberikan pilihan kepada calon penghuni.

Informasi pembayaran dan pengaduan juga masih disampaikan melalui grup WhatsApp atau pesan pribadi. Hal ini membuat pelayanan bergantung pada komunikasi langsung dengan staf dan belum terpusat dalam satu platform.

Oleh karena itu, diperlukan sistem informasi terpadu untuk mempermudah penyampaian informasi serta membantu pengelolaan layanan Rusunawa.

### 2.2 Bukti Empiris

Berdasarkan wawancara dengan calon penghuni, penghuni, dan staf Rusunawa Putri, ditemukan beberapa kondisi berikut:

1. **Proses Pendaftaran:** Calon penghuni menghubungi staf untuk mendapatkan informasi biaya sewa dan ketersediaan kamar sesuai lantai yang dipilih.

2. **Informasi Ketersediaan Kamar:** Staf memberikan informasi kamar kosong, kemudian calon penghuni dapat memilih kamar yang tersedia.

3. **Informasi Pembayaran:** Informasi pembayaran sewa disampaikan melalui grup WhatsApp atau pesan pribadi dari staf.

4. **Pengaduan Penghuni:** Keluhan mengenai fasilitas disampaikan melalui WhatsApp karena belum tersedia platform khusus untuk pengaduan.

5. **Pengelolaan Layanan:** Seluruh proses pelayanan masih dilakukan melalui komunikasi dengan staf dan belum terintegrasi dalam satu sistem.

Dari hasil tersebut, diperlukan platform resmi yang dapat menyatukan seluruh layanan agar informasi lebih mudah diakses oleh calon penghuni, penghuni, maupun pengelola.

## 3. Pemangku Kepentingan (Stakeholders)

Pihak-pihak yang memiliki peran dalam pengelolaan Sistem Informasi Layanan Rusunawa Terpadu adalah sebagai berikut:

| No. | Stakeholder | Peran dan Kepentingan | Kategori |
|---|---|---|---|
| 1 | Pengelola Rusunawa | Mengelola kamar, memeriksa pendaftaran, memantau pembayaran, dan menangani pengaduan. | Key Player |
| 2 | Pimpinan Kampus / Rektorat | Mengawasi operasional Rusunawa dan menerima laporan keuangan serta pelayanan. | Keep Satisfied |
| 3 | Mahasiswa Penghuni dan Calon Penghuni | Mengakses informasi kamar, tarif, pendaftaran, pembayaran, dan pengaduan. | Keep Informed |
| 4 | Tim Pengembang dan IT Support | Memelihara aplikasi, server, basis data, serta menangani kendala teknis. | Monitor |

## 4. Karakteristik Pendorong Mutu (Quality Drivers)

*Quality Drivers* merupakan aspek kualitas yang menjadi acuan dalam merancang arsitektur sistem. Terdapat tiga karakteristik utama yang perlu diperhatikan.

### 4.1 Performance Efficiency

Sistem harus mampu menjalankan pelayanan secara cepat dan efisien, mulai dari pendaftaran hingga pengelolaan pembayaran dan pengaduan. Tujuannya adalah mengurangi waktu tunggu serta mempercepat penyampaian informasi kepada pengguna.

### 4.2 Usability

Sistem perlu memiliki tampilan sederhana dan mudah dipahami oleh seluruh pengguna. Informasi kamar dan tarif pada empat lantai harus dapat ditemukan melalui *dashboard* utama dengan maksimal tiga kali klik.

### 4.3 Reliability

Sistem harus menjaga keamanan, ketepatan, dan konsistensi data. Seluruh informasi pendaftaran, kamar, pembayaran, dan pengaduan perlu tersimpan dengan baik agar dapat diakses serta ditindaklanjuti oleh pengelola.

## 5. Kebutuhan Signifikan Arsitektur (ASR)

*Architectural Significant Requirements* (ASR) merupakan kebutuhan penting yang menjadi dasar dalam menentukan rancangan arsitektur sistem. Berdasarkan karakteristik mutu yang telah ditetapkan, terdapat tiga kebutuhan utama.

### 5.1 ASR-1: Performance Efficiency (Efisiensi Proses Pelayanan Terintegrasi)

Sistem harus mampu memproses pendaftaran, pemeriksaan kamar, dan penyampaian informasi secara efisien melalui satu platform. Waktu respons untuk layanan utama ditargetkan maksimal 2 detik.

### 5.2 ASR-2: Usability (Kemudahan Akses Informasi Kamar)

Sistem harus menampilkan informasi ketersediaan dan tarif kamar pada empat lantai Rusunawa Putri melalui *dashboard* utama. Pengguna diharapkan dapat menemukan informasi tersebut dengan maksimal tiga kali klik dan waktu respons maksimal 1,5 detik.

### 5.3 ASR-3: Reliability (Keandalan Penyimpanan dan Pengelolaan Data)

Sistem harus menyimpan data pendaftaran, pembayaran, dan pengaduan beserta perubahan statusnya secara konsisten dalam basis data terelasi. Keberhasilan penyimpanan data ditargetkan minimal 99,99% untuk mengurangi risiko kehilangan atau ketidaksesuaian data.

## 6. Keterkaitan Quality Drivers dengan ASR

| No. | Quality Driver | ASR Terkait | Fokus Kebutuhan |
|---|---|---|---|
| 1 | Performance Efficiency | ASR-1 | Mempercepat pelayanan terintegrasi dengan waktu respons maksimal 2 detik. |
| 2 | Usability | ASR-2 | Memudahkan pencarian informasi kamar dan tarif dengan maksimal tiga kali klik serta respons 1,5 detik. |
| 3 | Reliability | ASR-3 | Menjaga konsistensi dan keberhasilan penyimpanan data minimal 99,99%. |
