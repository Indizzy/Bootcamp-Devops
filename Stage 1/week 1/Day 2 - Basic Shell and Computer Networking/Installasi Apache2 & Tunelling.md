# Day 2
# Instalasi Apache2 Dan Tunneling

Step 1 - Setting IP

langkah awal mensetting IP terlebih dahulu jika menggunakan jaringan bridge, maka kita gunakan IP dalam satu network dengan cara berikut:
```
sudo nano /etc/netplan/00-installer-config.yaml

```
Akan muncul sebagai berikut lalu ubah IP nya
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-24%2009-49-56.png)


Selanjutnya untuk mengkonfirmasi customisasi IP yang sudah kalian buat tadi kalian bisa menggunakan perintah dibawah.
```
sudo netplan apply
```

 Setelah selesai men-setting IP maka kita coba gunakan perintah ping google.com untuk mengetes koneksi dan jika berhasil maka akan muncul seperti gambar berikut
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-24%2009-54-38.png)
  
  
Step 2
Apache2 Installation

Untuk mengecek IP yang sudah kita ubah tadi kita akan coba dengan remote server. Caranya masuk ke terminal lokal kalian dan masukan perintah berikut
```
ssh dizzy@192.168.100.6 
```
Untuk username dan ip silakan kalian ganti dengan username Ubuntu Server kalian sendiri, jika ssh berhasil maka akan muncul seperti gambar berikut:
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-24%2010-01-00.png)


Selanjutnya tahapan pertama yang harus kita lakukan pada saat sedang berada di dalam server yaitu melakukan update serta upgrade terlebih dahulu gunanya untuk menjaga agar system kita tetap up-to-date.

Untuk melakukan update dan upgrade, kalian bisa menggunakan perintah di bawah ini.

sudo apt update; sudo apt upgrade
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-24%2010-02-47.png)


Selanjutnya kita akan coba untuk menginstall aplikasi Apache2.

Kalian bisa gunakan perintah di bawah ini.
```
sudo apt install apache2
```
Lalu nanti akan muncul notifikasi Do you want to continue? [Y/n] kalian ketik saja Y. Jika sudah maka instalasi akan berjalan.
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2002-35-26.png)


Jika instalasi sudah selesai kita bisa cek dengan menggunakan perintah dibawah ini.
```
sudo systemctl status apache2
```
![IMG](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2002-37-07.png)

Sekarang coba buka browser kalian, lalu masukkan IP dari server kalian.
![IMG](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2002-37-59.png)


Dan instalasi Apache2 berhasil

Step 3 - LocalTunnel

Pertama-tama yang kita lakukan adalah instalalsi node.js menggunakan nvm untuk melakukan instalasi kalian dapat mengikuti langkah-langkah dibawah ini.

sudo apt install curl
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

```
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2002-41-56.png)

```
exec bash
```

```
nvm install 16
```

```
node -v
```

```
npm -v

```
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2002-48-19.png)

Selanjutnya kita akan melakukan instalasi localtunnel menggunakan npm yang sudah kita install.

```
npm install -g localtunnel
```

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2002-49-19.png)

Sekarang kita akan melakukan instalasi Apache2
sudo apt install apache2
![IMG](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2002-54-49.png)

Lalu nanti akan muncul notifikasi Do you want to continue? [Y/n] kalian ketik saja Y. Jika sudah maka instalasi akan berjalan.

Jika instalasi kalian telah selesai melakukan instalasi Apache2, Selanjutnya kita coba untuk mengakses Apache di web browser kita untuk mengecek apakah Apache kita sudah berjalan atau belum.

Coba kalian akses di web browser kalian, lalu masukkan IP dari server kalian.

Sekarang kita coba untuk menggunakan localtunel untuk aplikasi apache2 yang sudah kita install.

Untuk menjalankan localtunel kalian dapat mengikuti perintah di bawah ini.

lt --port 80

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2003-03-27.png)

keterangan : pastikan dibagian port telah sesuai dengan aplikasi kalian. Karena setiap aplikasi pasti mempunyai port yang berbeda-beda, kita ambil contoh saja dari aplikasi node.js, aplikasi node.js biasanya berjalan di atas port 3000.

Jika sudah copy url yang ada di terminal kalian.

Setelah itu coba kalian akses menggunakan Web.browser kalian.
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2003-04-29.png)


Jika sudah klik tombol Click to Continue.
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2003-04-17.png)

Selanjutnya kalian akan di arahkan ke aplikasinya
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot%20from%202022-08-25%2003-04-29.png)


tampilan pada browser hand phone
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%202/Screenshot_20220825-030904_Chrome.jpg)

