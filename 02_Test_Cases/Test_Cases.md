# Skenario Pengujian (Test Cases)

* **TC-BOT-001: Uji Inisialisasi dan Pemilihan Mode**
  * **Skenario:** Pengguna mengirimkan perintah `/start`, lalu memilih mode "Pribadi".
  * **Ekspektasi:** Bot harus membalas dengan pesan sapaan, menawarkan pilihan mode (Usaha/Pribadi), dan mengonfirmasi pilihan pengguna dengan tepat.

* **TC-BOT-002: Uji Validasi Input Angka Penuh (Bug Identification)**
  * **Skenario:** Dalam mode Pribadi, pengguna memasukkan transaksi: "Pendapatan: Uang Mingguan = 500000", "Pengeluaran: Minyak motor = 30000".
  * **Ekspektasi:** Bot seharusnya dapat membaca angka tersebut sebagai nominal uang yang valid.
  * **Catatan:** Bot gagal membaca "30000" dan menganggapnya bukan nominal uang. (Defect Log)

* **TC-BOT-003: Uji Validasi Input Singkatan Angka**
  * **Skenario:** Pengguna memasukkan transaksi dengan singkatan "rb" atau "jt" (contoh: "Uang Mingguan = 500rb", "Minyak Motor = 30rb").
  * **Ekspektasi:** Bot harus berhasil membaca dan mengonversi singkatan tersebut menjadi angka penuh (contoh: Rp 500.000, Rp 30.000).

* **TC-BOT-004: Uji Akurasi Kategorisasi Pengeluaran (Bug Identification)**
  * **Skenario:** Pengguna memasukkan pengeluaran "Minyak Motor = 30rb".
  * **Ekspektasi:** Bot harus mengategorikannya ke kategori yang relevan, seperti "Transportasi" atau "Kendaraan".
  * **Catatan:** Bot salah mengategorikan sebagai "Makanan & Minuman". (Defect Log)

* **TC-BOT-005: Uji Pemrosesan Transaksi Multi-Item (Bug Identification)**
  * **Skenario:** Dalam mode UMKM, pengguna memasukkan item: "Modal: 2jt. Belanja Stok Toko: Minyak goreng = 500rb, Telur = 500rb, Shampo = 500rb".
  * **Ekspektasi:** Bot harus mencatat Modal (Rp 2.000.000) dan setiap rincian belanja stok secara terpisah.
