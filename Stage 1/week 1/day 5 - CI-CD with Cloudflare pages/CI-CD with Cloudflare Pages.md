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


