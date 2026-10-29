# A4. Kebutuhan Signifikan (ASR)

<!-- Penanggung jawab: [nama] -->


Untuk memenuhi Kebutuhan Signifikan Arsitektur (ASR) yang telah ditetapkan, rancangan arsitektur menerapkan taktik arsitektur spesifik (*Architectural Tactics*) berdasarkan atribut kualitas utama:

### 1. Taktik Performa (Performance Tactics)
* **Manage Demand (Queueing / Message Broker):** Menerapkan antrean terpusat untuk menampung *HTTP request* pendaftaran kamar saat jam pembukaan serentak, sehingga *web server* tidak mengalami kelebihan beban (*traffic spike*).
* **Defer Response:** Memproses transaksi pendaftaran secara asinkron di belakang layar (*background worker*) agar pengguna tidak mengalami *timeout*.

### 2. Taktik Kebergunaan (Usability Tactics)
* **Support User Initiative (Clear Navigation & Dashboard):** Menyajikan data ketersediaan kamar dan rincian tarif 4 lantai secara terpusat pada *dashboard* utama dengan navigasi maksimal 3 kali klik.
* **Explicit State Visibility:** Menampilkan status terkini dari setiap tahapan pendaftaran dan tiket pengaduan secara langsung di antarmuka pengguna.

### 3. Taktik Keandalan (Reliability / Availability Tactics)
* **State Management & Data Persistence:** Mengubah status laporan pengaduan kerusakan secara otomatis (*Diterima -> Diproses -> Selesai*) dan menyimpannya ke basis data terelasi untuk mencegah data hilang.
* **Automated Notification Logging:** Mengintegrasikan *gateway* notifikasi otomatis untuk mencatat dan mengonfirmasi resi pembayaran serta pembaruan status laporan secara konsisten.

