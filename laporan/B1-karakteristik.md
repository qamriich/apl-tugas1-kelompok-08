# B1. Identifikasi dan Klasifikasi Karakteristik

<!-- Penanggung jawab: Selma lia putri -->
# B1. Pandangan Arsitektur (Architectural Views Overview)

Bagian ini memberikan gambaran umum mengenai tiga struktur arsitektur yang digunakan untuk mendokumentasikan Sistem Informasi Layanan Rusunawa Terpadu. Pendekatan ini merujuk pada standar perancangan arsitektur perangkat lunak (Bass et al.) guna memberikan pemahaman menyeluruh dari berbagai sudut pandang *stakeholder*.

### 1. Struktur Modul (Module View)
* **Fokus:** Pengelompokan struktur kode, komponen internal, dan dependensi antar-modul secara logis.
* **Tujuan:** Menjadi panduan bagi tim pengembang (*programmers*) dalam membagi tugas pembuatan modul (Pendaftaran, Kamar & Tarif, Pembayaran, Pengaduan, dan Notifikasi).

### 2. Struktur Komponen dan Konektor (C&C View)
* **Fokus:** Perilaku elemen-elemen sistem saat aplikasi sedang berjalan (*runtime execution*) beserta alur komunikasi data antar-komponen.
* **Tujuan:** Memastikan sistem mampu menangani lonjakan akses melalui *Message Broker* dan *Background Worker* secara aman.

### 3. Struktur Alokasi (Allocation / Deployment View)
* **Fokus:** Pemetaan elemen perangkat lunak ke dalam infrastruktur fisik, *server* (*VPS & Dedicated Database*), serta jaringan komunikasi (*Internet HTTPS & Private Network*).
* **Tujuan:** Menjadi acuan bagi tim DevOps / administrator *server* dalam melakukan pemeliharaan infrastruktur dan *deployment* sistem.

