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

![image](https://user-images.githubusercontent.com/18206510/189105593-a90d6f21-6a65-48a4-8526-cf6f59c2cdd6.png)


kemudian kita diminta untuk memasukkan password yang kuat


![image](https://user-images.githubusercontent.com/18206510/189110422-26f67b30-0d98-4823-a7aa-e511eee0b5db.png)


untuk mengecek versi mysql yang kita gunakan bisa dengan perintah

``` mysql --version```

![image](https://user-images.githubusercontent.com/18206510/189110821-fca2de11-2725-4d4a-a42b-f38e3509a079.png)


kemudian untuk masuk ke mysql kita gunakan perintah

```mysql -u root -p```

karena tadi kita sudah memasukkan password untuk mysql kita


![image](https://user-images.githubusercontent.com/18206510/189112199-4d34d8cb-8c2b-4356-bc31-9423ab7920e8.png)


# membuat user dan database baru

sekarang kita coba membuat user dan databe baru, untuk membuat user masukan perintah berikut :


``` CREATE USER 'nama user bebas'@'%' IDENTIFIED BY 'password bebas';```


![image](https://user-images.githubusercontent.com/18206510/189121126-d5d889a6-0da8-4b76-82b9-1d249b94c66a.png)


lalu kita berikan hak akses istimewa kepada user kita tadi dengan perintah 


```GRANT ALL PRIVILEGES ON *.* TO 'user_database'@'localhost';```


![image](https://user-images.githubusercontent.com/18206510/189121904-119cab4d-af77-408a-9709-bc88b28bc274.png)


lalu kita coba masuk dengan user yang baru saja kita buat dengan perintah 

``` mysql -u (nama user tadi) -p ```


![image](https://user-images.githubusercontent.com/18206510/189122619-efa6327e-df3d-44f1-af87-678ec00aca09.png)



kemudian untuk mengecek user kita bisa lakukan dengan perintah 


```SELECT user, host FROM mysql.user;```


![image](https://user-images.githubusercontent.com/18206510/189123112-d9f8e808-ae90-4087-957e-1d6ac697c546.png)


# kemudian sekarang kita akan membuat databasenya

untuk membuat database masukan perintah


```CREATE DATABASE (nama database);```


![image](https://user-images.githubusercontent.com/18206510/189123753-fa85177a-26f6-4e69-a2e9-7d01bbcc8e5b.png)


kemudian untuk melihat database dapat mebnggunakan perintah 


```SHOW databases;```


untuk memakai database bisa gunakan perintah


```USE (nama database);```


untuk melihat tables pada database gunakan perintah 


```SHOW tables;```



![image](https://user-images.githubusercontent.com/18206510/189124827-caf90732-5a49-4eed-90f4-d54efbfc9365.png)


kemudian sekarang kita akan mencoba melakukan pergantian Bind address agar database dapat diakses oleh client 

pertama masukkan perintah 

```cd /etc/mysql/mysql.conf.d```

lalu masuk ke file mysqld.cnf dengan perintah 


```sudo nano mysqld.cnf```



![image](https://user-images.githubusercontent.com/18206510/189127137-233343a1-b3ec-4c9f-b7c2-42fd858f0a6e.png)


pada bagian Bind address dan mysql-bind-address kita ganti menjadi ```0.0.0.0```


jika sudah lalu simpan


kemudian kita restart mysql kita agar semua perubahan dapat berjalan, masukan perintah


```sudo systemctl restart mysql.service```


![image](https://user-images.githubusercontent.com/18206510/189127973-68c6e160-21ee-4735-a453-30f8d980bb5c.png)


kemudian karena di sini kita akan mendeploy aplikasi backend maka kita siapkan dulu environtmentnya, di sini saya akan menaruh app backend di tempat yang 


sama dengan frontend sebelumnya, pertama saya buat direktori dulu lalu masuk ke direktorinya dan melakukan cloning app backend



![image](https://user-images.githubusercontent.com/18206510/189130147-cd58c0f1-5f89-460c-b389-0aab9ea8167f.png)


masukan perintah 


```git clone https://github.com/dumbwaysdev/dumbflix-backend```


![image](https://user-images.githubusercontent.com/18206510/189131083-9d778364-a655-45bd-9068-3a387b92133b.png)


kemudian kita install NVM (node version manager) dan NPM (node package manager) 


jika belum menginstall NVM maka masukan perintah 

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```

lalu masukkan 


```nvm install 14(versi yg ingin kita gunakan)```


di sini karena saya sudah menginstall nvm terlebih dahulu maka saya tinggal memasukkan perintah nvm install (versi)


kemudian untuk melakukan installasi npm kita gunakan perintah

```sudo apt install npm```


![image](https://user-images.githubusercontent.com/18206510/189133011-4ecf5dbe-4db1-4627-90a3-6ae63d418749.png)


di sini karena saya juga sudah menginstall npm maka muncul keterangan seperti diatas


kemudian untuk mengecek versi dari nvm dan npm bisa gunakan perintah

```node -v``` untuk nvm 

```npm -p``` untuk npm 


![image](https://user-images.githubusercontent.com/18206510/189134518-5aa5e2ce-6ee6-4cf7-923e-4a3bcf70d177.png)


# Remote database oleh client





































