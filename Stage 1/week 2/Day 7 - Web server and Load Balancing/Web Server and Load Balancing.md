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

untuk mengaktifkan nginx bisa kita gunakan perintah 

```sudo systemctl enable nginx```

![image](https://user-images.githubusercontent.com/18206510/187916803-388dcb33-4a68-4012-9223-858be3381d79.png)

sedangkan untuk mematikan sistem dari nginx kita bisa gunakan perintah 

```sudo systemctl disable nginx```

![image](https://user-images.githubusercontent.com/18206510/187917520-5bed80e8-a01a-440c-8427-3dda0c2886f0.png)

jika ingin menghentikan sistem dari nginx kita bisa menggunakan perintah

```sudo systemctl stop nginx```

kemudian status nginx akan berubah menjadi inactive

![image](https://user-images.githubusercontent.com/18206510/187918154-50e9c58b-b297-4e2a-94a8-c56b788704ec.png)

untuk melihat nginx telah terinstall kita juga bisa mengakses ip dari server kita maka akan terlihat seperti berikut

![image](https://user-images.githubusercontent.com/18206510/187919014-321e7528-4a3f-4606-91fa-2da4e75b2f5e.png)


# 3. Reverse Proxy
# 3.1 Apa itu Reverse Proxy?

Reverse proxy adalah konfigurasi standar yang digunakan untuk mengubah jalur traffic, misalkan aplikasi menggunakan port 3000 tetapi agar dapat di akses melalui port 80 maka harus menggunakan reverse proxy.

Berikut adalah konfigurasi dari revese proxy.

server { 
    server_name domain.com; 
    
   location / { 
             proxy_pass http://127.0.0.1:3000;
    }
}




# 3.2 Kenapa Harus Reverse Proxy?

Untuk mengamankan aplikasi yang berjalan pada server maka kita perlu untuk melakukan reverse proxy, supaya pengguna tidak dapat mengakses aplikasi kita secara langsung.

# 3.3 Membuat Konfigurasi Revese Proxy

Untuk membuat reverse proxy dapat mengikuti langkah-langkah berikut :

Pertama-tama masuk ke folder nginx setelah itu buat suatu directory baru telebih dahulu.

```cd /etc/nginx```

lalu buat direktori baru terserah kalian


![image](https://user-images.githubusercontent.com/18206510/187965820-a5e82d28-27fd-4f8c-9aab-a52b3b0eb35a.png)



kemudian ,masuk pada direktori tersebut lalu buat file dengan ekstensi .conf 


![image](https://user-images.githubusercontent.com/18206510/187966097-8892e85a-d62b-438b-b7aa-77326925f11b.png)


lalu masukan konfigurasi reverse proxy di dalam file tersebut


![image](https://user-images.githubusercontent.com/18206510/187966925-42ff2e58-f471-45a7-9ee8-d560b408460f.png)


pastikan port sesuai dengan yang digunakan oleh aplikasi


lalu keluar dari direktori tersebut dan masuk ke file nginx.conf

![image](https://user-images.githubusercontent.com/18206510/187967115-2d570f4d-afad-45bb-983d-216932217b54.png)


selanjutnya scroll ke bawah, di bagian include masukan lokasi dari direktori yang berisi konfigurasi tadi

![image](https://user-images.githubusercontent.com/18206510/187967420-c28ed0ce-d53d-465a-96db-98f6c3a8fc77.png)

tanda bintang di sini menandakan bahwa nginx akan membaca semua yg ada pada direktori tersebut

jika sudah maka pastikan konfigurasi tadi sudah benar dengan perintah 

```sudo nginx -t```

![image](https://user-images.githubusercontent.com/18206510/187967519-5cc216eb-5413-4e20-bb05-445f5f9f426b.png)

lalu kemudian kita tinggal melakukan restart/reload pada nginx kita dengan perintah 

```sudo systemctl restart nginx```

![image](https://user-images.githubusercontent.com/18206510/187967688-1ff8cfa5-2bca-4fc1-b573-6bbb5a13bde9.png)


selanjutnya kita akan membuat virtual host di local server kita, untuk membuat virtual host kita harus masuk ke file /etc/hosts dengan perintah 


```sudo nano /etc/hosts```

selanjutnya masukan ip server kita dan nama domain yang kita buat

![image](https://user-images.githubusercontent.com/18206510/187968601-7229fd0a-9753-4795-96cb-15dc711718ca.png)


jika sudah coba buka browser untuk akses domain kalian

![image](https://user-images.githubusercontent.com/18206510/187969334-a915cd62-f437-4e33-9193-4f1cbda52b35.png)

di sini terdapat tanda 502 bad getaway karena aplikasi kita belum berjalan, sekarang kita coba jalankan aplikasi yang pernah kita pakai sebelumnya

masuk ke direktori aplikasi tersebut lalu install npm untuk menjalankan module dari node.js dengan perintah

```sudo apt install npm```

![image](https://user-images.githubusercontent.com/18206510/187951339-96edc009-297e-4a58-947d-c9b41d4656f5.png)


lalu tunggu hingga prosesnya selesai kemudian start npm dengan perintah

```npm start```


![image](https://user-images.githubusercontent.com/18206510/187951493-47c171ab-6b11-4d3f-baea-13075f83efa2.png)


![image](https://user-images.githubusercontent.com/18206510/187952916-a4bad326-4d7c-4e1d-b83d-5907d2312234.png)



selanjutnya coba refresh browser kita

 ,









































































