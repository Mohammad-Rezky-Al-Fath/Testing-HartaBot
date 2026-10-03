# Skenario Pengujian (Test Cases)

* TC-BOT-001: Uji Inisialisasi dan Pemilihan Mode
  - Skenario: Pengguna mengirimkan perintah /start, lalu memilih mode "Pribadi".     - Ekspektasi: Bot harus membalas dengan pesan sapaan, menawarkan pilihan mode (Usaha/Pribadi), dan mengonfirmasi pilihan pengguna dengan tepat.

* TC-BOT-002: Uji Validasi Input Angka Penuh (Bug Identification)
  - Skenario: Dalam mode Pribadi (Analis Data), pengguna memasukkan transaksi          dengan nominal angka penuh tanpa singkatan (contoh: "Pendapatan: Uang          Mingguan = 500000", "Pengeluaran: Minyak motor = 30000").   
  - Ekspektasi: Bot seharusnya dapat membaca angka tersebut sebagai nominal uang       yang valid.
  - Catatan: Bot gagal membaca "30000" dan menganggapnya bukan nominal uang. Ini berpotensi menjadi Defect Log pertama.

* TC-BOT-003: Uji Validasi Input Singkatan Angka
  - Skenario: Pengguna memasukkan transaksi dengan singkatan "rb" atau "jt" (contoh: "Uang Mingguan = 500rb", "Minyak Motor = 30rb").
  - Ekspektasi: Bot harus berhasil membaca dan mengonversi singkatan tersebut          menjadi angka penuh (contoh: Rp 500.000, Rp 30.000) dan mencatatnya dengan         benar.
 
* TC-BOT-004: Uji Akurasi Kategorisasi Pengeluaran (Bug Identification)
  - Skenario: Pengguna memasukkan pengeluaran "Minyak Motor = 30rb".               - Ekspektasi: Bot harus mengategorikannya ke dalam kategori yang relevan,          seperti "Transportasi" atau "Kendaraan".
  - Catatan: Bot  mengategorikan "Minyak motor"  sebagai "Makanan & Minuman". Ini adalah kesalahan logika dan harus masuk ke Defect Log.

* TC-BOT-005: Uji Pemrosesan Transaksi Multi-Item (Bug Identification)
  - Skenario: Dalam mode UMKM, pengguna memasukkan banyak item sekaligus dalam satu pesan (contoh: "Modal: 2jt. Belanja Stok Toko: Minyak goreng = 500rb, Telur = 500rb, Shampo = 500rb").
  - Ekspektasi: Bot harus mencatat Modal (Rp 2.000.000) dan setiap rincian belanja stok toko secara terpisah dan menjumlahkannya jika perlu.
  - Catatan : Bot sepertinya kesulitan memisahkan rincian "Belanja Stok Toko"  dan hanya mencatat satu aktivitas pengeluaran Rp 500.000. Ini perlu diinvestigasi lebih lanjut sebagai Defect.  

