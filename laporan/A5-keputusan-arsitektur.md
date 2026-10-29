# A5. Keputusan Arsitektur dan ADR

<!-- Penanggung jawab: Nurul Qamri Ramadhina -->

Bagian ini mendokumentasikan keputusan arsitektur utama yang diambil untuk memenuhi Kebutuhan Signifikan Arsitektur (ASR) pada layanan rusunawa berdasarkan kendala sistem dan temuan wawancara.

| ID | Judul Keputusan | Ringkasan Keputusan | Status | Tautan ADR |
|---|---|---|---|---|
| ADR-001 | Penerapan Sistem Antrean (*Queue System*) | Menerapkan mekanisme antrean latar belakang (*background job*) untuk mencegah *server down* dan *race condition* saat lonjakan pendaftaran kamar. | Diusulkan | [Baca detail](../adr/ADR-001-sistem-antrean.md) |
| ADR-002 | Platform Terpadu & Pelacakan Pengaduan | Membangun sistem web terintegrasi untuk menggantikan komunikasi via WhatsApp, dilengkapi pelacakan status pengaduan dan transparansi ketersediaan kamar. | Diusulkan | [Baca detail](../adr/ADR-002-sistem-terpadu.md) |
| ADR-003 | Penerapan Layanan Notifikasi Terpusat | Mengintegrasikan *Email Gateway* atau *Push Notification* untuk mengatasi masalah terlewatnya pengumuman di grup WA dan memberikan *update* otomatis. | Diusulkan | [Baca detail](../adr/ADR-003-sistem-notifikasi.md) |