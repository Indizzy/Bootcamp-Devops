# Apa itu Database?

  Database atau basis data adalah kumpulan data yang dikelola sedemikian rupa berdasarkan ketentuan tertentu yang saling berhubungan sehingga mudah dalam pengelolaannya. Melalui pengelolaan tersebut pengguna dapat memperoleh kemudahan dalam mencari informasi, menyimpan informasi dan membuang informasi.

Adapun pengertian lain dari database adalah sistem yang berfungsi sebagai mengumpulkan file, tabel, atau arsip yang terhubung dan disimpan dalam berbagai media elektronik.

Di sini kita buat dulu server untuk database nya, caranya masih sama hanya saja di sini resource name kita beri nama awan-database 


![image](https://user-images.githubusercontent.com/18206510/189077326-2472e99d-5b9b-48af-b0d1-4901526a38bd.png)



![image](https://user-images.githubusercontent.com/18206510/189077622-09ba59a1-1c37-4122-8530-df8143a86db5.png)


kita tunggu hingga prosesnya selesai


![image](https://user-images.githubusercontent.com/18206510/189078480-9709c6c9-5043-4638-9af1-72de15b535fe.png)



kemudian seperti biasa masuk ke server databasenya lalu lakukan update dan upgrade



![image](https://user-images.githubusercontent.com/18206510/189081666-b709f70e-d053-45e4-ac4b-b0ef0d26468c.png)


# Installasi mysql

# Apa itu mysql?

MySQL adalah sebuah database management system (manajemen basis data) menggunakan perintah dasar SQL (Structured Query Language) yang cukup terkenal.

Database management system (DBMS) MySQL multi pengguna dan multi alur ini sudah dipakai lebih dari 6 juta pengguna di seluruh dunia.


MySQL adalah DBMS yang open source dengan dua bentuk lisensi, yaitu Free Software (perangkat lunak bebas) dan Shareware (perangkat lunak berpemilik yang penggunaannya terbatas).

Jadi, MySQL adalah database server yang gratis dengan lisensi GNU General Public License (GPL) sehingga dapat Anda pakai untuk keperluan pribadi atau komersil tanpa harus membayar lisensi yang ada.

cara menginstall mysql ke dalam server database yang sudah kita buat, masukan perintah 

```
sudo apt install mysql-server
```

![image](https://user-images.githubusercontent.com/18206510/189091744-0d22386b-54c2-4fa6-882e-b5a85e1b8d14.png)


Ini akan menginstal MySQL, tetapi tidak akan meminta Anda untuk menetapkan kata sandi atau membuat perubahan konfigurasi lain. Karena ini membuat instalasi

MySQL Anda menjadi tidak aman

Untuk instalasi baru MySQL, Anda akan menjalankan skrip keamanan DBMS yang disertakan. Skrip ini mengubah beberapa opsi asali yang kurang aman untuk hal-

hal seperti log masuk root jarak jauh dan pengguna sampel.

masukkan perintah 

```
sudo mysql_secure_installation
```

![image](https://user-images.githubusercontent.com/18206510/189094205-7c1df06e-cb17-4f51-96ce-f5b447dde728.png)
















