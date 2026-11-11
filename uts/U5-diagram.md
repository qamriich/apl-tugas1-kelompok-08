
# (U5) DESAIN ARSITEKTUR 

### 4.1 Struktur Pandangan Arsitektur (Architectural Views)
Perancangan arsitektur ini divisualisasikan melalui tiga pandangan utama:
1. **Module View:** Membagi elemen logis kode menjadi modul Pendaftaran, Kamar, Pembayaran, dan Pengaduan.
2. **Component & Connector (C&C) View:** Menunjukkan interaksi komponen saat *runtime*, khususnya peran *Message Broker* dalam menangani beban pendaftaran **[4], [5]**.
3. **Allocation View:** Memetakan komponen perangkat lunak ke infrastruktur fisik server.

---

### 4.2 Diagram Konteks (C4 System Context - Level 1)
Diagram ini memetakan interaksi antara sistem Rusunawa dengan pengguna dan sistem eksternal **[5]**.

```plantuml
@startuml
!include [https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml](https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml)
Person(mahasiswa, "Mahasiswa", "Mendaftar, melihat tarif, dan mengadu.")
Person(pengelola, "Pengelola", "Memverifikasi data dan keluhan.")
System(rusunawaSystem, "Sistem Layanan Rusunawa Terpadu", "Pusat layanan akademik rusunawa.")
System_Ext(paymentGateway, "Sistem Keuangan UMI", "Verifikasi transaksi.")
Rel(mahasiswa, rusunawaSystem, "Akses HTTPS")
Rel(pengelola, rusunawaSystem, "Akses HTTPS")
Rel(rusunawaSystem, paymentGateway, "REST API")
@enduml
