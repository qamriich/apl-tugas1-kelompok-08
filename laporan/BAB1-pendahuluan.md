# BAB I. PENDAHULUAN

<!-- Penanggung jawab: Nurul Qamri Ramadhina -->

## 1.1 Latar Belakang
Layanan rumah susun mahasiswa (Rusunawa) merupakan fasilitas penting untuk mendukung kelancaran kegiatan mahasiswa [3]. Namun, berdasarkan hasil survei dan wawancara dengan mahasiswa serta staf pengelola, pengelolaan layanan saat ini masih belum optimal karena belum memiliki sistem informasi terpadu [5]. Komunikasi informasi pendaftaran, ketersediaan kamar, hingga pengaduan kerusakan fasilitas saat ini sangat bergantung pada grup WhatsApp [5]. 

Kondisi ini menimbulkan berbagai kendala, seperti calon penghuni yang kesulitan mencari informasi tarif sewa yang berbeda di keempat lantai, pengumuman penting yang sering terlewat, hingga laporan keluhan fasilitas yang tenggelam di ruang obrolan (*chat*) dan tidak bisa dilacak status penanganannya [5]. Oleh karena itu, diperlukan perancangan arsitektur perangkat lunak yang andal untuk membangun Sistem Informasi Layanan Rusunawa Terpadu berbasis web guna menyelesaikan masalah operasional tersebut secara sistematis [4].

## 1.2 Tujuan Dokumen
Tujuan dari penyusunan dokumen arsitektur ini adalah:
1. Mendokumentasikan Kebutuhan Signifikan Arsitektur (ASR) yang digali langsung dari keluhan *stakeholder* di lapangan [1].
2. Merumuskan Keputusan Arsitektur (ADR) yang logis, seperti penerapan sistem antrean (*queue system*) untuk mengatasi lonjakan akses (*traffic spike*) [2].
3. Memetakan rancangan sistem ke dalam tiga struktur arsitektur utama (Modul, *Component & Connector*, dan Alokasi) sebagai pedoman teknis bagi pengembang [1].
4. Menetapkan target metrik atribut kualitas (performa, kebergunaan, dan keandalan) beserta analisis kompromi (*trade-off*) dari sistem yang dirancang [1].

## 1.3 Ruang Lingkup Sistem
Ruang lingkup arsitektur perangkat lunak yang dirancang berfokus pada pemenuhan atribut kualitas utama melalui fitur berikut:
1. **Pendaftaran dan Penempatan Kamar:** Sistem antrean pendaftaran mahasiswa dan pemilihan kamar serentak [2].
2. **Ketersediaan dan Transparansi Tarif:** Pengelolaan ketersediaan kamar secara *real-time* dengan rincian tarif 4 lantai yang berbeda [5].
3. **Manajemen Pengaduan (Ticketing):** Fasilitas pelaporan kerusakan dengan pelacakan status penanganan (*state management*) untuk menjamin keandalan layanan [3].
4. **Pembayaran dan Notifikasi:** Pencatatan pembayaran dan pengiriman pembaruan otomatis tanpa bergantung pada pihak ketiga yang tidak terstruktur [4].
