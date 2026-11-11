# U3. Taktik

## 1. ASR-1: Performance Efficiency (Performa)

**Taktik: Message Queue dan Load Balancing**

- **Cara Kerja:**

  Sistem menggunakan Message Queue untuk menampung permintaan pendaftaran dari 500 calon penghuni secara bersamaan. Setiap permintaan dimasukkan ke dalam antrean agar diproses secara teratur oleh server aplikasi. Load Balancing membagi beban permintaan ke beberapa server agar tidak terjadi penumpukan pada satu server.

- **Tujuan:**

  Mengurangi beban server dan menjaga waktu respons tetap kurang dari 2 detik saat terjadi lonjakan akses pendaftaran.

- **Harga yang Dibayar (Trade-off):**

  Penerapan kedua teknologi ini membutuhkan sumber daya server tambahan dan konfigurasi yang lebih kompleks. Selain itu, penggunaan antrean dapat menimbulkan sedikit keterlambatan dalam pemrosesan permintaan.

## 2. ASR-2: Usability (Kebergunaan)

**Taktik: Penyederhanaan Antarmuka dan Navigasi**

- **Cara Kerja:**

  Sistem menyediakan dashboard utama yang menampilkan informasi ketersediaan kamar, pembagian kamar berdasarkan empat lantai, serta rincian tarif sewa. Menu disusun secara sederhana agar pengguna dapat menemukan informasi dengan maksimal tiga kali klik.

- **Tujuan:**

  Memudahkan calon penghuni dan penghuni dalam memperoleh informasi kamar tanpa harus menghubungi staf Rusunawa secara langsung.

- **Harga yang Dibayar (Trade-off):**

  Penyederhanaan tampilan membutuhkan perencanaan dan pengujian agar informasi tetap mudah dipahami. Selain itu, banyaknya informasi dalam satu dashboard dapat membuat tampilan lebih padat, terutama pada smartphone.

## 3. ASR-3: Reliability (Keandalan)

**Taktik: Database Transaction dan Backup Data**

- **Cara Kerja:**

  Sistem menggunakan transaksi basis data untuk memastikan setiap pengaduan tersimpan secara utuh dan konsisten. Setelah laporan berhasil disimpan, sistem memberikan nomor tiket dan status pengaduan kepada penghuni. Backup data dilakukan secara berkala untuk mengantisipasi kehilangan data akibat gangguan sistem.

- **Tujuan:**

  Menjaga konsistensi data pengaduan serta memastikan laporan dapat diakses dan ditindaklanjuti oleh penghuni maupun pengelola Rusunawa.

- **Harga yang Dibayar (Trade-off):**

  Penerapan transaksi basis data dan backup membutuhkan kapasitas penyimpanan tambahan serta waktu pemrosesan. Selain itu, pencadangan data perlu dikelola secara rutin agar data dapat dipulihkan ketika terjadi gangguan.

## 4. Ringkasan Penerapan Taktik

| No. | ASR | Quality Attribute | Taktik yang Digunakan | Tujuan Utama |
|---|---|---|---|---|
| 1 | ASR-1 | Performance Efficiency | Message Queue dan Load Balancing | Menangani 500 pengguna secara bersamaan dengan waktu respons kurang dari 2 detik. |
| 2 | ASR-2 | Usability | Penyederhanaan Antarmuka dan Navigasi | Memudahkan pencarian informasi kamar dan tarif maksimal tiga kali klik. |
| 3 | ASR-3 | Reliability | Database Transaction dan Backup Data | Menjaga konsistensi serta mencegah kehilangan data pengaduan. |
