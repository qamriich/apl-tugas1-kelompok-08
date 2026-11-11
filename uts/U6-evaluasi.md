# U6. Evaluasi Arsitektur

Dokumen ini memuat evaluasi menyeluruh terhadap rancangan arsitektur Sistem Informasi Layanan Rusunawa Terpadu. Evaluasi dilakukan melalui tiga metode utama: Pohon Utilitas Mini, Matriks Evaluasi Trade-off Berbobot, dan Analisis ATAM (*Architecture Trade-off Analysis Method*), serta diakhiri dengan penjelasan keteratasan masalah utama.

---

## 1. Pohon Utilitas Mini (Mini Utility Tree)

Pohon Utilitas Mini digunakan untuk memetakan dan memprioritaskan kebutuhan kualitas arsitektur sistem berdasarkan tiga *Architectural Significant Requirements* (ASR) pada U1 dan U2. Setiap skenario dinilai berdasarkan dua dimensi prioritas:
- **Importance to Business (H/M/L):** Tingkat kepentingan skenario bagi operasional bisnis Rusunawa.
- **Difficulty to Implement (H/M/L):** Tingkat kesulitan teknis dalam mengimplementasikan solusi arsitektur.

```text
Utilitas Layanan Rusunawa Terpadu
  ├── 1. Performance Efficiency
  │      └── Concurrency & Time Behaviour
  │             └── [S1] Menangani 500 pendaftaran serentak (< 2 detik, zero downtime)
  │                    └── Prioritas: (High, High)
  │
  ├── 2. Usability
  │      └── Operability & Learnability
  │             └── [S2] Akses katalog kamar 4 lantai & tarif (< 1,5 detik, <= 3 klik)
  │                    └── Prioritas: (Medium, High)
  │
  └── 3. Reliability
         └── Fault Tolerance & Data Persistence
                └── [S3] Pencatatan tiket pengaduan kerusakan (keandalan 99,99%)
                       └── Prioritas: (High, Medium)
