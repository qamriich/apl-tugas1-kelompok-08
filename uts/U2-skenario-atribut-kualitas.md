
# U2. Skenario Atribut Kualitas

## 1. Pendahuluan

Skenario atribut kualitas merupakan gambaran kebutuhan kualitas yang harus dipenuhi oleh Sistem Informasi Layanan Rusunawa Terpadu. Skenario ini disusun berdasarkan tiga Architectural Significant Requirements (ASR) pada U1, yaitu performa dalam menangani pendaftaran serentak, kebergunaan informasi kamar dan tarif, serta keandalan pencatatan data pengaduan.

Tujuan penyusunan skenario ini adalah memastikan sistem mampu memberikan layanan yang cepat, mudah digunakan, dan dapat diandalkan dalam mengelola operasional rusunawa.

## 2. Skenario Atribut Kualitas

### 2.1 ASR-1: Performance Efficiency (Performa)

- **Sumber Stimulus:** Mahasiswa calon penghuni rusunawa.
- **Stimulus:** Sebanyak 500 calon penghuni mengakses halaman pendaftaran secara bersamaan pada saat pembukaan kuota kamar.
- **Lingkungan:** Sistem berada dalam kondisi beban puncak (peak traffic load).
- **Artefak:** Modul pendaftaran, server aplikasi, dan Message Queue.
- **Respons:** Sistem menerima permintaan melalui Message Queue, mengatur antrean, dan memproses data secara terstruktur.
- **Ukuran Respons:** Sistem mampu menangani 500 pengguna secara bersamaan dengan waktu tanggap kurang dari 2 detik tanpa downtime selama proses pendaftaran.

### 2.2 ASR-2: Usability (Kebergunaan)

- **Sumber Stimulus:** Mahasiswa calon penghuni dan penghuni rusunawa.
- **Stimulus:** Pengguna mencari informasi kamar kosong, lokasi kamar berdasarkan 4 lantai, serta rincian tarif sewa.
- **Lingkungan:** Sistem berada dalam kondisi operasional normal dan diakses melalui komputer maupun smartphone.
- **Artefak:** Dashboard utama dan katalog informasi kamar rusunawa.
- **Respons:** Sistem menampilkan informasi ketersediaan kamar, pembagian kamar berdasarkan 4 lantai, serta rincian tarif sewa secara visual.
- **Ukuran Respons:** Informasi ditampilkan dengan waktu tanggap kurang dari 1,5 detik dan dapat ditemukan dalam maksimal 3 kali klik.

### 2.3 ASR-3: Reliability (Keandalan)

- **Sumber Stimulus:** Mahasiswa penghuni rusunawa.
- **Stimulus:** Penghuni mengirimkan tiket pengaduan terkait kerusakan fasilitas.
- **Lingkungan:** Sistem sedang beroperasi dan digunakan oleh beberapa penghuni secara bersamaan.
- **Artefak:** Modul pengaduan, pengelolaan tiket, dan basis data terelasi.
- **Respons:** Sistem memvalidasi data pengaduan, menyimpan laporan secara otomatis, serta memberikan nomor tiket dan status laporan kepada penghuni.
- **Ukuran Respons:** Sistem mencapai keandalan pencatatan sebesar 99,99% dan memastikan data pengaduan yang berhasil dikirim tidak hilang.

## 3. Kesimpulan

Sistem Informasi Layanan Rusunawa Terpadu harus mampu menangani beban pendaftaran serentak, menyediakan informasi kamar dan tarif yang mudah diakses, serta menjamin keandalan penyimpanan data pengaduan. Penerapan atribut Performance Efficiency, Usability, dan Reliability diharapkan dapat meningkatkan kualitas layanan rusunawa.
