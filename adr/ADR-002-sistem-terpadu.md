# ADR-[002]: [Sistem Terpadu]

# ADR-002: Pengembangan Sistem Terpadu dengan Fitur Pelacakan Pengaduan

- **Status:** Diusulkan
- **Tanggal:** 29-10-2026
- **Pengambil keputusan:** Nurul Qamri Ramadhina

## Context
Berdasarkan wawancara dengan mahasiswa dan staf, layanan rusunawa saat ini belum memiliki platform *online* khusus dan hanya mengandalkan grup WhatsApp[cite: 4]. Hal ini mengakibatkan informasi ketersediaan kamar, perbedaan tarif sewa di empat lantai, dan pengumuman sering terlewat[cite: 4]. Selain itu, laporan kerusakan fasilitas sering tenggelam di *chat* sehingga mahasiswa tidak bisa memantau status penanganannya[cite: 4].

## Decision
Kami memutuskan untuk membangun Sistem Informasi Berbasis Web Terpadu yang mengintegrasikan modul pendaftaran, ketersediaan kamar, tarif sewa, pembayaran, dan layanan pengaduan dalam satu pintu[cite: 4]. Khusus untuk pengaduan, arsitektur akan dilengkapi mekanisme *state management* (status tiket keluhan: *Diterima*, *Diproses*, *Selesai*) agar mahasiswa dapat memantau perkembangan laporannya secara transparan[cite: 4].

## Consequences
- **Positif:** Mengatasi masalah informasi yang berserakan di WhatsApp[cite: 4]. Mahasiswa mendapatkan kepastian status penanganan fasilitas dan transparansi biaya sebelum memilih kamar[cite: 4]. Staf dapat mengelola data secara lebih efisien[cite: 4].
- **Negatif:** Integrasi seluruh layanan ini membutuhkan perancangan skema *database* relasional yang cukup kompleks di awal untuk mengikat relasi antara entitas Mahasiswa, Kamar, Pembayaran, dan Tiket Pengaduan.