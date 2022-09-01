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


![image](https://user-images.githubusercontent.com/18206510/187979818-c38d50a2-31c2-4d4e-8904-5a982f789298.png)



kemudian ,masuk pada direktori tersebut lalu buat file dengan ekstensi .conf 


![image](https://user-images.githubusercontent.com/18206510/187980326-a7ecbb72-172e-4a1e-b0da-803df81a04f5.png)

lalu masukan konfigurasi reverse proxy di dalam file tersebut


![image](https://user-images.githubusercontent.com/18206510/187981879-346a7f14-d8fc-4a45-a3ff-650d4e4dff1d.png)


pastikan port sesuai dengan yang digunakan oleh aplikasi


lalu keluar dari direktori tersebut dan masuk ke file nginx.conf

![image](https://user-images.githubusercontent.com/18206510/187982007-838dc9eb-801f-4e36-82b5-7167293d26c9.png)


selanjutnya scroll ke bawah, di bagian include masukan lokasi dari direktori yang berisi konfigurasi tadi

![image](https://user-images.githubusercontent.com/18206510/187982230-3015b712-2e50-4f98-9272-8b6b01b14bbe.png)

tanda bintang di sini menandakan bahwa nginx akan membaca semua yg ada pada direktori tersebut

jika sudah maka pastikan konfigurasi tadi sudah benar dengan perintah 

```sudo nginx -t```

![image](https://user-images.githubusercontent.com/18206510/187967519-5cc216eb-5413-4e20-bb05-445f5f9f426b.png)

lalu kemudian kita tinggal melakukan restart/reload pada nginx kita dengan perintah 

```sudo systemctl restart nginx```

![image](https://user-images.githubusercontent.com/18206510/187982446-4e668b3f-7faa-470d-833d-79d8878d1f71.png)


selanjutnya kita akan membuat virtual host di local server kita, untuk membuat virtual host kita harus masuk ke file /etc/hosts dengan perintah 


```sudo nano /etc/hosts```

selanjutnya masukan ip server kita dan nama domain yang kita buat

![image](https://user-images.githubusercontent.com/18206510/187982938-37e387fc-4553-4f73-acef-ae01887b352c.png)


jika sudah coba buka browser untuk akses domain kalian

![image](https://user-images.githubusercontent.com/18206510/187983042-aced8ea3-2fee-4592-b1aa-2fa762dcdace.png)

di sini terdapat tanda 502 bad getaway karena aplikasi kita belum berjalan, sekarang kita coba jalankan aplikasi yang pernah kita pakai sebelumnya ikuti langkah-langkah berikut pertama kita clone aplikasinya

```git clone https://github.com/dumbwaysdev/wayshub-frontend.git```


![image](https://user-images.githubusercontent.com/18206510/187985912-3b09971b-0e6c-4053-85fb-42e857a57b9f.png)


masuk ke direktori aplikasi tersebut lalu install npm untuk menjalankan module dari node.js dengan perintah

```npm install```

![image](https://user-images.githubusercontent.com/18206510/187986739-2b96b7a2-f677-45a4-bd9d-1c347962b99e.png)


lalu tunggu hingga prosesnya selesai kemudian start npm dengan perintah

```npm start```

![image](https://user-images.githubusercontent.com/18206510/187988008-db3e273f-09d8-42ad-b44a-a5ab09e7ad3f.png)


lalu coba refresh kembali browser kita

![image](https://user-images.githubusercontent.com/18206510/187988303-e3d0dd2f-548c-496a-9497-b7edf17fb0bb.png)

jika hasilnya seperti ini maka aplikasi kita berhasil dijalankan.

# 4 Load balancing
# 4.1 Apa itu Load Balancing?

Load Balancing adalah suatu jaringan komputer yang menggunakan metode untuk mendistribusikan beban kerjaan pada dua atau bahkan lebih suatu koneksi jaringan secara seimbang agar pekerjaan dapat berjalan optimal dan tidak overload (kelebihan) beban pada salah satu jalur koneksi.

# 4.2 Kenapa Harus Load Balancing?



Jika kita memiliki website atau aplikasi yang telah digunakan hingga ribuan, ratusan atau bahkan jutaan pengguna maka kita harus melakukan load balancing pada aplikasi tersebut agar tidak down, karena beban akses pengguna dibagi ke beberapa server sekaligus.

# 4.3 Membuat Konfigurasi Load Balancing

   Untuk membuat Load Balancing kalian harus membuat server baru lagi. Untuk cara membuat server kalian ikuti saja step by step seperti saat pertemuan Fundamental DevOps : Install Ubuntu Server

  Jika server kalian sudah terbuat maka buatlah aplikasi sederhana sama seperti pertemuan sebelumnya (node.js). setelah itu jalankan aplikasi tersebut.
  
  
  ![image](https://user-images.githubusercontent.com/18206510/187992123-c6784106-8a39-424a-8800-ad9ee3ebfd28.png)
  
  

  ![image](https://user-images.githubusercontent.com/18206510/187992344-06b1b31f-f789-4616-a547-dc409ed6ec32.png)
  
  
  ![image](https://user-images.githubusercontent.com/18206510/187994012-da1edd8c-843b-4858-b439-57413e1f19df.png)

  
jika sudah lalu jalankan aplikasinya dengan perintah 

```npm start```

   
![image](https://user-images.githubusercontent.com/18206510/188029646-41864a0f-7548-45a9-843a-45cf17614500.png)


Sekarang kita sudah mempunyai 2 buah server untuk aplikasi kita.

Sekarang kita akan coba untuk membuat konfigurasi load balancing.

Pertama-tama kita masuk ke dalam konfigurasi reverse proxy yang sudah kita buat sebelumnya dengan melakukan perintah 

```sudo nano /etc/nginx/dumbways/reverse.conf```







































































