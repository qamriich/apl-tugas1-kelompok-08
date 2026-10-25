# A3. Batasan Sistem

<!-- Penanggung jawab: [nama] -->

Layanan rusunawa yang sedang kami analisis meliputi pendaftaran, proses seleksi calon penghuni, penempatan kamar, dan penanganan pengaduan penghuni. Batasan-batasan berikut adalah rancangan awal yang harus kami konfirmasi lewat data publik, kebijakan pengelola, atau observasi langsung terhadap proses layanan.

| Kategori | Batasan | Dampak terhadap Arsitektur |
|---|---|---|
| Teknologi | Sistem harus memperhatikan akses lewat perangkat yang sering dipakai mahasiswa, seperti ponsel dan komputer. | Arsitektur antarmuka harus mendukung desain responsif supaya informasi dan fungsi penting dapat diakses di semua ukuran layar. |
| Teknologi | Bila sistem harus terhubung ke sistem kampus yang sudah ada, integrasi harus mengikuti mekanisme akses dan pertukaran data yang diizinkan. | Arsitektur harus memisahkan komponen integrasi dari logika utama layanan agar ketergantungan pada sistem eksternal dapat dikelola. |
| Bisnis | Proses pendaftaran dan seleksi harus mematuhi persyaratan serta kriteria yang ditetapkan oleh pengelola rusunawa. | Aturan pendaftaran dan seleksi harus dirancang agar bisa disesuaikan tanpa perlu mengubah seluruh komponen sistem ketika kebijakan berubah. |
| Bisnis | Penempatan kamar harus mempertimbangkan kapasitas kamar dan keputusan penempatan yang ditetapkan pengelola. | Arsitektur harus menjaga konsistensi data ketersediaan kamar dan mencegah penempatan melebihi kapasitas yang ditentukan. |
| Operasional | Pemrosesan pendaftaran, keputusan seleksi, penempatan kamar, dan tindak lanjut pengaduan memerlukan peran pengelola yang berwenang. | Sistem harus membedakan hak akses berdasarkan peran dan mencatat perubahan penting agar proses dapat ditelusuri. |
| Operasional | Pelaksanaan layanan digital dapat tergantung pada ketersediaan jaringan dan infrastruktur server. | Arsitektur harus mempertimbangkan pencatatan kesalahan, pemantauan layanan, serta prosedur pencadangan dan pemulihan data sesuai kemampuan infrastruktur yang tersedia. |
