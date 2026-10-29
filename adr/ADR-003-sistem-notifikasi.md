# ADR-[003]: [Sistem Notifikasi]

# ADR-003: Penerapan Layanan Notifikasi Terpusat (Email Gateway / Push Notification)

- **Status:** Diusulkan
- **Tanggal:** 29-10-2026
- **Pengambil keputusan:** Nurul Qamri Ramadhina

## Context
Berdasarkan wawancara, kendala yang sering terjadi adalah mahasiswa terlewat pengumuman penting dan kesulitan membedakan informasi baru dan lama karena hanya mengandalkan grup WhatsApp[cite: 4]. Jika sistem baru nanti membutuhkan konfirmasi ketersediaan kamar, penagihan tarif sewa berdasarkan lantai, dan pembaruan status pengaduan[cite: 4], maka sistem tidak bisa hanya menunggu mahasiswa untuk melakukan pengecekan secara manual (*pull*).

## Decision
Kami akan mengintegrasikan layanan Notifikasi Terpusat (*Email Gateway* seperti Mailgun/SMTP atau *Push Notification* Firebase) ke dalam arsitektur sistem. Setiap ada perubahan status krusial (contoh: tiket pengaduan direspons, atau tagihan sewa lantai diterbitkan), sistem akan secara otomatis mendorong (*push*) notifikasi langsung ke email atau perangkat pengguna.

## Consequences
- **Positif:** Mengurangi risiko mahasiswa terlewat pengumuman penting dan meningkatkan kepuasan pengguna terhadap respons layanan pengaduan[cite: 4].
- **Negatif:** Membutuhkan integrasi pihak ketiga (API eksternal) yang berpotensi menambah biaya operasional jika jumlah email/notifikasi melebihi batas layanan gratis (*free tier*).