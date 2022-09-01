Selain menggunakan tools CI/CD yang telah disebutkan sebelumnya, kita akan mencoba melakukan konfigurasi sederhana untuk memahami konsep dan cara kerja CI/CD menggunakan Cloudflare Pages.

pertama-tama mari kita bahas dulu apa itu CI/CD :
Continuous integration (CI) adalah pengintegrasian kode ke dalam repositori kode kemudian menjalankan pengujian secara otomatis, cepat, dan sering. Kamu dapat melakukan CI ini dengan menggunakan perintah  commit.

Sementara continous delivery atau continuous deployment (CD) adalah praktik yang dilakukan setelah proses CI selesai dan seluruh kode berhasil terintegrasi, sehingga aplikasi bisa dibangun lalu dirilis secara otomatis.

CI/CD Set-Up with Cloudflare
# 1. Registrasi

Pastikan kalian sudah melakukan register ke https://cloudflare.com, Jika kalian belum mempunyai akun Cloudflare kalian bisa melakukan registrasi dengan klik link tersebut.
kemudian klik kata sign up yg berada di pojok kanan atas
![image](https://user-images.githubusercontent.com/18206510/187820021-33518c4b-9e6f-4262-8466-6cee82c366c3.png)


setelah melakukan registrasi lalu masuk ke menu pages

![image](https://user-images.githubusercontent.com/18206510/187820207-b0eee26d-3f1f-415a-b819-f94dfb86833c.png)

jika sudah lalu masuk ke menu pages untuk membuat project baru tapi sebelum bisa membuat project nanti kalian akan diminta untuk melakukan verifikasi akun cloudflare yang sudah kalian buat

klik connct to git kemudian pilih connect to github agar repository kita di github terdeteksi oleh cloudflare
![image](https://user-images.githubusercontent.com/18206510/187820301-4b9b04e8-b396-45fc-adeb-869f91d99879.png)

sebelum menentukan repository yang akan kita gunakan di sini kita akan melakukan fork terhadap repository yang akan kita gunakan 
di sini saya menggunakan repository dari https://github.com/dumbwaysdev/wayshub-frontend

klik create new fork
![image](https://user-images.githubusercontent.com/18206510/187824497-8c15239a-0640-4e7b-926c-5a5e8bdc775a.png)

kemudian kembali lagi ke halaman connect to github lalu masukkan akun github kemudian pilih all repository

![image](https://user-images.githubusercontent.com/18206510/187828954-83944c77-9957-4616-94e4-7f0e009ca1e5.png)

lalu kita akan diarahkan kembali ke menu pages cloudflare kita kemudian pilih repository yang sudah kita fork tadi lalu klik begin setup

![image](https://user-images.githubusercontent.com/18206510/187829146-f9378a20-58e1-47eb-aab2-d760102889ea.png)

kemudian pada bagian setup builds and deployment pada bagian framework preset pilih sesuai framework yang kita gunakan di sini saya memilih Create React app karena framework yang kita gunakan adalah react, lalu pada bagian Build Command akan terisi automatis 
jika sudah maka klik save and deploy

![image](https://user-images.githubusercontent.com/18206510/187829607-d1d908ee-28d5-48fe-94e1-a4ff6b87881e.png)
 
 setelah itu tunggu sampai proses deploy selesai
 
 ![image](https://user-images.githubusercontent.com/18206510/187829763-6d5fb24f-0677-4bde-92c1-ec8ce5fdee0a.png)

jika sudah berhasil maka akan muncul notifikasi seperti ini

![image](https://user-images.githubusercontent.com/18206510/187829933-890cbbfc-aad9-4bc4-93ff-3f4564e63a76.png)


selanjutnya mari kita coba membuka url yang diberikan untuk memastikan apakah project kita bisa berjalan di browser

![image](https://user-images.githubusercontent.com/18206510/187830115-e611a9ee-ffca-4850-847a-5a8f697a2958.png)

nah jika sudah berhasil maka akan muncul tampilan dari project yg kita buat tadi

Lalu di step kali ini kita akan mencoba untuk mengubah title pada project yang kita buat tadi












