# A2. Stakeholder dan Peta Power/Interest

<!-- Penanggung jawab: Selma Lia Putri -->

Dokumen ini memetakan para pemangku kepentingan (*stakeholders*) dalam pengembangan Sistem Informasi Layanan Rusunawa Terpadu berdasarkan tingkat pengaruh (*Power*) dan kepentingan (*Interest*) mereka terhadap sistem.

### 1. Analisis Stakeholder

| Stakeholder | Peran / Deskripsi | Power | Interest | Kategori | Strategi Pengelolaan |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Pengelola Rusunawa** | Mengelola pendaftaran, kamar, tarif, dan pemeliharaan fasilitas. | Tinggi | Tinggi | *Key Players* | **Manage Closely** (Dilibatkan dalam setiap keputusan fitur) |
| **Pimpinan Kampus / Rektorat** | Mengawasi operasional aset dan menerima laporan kinerja. | Tinggi | Rendah | *Meet Satisfied* | **Keep Satisfied** (Diberi laporan berkala) |
| **Mahasiswa (Calon & Penghuni)** | Pengguna akhir yang mendaftar, melihat tarif, dan mengajukan pengaduan. | Rendah | Tinggi | *Show Consideration* | **Keep Informed** (Diberi informasi transparan dan antarmuka ramah pengguna) |
| **Tim Pengembang (IT / Dev)** | Membangun dan memelihara sistem sesuai rancangan arsitektur. | Rendah | Rendah | *Minimal Effort* | **Monitor** (Dipantau melalui dokumentasi arsitektur yang jelas) |

### 2. Matriks Power / Interest

* **High Power, High Interest (Manage Closely):** Pengelola Rusunawa.
* **High Power, Low Interest (Keep Satisfied):** Pimpinan Kampus / Rektorat.
* **Low Power, High Interest (Keep Informed):** Mahasiswa Penghuni & Calon Penghuni.
* **Low Power, Low Interest (Monitor):** Tim Pengembang / Staf Administrasi Umum.

*(Berikut adalah diagram peta power/interest stakeholder)*
![Peta Power Interest](../diagram/A2-peta-power-interest.png)
