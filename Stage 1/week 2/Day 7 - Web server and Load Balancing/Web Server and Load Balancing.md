# 1. Web Server

# 1.1 Apa itu Web Server?

Web Server adalah sebuah software yang memberikan layanan berupa data. Berfungsi untuk menerima permintaan HTTP atau HTTPS dari client atau di kenal dengan web browser (chrome atau firefox). Kemudian web server akan mengirimkan respon atas permintaan tersebut dalam bentuk halaman web.

# 1.2 Mengapa Memplejari Web Server?

Karena Web server memiliki peran penting dalam mengendalikan proses kerja dari sebuah website. Tanpa adanya web server, kamu tidak bisa melakukan permintaan data apapun pada suatu halaman atau page di web browser.


# 1.3 Bagaimana Cara Kerja Web Server?

jadi computer kita sebagai client akan melakukan request data yang berada pada server database melalui sebuah web server kemudian web server akan mengembalikan data tersebut dalam bentuk halaman website pada komputer kita sebagai client.

# 1.4 Fungsi Web Server

Menyediakan data berdasarkan request atau permintaan yang masuk agar dapat menjamin keamanan sistem yang berjalan dengan lancar.

Melakukan pemeriksaan terhadap sistem security yang berasal dari permintaan HTTP berdasarkan request client atau web browser.

# 1.5 Jenis-Jenis Web Server

 Nginx
 Apache
 Lightpd
 Lightspeed

# 1.6 Instalasi Nginx dan Service Management

Sekarang kita akan mencoba untuk melakukan instalasi salah satu web server yang terkenal yaitu adalah Nginx.
pertama-tama lakukan update dan upgrade pada server kita agar segala sesuatunya tetap terbaru dengan perintah 

```sudo apt update; sudo apt upgrade```

kemudian kita install nginx-nya dengan perintah 

```sudo apt install nginx```

jika keluar notifikasi 'Do you want to continue?' maka ketik saja Y lalu tunggu hingga prosesnya selesai


Jika kalian sudah menjalankan beberapa perintah diatas kalian sudah berhasil untuk melakukan installasi Nginx. Kalian bisa check menggunakan perintah di bawah ini.

```nginx -v```

![image](https://user-images.githubusercontent.com/18206510/187915937-b680852a-62f9-4c48-aa6b-f585adabb2c9.png)

kemudian untuk bisa melihat status nginx bisa menggunakan perintah

```sudo systemctl status nginx```


![image](https://user-images.githubusercontent.com/18206510/187916440-3dd75535-9845-4900-b5d0-d391df5e1bf9.png)





















