# BAB IV. PENUTUP

<!-- Penanggung jawab: Nurul Qamri Ramadhina -->

## 4.1 Kesimpulan
Berdasarkan perumusan Kebutuhan Signifikan Arsitektur (ASR) dan temuan lapangan [5], rancangan arsitektur Sistem Informasi Layanan Rusunawa ini telah disusun untuk menyelesaikan berbagai kendala operasional. Keputusan arsitektur (ADR) yang diambil meliputi penerapan pola arsitektur *Model-View-Controller* (MVC) untuk memisahkan logika pemrosesan data dan antarmuka [3], serta pemanfaatan sistem antrean (*queue system*) terpusat guna mencegah kelebihan beban *server* saat terjadi lonjakan pendaftar [2].

Sistem ini dirancang sebagai platform terpadu yang memusatkan informasi ketersediaan kamar, perbedaan tarif lantai, dan pelacakan status pengaduan fasilitas [5]. Pendekatan arsitektural ini secara signifikan akan meningkatkan atribut kualitas kebergunaan (*usability*) dan keandalan (*reliability*) sistem [1]. Meskipun terdapat kompromi (*trade-off*) berupa peningkatan kompleksitas infrastruktur dan implementasi kode [1], keputusan ini sepadan dengan stabilitas dan transparansi yang akan dicapai oleh instansi [4].

## 4.2 Saran dan Tindak Lanjut
Untuk memastikan rancangan arsitektur ini dapat diimplementasikan dengan baik pada tahap pengembangan (*coding*), disarankan beberapa hal berikut:
1. **Perancangan Skema Basis Data:** Relasi entitas antara Mahasiswa, Kamar, Tarif, dan Tiket Pengaduan harus didesain dengan ketat sejak awal untuk menjaga integritas data [3].
2. **Pengujian Beban (Stress Testing):** Tim pengembang perlu melakukan simulasi *stress testing* pada *message broker* untuk memastikan sistem antrean mampu memproses *request* tanpa kehilangan data (*data loss*) di bawah beban puncak [4].
3. **Pemantauan Layanan Pihak Ketiga:** Jika mengintegrasikan *Email Gateway* atau *Push Notification*, pemantauan kuota API harus dilakukan secara berkala agar notifikasi ke mahasiswa tidak terputus [2].