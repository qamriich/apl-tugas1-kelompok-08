
# U4. Pola Arsitektur (Architectural Patterns)

Pola arsitektur mendefinisikan struktur tingkat tinggi dari arsitektur perangkat lunak yang menyediakan skema organisasi untuk komponen-komponen sistem.

## 1. Pola Arsitektur 1: Event-Driven Architecture (EDA)

- **Kategori Pola:** Integration & Event-Based Pattern.

- **Alasan Penerapan pada Rusunawa:**
Sistem membutuhkan pemisahan (decoupling) antara proses penerimaan formulir pendaftaran di frontend dengan pemrosesan basis data di backend. Pola ini diterapkan untuk mengatasi masalah HTTP 504 Gateway Timeout akibat lonjakan 500 pendaftaran secara bersamaan.

- **Kelebihan pada Layanan Rusunawa:**
  - **Skalabilitas Tinggi:** Mampu menangani lonjakan permintaan pendaftaran secara bersamaan melalui Message Queue tanpa membebani web server secara langsung.
  - **Keterikatan Longgar (Loose Coupling):** Frontend dan background worker dapat beroperasi secara independen sehingga proses penerimaan pendaftaran tidak harus menunggu seluruh pemrosesan basis data selesai.

- **Kekurangan pada Layanan Rusunawa:**
  - **Kompleksitas Debugging:** Penelusuran kesalahan (error tracing) pada alur transaksi yang melibatkan beberapa komponen lebih sulit dilakukan dibandingkan sistem sinkron.

## 2. Pola Arsitektur 2: Layered Architecture (N-Tier Architecture)

- **Kategori Pola:** Structural / Partitioning Pattern.

- **Alasan Penerapan pada Rusunawa:**
Pola ini digunakan pada struktur internal modul aplikasi seperti autentikasi (Auth), pengelolaan kamar, dan pengaduan untuk memisahkan tanggung jawab kode program secara terstruktur berdasarkan lapisan.

- **Kelebihan pada Layanan Rusunawa:**
  - **Kode Terstruktur dan Mudah Dirawat (Maintainable):** Memisahkan tanggung jawab aplikasi menjadi:
    1. Presentation Layer: Menampilkan antarmuka kepada pengguna.
    2. Business Logic Layer: Mengelola proses dan aturan bisnis sistem.
    3. Data Access Layer: Mengelola akses dan komunikasi dengan basis data.
  - **Memudahkan Pembagian Kerja:** Pengembang antarmuka dan pengembang basis data dapat bekerja pada lapisan yang berbeda sehingga pekerjaan lebih terorganisasi.

- **Kekurangan pada Layanan Rusunawa:**
  - **Sinkronisasi Antar-Lapisan:** Setiap permintaan harus melewati lapisan secara berurutan (Presentation → Logic → Data), sehingga dapat menambah waktu pemrosesan apabila tidak dioptimalkan.

## 3. Perbedaan Gaya Arsitektur (Architectural Style) dan Pola Arsitektur (Architectural Pattern)

### 3.1 Gaya Arsitektur (Architectural Style)

Gaya arsitektur merupakan pendekatan umum atau gambaran makro tentang bagaimana seluruh komponen sistem diorganisasikan, dibatasi, dan saling berkomunikasi. Gaya arsitektur menetapkan aturan dasar struktur sistem secara keseluruhan.

Contoh:
- Microservices Style.
- Monolithic Style.
- Client-Server Style.

### 3.2 Pola Arsitektur (Architectural Pattern)

Pola arsitektur merupakan solusi yang telah teruji untuk menyelesaikan masalah tertentu dalam perancangan arsitektur perangkat lunak. Pola arsitektur memiliki cakupan yang lebih spesifik dan teknis dibandingkan gaya arsitektur.

Contoh:
- Event-Driven Pattern.
- CQRS Pattern.
- Model-View-Controller (MVC) Pattern.

### 3.3 Kesimpulan Perbedaan

Gaya arsitektur memberikan gambaran umum mengenai bagaimana sistem dibangun secara keseluruhan, sedangkan pola arsitektur memberikan solusi yang lebih spesifik untuk mengatasi permasalahan dalam pengorganisasian komponen sistem.

## 4. Kesimpulan

Berdasarkan pembahasan tersebut, Sistem Informasi Layanan Rusunawa Terpadu menerapkan Event-Driven Architecture untuk mendukung proses pendaftaran yang memiliki beban akses tinggi dan Layered Architecture untuk memisahkan tanggung jawab setiap bagian aplikasi.

Kedua pola tersebut saling mendukung dalam meningkatkan skalabilitas, keteraturan kode program, kemudahan pemeliharaan, dan keandalan sistem. Dengan demikian, arsitektur yang diterapkan diharapkan mampu memenuhi kebutuhan kualitas yang telah dijelaskan pada U1 dan U2.
