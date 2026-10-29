# B5. Analisis Trade-off

<!-- Penanggung jawab: Nurul Qamri Ramadhina -->

Setiap keputusan arsitektur yang dirancang untuk menyelesaikan masalah layanan rusunawa memiliki kompromi (*trade-off*). Berikut adalah analisis *trade-off* dari keputusan yang diambil:

**1. Trade-off Sistem Antrean (ADR-001)**
* **Fokus Peningkatan:** Performa dan Keandalan (*Reliability*). Sistem tidak akan mati (*down*) saat ratusan mahasiswa mendaftar kamar bersamaan.
* **Fokus yang Dikorbankan:** Latensi dan Kebergunaan (*Usability*). Mahasiswa mengorbankan kecepatan mendapatkan hasil. Mereka tidak langsung mendapat konfirmasi sukses saat mengeklik tombol daftar, melainkan harus menunggu *worker* memproses antreannya terlebih dahulu. Kompleksitas infrastruktur juga meningkat karena perlu *setup message broker*.

**2. Trade-off Pelacakan Pengaduan Terpadu (ADR-002)**
* **Fokus Peningkatan:** Transparansi dan Kebergunaan. Mahasiswa bisa melihat progres keluhannya secara *real-time* dan tahu tarif tiap lantai dengan jelas, tidak lagi bergantung pada jawaban manual staf di grup WhatsApp.
* **Fokus yang Dikorbankan:** Biaya dan Waktu Pengembangan (*Time-to-market*). Menggabungkan modul pendaftaran, pembayaran, dan sistem tiket *tracking* pengaduan dalam satu *database* relasional membutuhkan perancangan skema yang lebih rumit dan waktu *coding* yang lebih lama dibandingkan membuat sistem terpisah.

**3. Trade-off Layanan Notifikasi Terpusat (ADR-003)**
* **Fokus Peningkatan:** Kebergunaan. Mahasiswa tidak akan terlewat pengumuman penting karena langsung mendapat *push notification* atau email.
* **Fokus yang Dikorbankan:** Ketergantungan Eksternal (*Modifiability*) dan Biaya. Arsitektur menjadi sangat bergantung pada API pihak ketiga (*Email Gateway*/Firebase). Jika layanan pihak ketiga tersebut bermasalah atau *limit* gratisannya habis, fitur notifikasi akan mati dan pengelola harus mengeluarkan biaya langganan bulanan.