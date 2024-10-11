Program ini adalah sistem manajemen sesi foto untuk Pipin Self Photo Studio, di mana manajer studio bisa melakukan berbagai operasi terkait pengelolaan sesi foto pelanggan. Berikut penjelasan dan cara kerja program secara keseluruhan:


#Struktur Program:

1. Class PBOProject1:
Ini adalah main class yang bertanggung jawab menjalankan program. Di sini, pengguna diberikan pilihan melalui menu untuk melakukan berbagai tindakan, seperti menambah sesi foto, menampilkan semua sesi, mengubah status pembayaran, atau menghapus sesi foto. Program terus berulang sampai pengguna memilih opsi Keluar.

2. Class manajer:
Class ini mengimplementasikan interface CRUD dan bertanggung jawab untuk semua operasi terkait sesi foto.
Operasi yang bisa dilakukan di sini antara lain:
Tambah sesi foto: Manajer bisa menambahkan sesi foto baru untuk pelanggan dengan nama, durasi sesi, dan menentukan apakah pelanggan adalah VIP atau regular.
Tampilkan semua sesi: Menampilkan daftar semua sesi yang telah diinput, lengkap dengan informasi pelanggan dan status pembayaran.
Ubah status pembayaran: Manajer bisa mengubah status pembayaran pelanggan dari "Belum Bayar" menjadi "Sudah Bayar".
Hapus sesi foto: Manajer bisa menghapus sesi foto tertentu berdasarkan nama pelanggan.

3. Interface CRUD:
Interface ini mendefinisikan metode tambahSesiFoto(), tampilkanSemuaSesi(), ubahStatusPembayaran(), dan hapusSesiFoto(), yang kemudian diimplementasikan oleh class manajer.

4. Class session (Abstrak):
Class ini adalah class abstrak yang berfungsi sebagai parent dari customer.
session memiliki properti dasar seperti namaCustomer, durasi, dan harga. Class ini juga mendefinisikan metode abstrak cetakInvoice(), yang harus diimplementasikan oleh subclass seperti customer.

5. Class customer:
Class ini adalah turunan dari class session dan memiliki tambahan properti statusPembayaran. Metode cetakInvoice() di sini mencetak detail sesi foto beserta status pembayarannya.
Class customer juga menyediakan getter dan setter untuk mengakses atau mengubah status pembayaran.

6. Class VipCustomer:
Ini adalah subclass dari customer yang merepresentasikan pelanggan VIP. Selain properti dari customer, VipCustomer juga memiliki properti diskon.
Dalam metode cetakInvoice(), pelanggan VIP mendapatkan harga diskon dan ini ditampilkan dalam invoice.

7. Class RegularCustomer:
Ini juga subclass dari customer, namun untuk pelanggan regular tanpa diskon. Dalam metode cetakInvoice(), detail sesi foto dicetak dengan harga penuh tanpa diskon.


#Cara Kerja Program:

1. Menjalankan Program:
Saat program dijalankan, pengguna diberikan menu pilihan untuk mengelola sesi foto di studio. Manajer bisa menambah, melihat, mengubah status pembayaran, atau menghapus sesi foto.

2. Menambah Sesi Foto:
Manajer memasukkan nama pelanggan, durasi sesi (15, 30, 60, atau 90 menit), dan apakah pelanggan adalah VIP atau regular.
Jika pelanggan VIP, harga akan dikenakan diskon 10%. Jika regular, harga dihitung normal berdasarkan durasi sesi.

3. Menampilkan Semua Sesi Foto:
Semua sesi yang telah dimasukkan akan ditampilkan, termasuk informasi pelanggan, durasi sesi, total harga (termasuk diskon jika ada), dan status pembayaran.

4. Mengubah Status Pembayaran:
Manajer bisa mencari sesi berdasarkan nama pelanggan dan mengubah status pembayaran dari "Belum Bayar" menjadi "Sudah Bayar".

5. Menghapus Sesi Foto:
Manajer dapat mencari sesi berdasarkan nama pelanggan dan menghapus sesi tersebut dari daftar.

Bedanya sama program di ProjectPBO1 ada dibagian customer. Program ProjectPBO2 memiliki kategori customer, yaitu Customer VIP dan Regular sebagai implementasi dari materi Inheritance. Selebihnya masih sama seperti ProjectPBO1.
