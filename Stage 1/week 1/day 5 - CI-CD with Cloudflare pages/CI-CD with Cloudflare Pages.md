Selain menggunakan tools CI/CD yang telah disebutkan sebelumnya, kita akan mencoba melakukan konfigurasi sederhana untuk memahami konsep dan cara kerja CI/CD menggunakan Cloudflare Pages.

pertama-tama mari kita bahas dulu apa itu CI/CD :
Continuous integration (CI) adalah pengintegrasian kode ke dalam repositori kode kemudian menjalankan pengujian secara otomatis, cepat, dan sering. Kamu dapat melakukan CI ini dengan menggunakan perintah  commit.

Sementara continous delivery atau continuous deployment (CD) adalah praktik yang dilakukan setelah proses CI selesai dan seluruh kode berhasil terintegrasi, sehingga aplikasi bisa dibangun lalu dirilis secara otomatis.

CI/CD Set-Up with Cloudflare
# 1. Registrasi

Pastikan kalian sudah melakukan register ke https://cloudflare.com, Jika kalian belum mempunyai akun Cloudflare kalian bisa melakukan registrasi dengan klik link tersebut.
kemudian klik kata sign up yg berada di pojok kanan atas
![image](https://user-images.githubusercontent.com/18206510/187818523-f23b7f80-586f-4127-b55c-ce58fcd13039.png)

setelah melakukan registrasi lalu masuk ke menu home

![image](https://user-images.githubusercontent.com/18206510/187818642-76f995b7-2e5b-42bb-8769-9cfec973e869.png)

jika sudah lalu masuk ke menu pages untuk membuat project baru tapi sebelum bisa membuat project nanti kalian akan diminta untuk melakukan verifikasi akun cloudflare yang sudah kalian buat

klik connct to git kemudian pilih connect to github agar repository kita di github terdeteksi oleh cloudflare
![image](https://user-images.githubusercontent.com/18206510/187819833-8cf68266-3c16-4811-adfd-9bcf6468a454.png)


