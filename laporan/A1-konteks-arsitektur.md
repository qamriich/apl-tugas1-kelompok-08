# A1. Analisis Empat Konteks Arsitektur

<!-- Penanggung jawab: Nur Syifa Ainina -->

| Konteks | Kondisi pada Layanan Rusunawa | Pengaruh terhadap Arsitektur |
|---|---|---|
| Teknis | Layanan rusunawa mencakup pendaftaran, seleksi, penempatan kamar, dan pengaduan penghuni. Proses-proses tersebut membutuhkan pengelolaan data yang konsisten. | Arsitektur perlu mengelola data pendaftaran, hasil seleksi, penempatan kamar, dan pengaduan secara terstruktur serta menjaga konsistensi perubahan data. |
| Siklus hidup proyek | Aturan pendaftaran, kriteria seleksi, dan prosedur pengaduan dapat berubah mengikuti kebijakan pengelola. Perubahan tersebut perlu dipertimbangkan dalam pengembangan dan pemeliharaan sistem. | Arsitektur sebaiknya memisahkan aturan bisnis dari bagian sistem lainnya agar perubahan kebijakan lebih mudah dilakukan dan diuji. |
| Bisnis | Layanan bertujuan mendukung proses pendaftaran, seleksi calon penghuni, penempatan kamar, dan penanganan pengaduan. Pengelola membutuhkan informasi yang dapat membantu pelaksanaan proses tersebut. | Arsitektur perlu mendukung alur proses yang jelas, penyajian status pendaftaran dan penempatan kamar, serta pencatatan pengaduan dan tindak lanjutnya. |
| Profesional | Mahasiswa sebagai pengguna dan staf atau pengelola sebagai pihak yang menangani layanan memiliki kebutuhan dan kewenangan berbeda. Informasi penghuni juga perlu ditangani secara bertanggung jawab. | Arsitektur perlu membedakan hak akses berdasarkan peran, membatasi akses terhadap data yang relevan, serta menyediakan dokumentasi proses dan keputusan arsitektur. |
