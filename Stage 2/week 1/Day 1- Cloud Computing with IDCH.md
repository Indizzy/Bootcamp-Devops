# Cloud Computing with IDCH 

# Apa itu cloud computing?

![image](https://user-images.githubusercontent.com/18206510/188864008-0c66e041-8786-4e30-a696-bc817d65a0c4.png)



   Cloud computing (komputasi awan) adalah metode penyampaian berbagai layanan melalui internet. Sumber daya yang dimaksud contohnya adalah aplikasi seperti penyimpanan data, server, database, jaringan, dan perangkat lunak.
  Daripada menyimpan banyak file di hard drive atau penyimpanan lokal di komputer atau handphone, penyimpanan berbasis cloud memungkinkan Anda menyimpan file selama Anda memiliki akses ke internet.


# Keuntungan menggunakan cloud computing :

  Cloud computing bukan sekadar bisa mengakses file secara remote. Berkat cloud computing, penggunanya dapat mengecek email di komputer mana pun, atau bahkan menyimpan serta mengakses file dari mana pun seperti Dropbox atau Google Drive.
Maka itu, perusahaan-perusahaan yang menggunakan cloud dapat memangkas biaya secara signifikan. Sebelum adanya cloud, perusahaan harus membeli, memiliki, membangun manajemen informasi teknologi (IT) mereka sendiri. Sebaliknya, dengan adanya cloud, perusahaan hanya membutuhkan pusat server dan divisi IT agar memastikan internet yang dimiliki cepat dan stabil, agar karyawannya bisa berinteraksi dengan cloud secara online.
Cloud membuat para karyawan bisa menghemat ruang penyimpanan di laptop atau komputer. Saat ada perangkat lunak atau program yang membutuhkan update, tinggal download saja tanpa menggunakan cara tradisional seperti menggunakan disc atau flash drive. 
Contohnya Adobe, penggunanya bisa mengakses aplikasi melalui Cretive Cloud dengan model subscription. Ini memungkinkan penggunanya mengunduh versi terbaru dan memperbaiki program lebih mudah.


Layanan penyedia cloud yang populer di indonesia antara lain

- IDCloudHost
- AWS (Amazon Web Service)
- Microsoft Azure
- IBM Cloud
- Alibaba Cloud 



Kali ini kita akan mencoba melakukan cloud computing dengan menggunakan layanan dari IDCloudHost pertama-tama lakukan register di 
https://idcloudhost.com/ 


lalu di bagian pojok kanan atas pilih yang console 

![image](https://user-images.githubusercontent.com/18206510/188867103-eda69c2f-0e35-49e0-81ed-c30ce90532be.png)


selanjutnya kita akan diarahkan ke halaman dashboard dari akun yang sudah kita buat tadi

![image](https://user-images.githubusercontent.com/18206510/188867408-d116a326-0be6-4d51-aaf3-2ea573c06cf7.png)



lalu di sini karena saya akan menggunakan akun dari dumbways maka di bagian profil saya klik kemudian act as (nama akun yang ingin kita pakai) dengan catatan sebelumnya sudah dapat akses dari akun tersebut


![image](https://user-images.githubusercontent.com/18206510/188867870-f93f4db4-30fa-4aef-9475-776a4e7e8f49.png)



lalu setelah itu kita bisa memilih ```compute``` lalu ```new``` di bagian kiri dashboard IDCH kita untuk mulai membuat server


![image](https://user-images.githubusercontent.com/18206510/188880965-568ba1bd-20f6-47e6-bdb5-6177126283e3.png)



Lalu pada bagian ``` Create new resource ``` kita isi seperti berikut :

Type        : virtual machine (karena kita di sini akan membuat machine virtual)

OS          : di sini saya memilih Ubuntu 20.04 lts

Location    : kemudian di sini kita pilih lokasinya ke Indonesia


![image](https://user-images.githubusercontent.com/18206510/188887226-a3913b8f-9352-40c0-b2ad-5aa25f08cfa7.png)



Size              : 1 cpu, 1GB RAM, 20 GB Disk

Public IP         : kita select pada bagian create a public ipv4 

Vpc Network       : biarkan default saja

Username          : kita isi bebas sesuai keinginan

password          : bebas

confirm password  : ulangi password 


SSh               : di sini kita biarkan kosong saja


![image](https://user-images.githubusercontent.com/18206510/188889591-ce78d3a9-c573-4e3f-853f-080d95b685e3.png)



di bagian resource name : nama bebas

Lalu klik ```Create``` 


![image](https://user-images.githubusercontent.com/18206510/188890114-dded23f9-7375-4083-8ef9-dde2c9101817.png)


tunggu prosesnya selesai


![image](https://user-images.githubusercontent.com/18206510/188893071-0bff7c0a-f260-475e-8271-5606d183130e.png)


nah jika sudah selesai maka beginilah tampilannya 


![image](https://user-images.githubusercontent.com/18206510/188968073-a8f4cbae-dcf6-4dd5-a8ce-417d4cafea76.png)



lalu sekarang kita koneksikan server tadi ke lokal kita melalui SSH dengan melakukan perintah 

``` ssh user akun@Ip address dari server yang kita buat tadi ```


![image](https://user-images.githubusercontent.com/18206510/188969325-c7009ad1-768e-4d6a-90e3-881656526fb5.png)


selanjutnya kita lakukan update dan upgrade


![image](https://user-images.githubusercontent.com/18206510/188979282-3550071a-c440-4533-b3c7-fa3598c5e8ec.png)



kemudian di sini kita akan menjalankan aplikasi dumblix frontend, pertama-tama kita install engine dari si node js dengan perintah 

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```


![image](https://user-images.githubusercontent.com/18206510/188977171-0cc26f61-ee48-411d-af9e-03a7c1b443da.png)


setelah itu kita lakukan eksekusi pada bash dengan perintah 

```
exec bash
```
lalu selanjutnya kita install NVM ( node version manager ) dan NPM ( Node Package Manager )

dengan perintah 

```
nvm install 16 (untuk menginstall versi 16)
```

![image](https://user-images.githubusercontent.com/18206510/188981381-39d3080e-e0cd-4b42-9568-1ddd4a71e061.png)


lalu untuk menginstall npm gunakan perintah

```
sudo apt install npm
```

kemudian tunggu sampai selesai

![image](https://user-images.githubusercontent.com/18206510/188982159-cc319ce5-93ba-4e91-8a32-0c779bba2c7b.png)


kemudian kita lakukan cloning pada aplikasi yang akan kita gunakan dengan cara memasukkan command berikut

```
git clone https://github.com/dumbwaysdev/dumbflix-frontend

```

![image](https://user-images.githubusercontent.com/18206510/189026294-f025c21f-bf2f-46f0-b679-4e2c843ca58c.png)


setelah itu kita install node module di dalam aplikasi yang kita clone tadi dengan perintah 


```
npm i

```

![image](https://user-images.githubusercontent.com/18206510/189026524-808cce67-e46b-4f49-a6f5-77be51a7e4bd.png)



Selanjutnya kita akan membuat satu server lagi dimana akan kita install nginx, pertama kembali lagi ke halaman IDCloudhost lalu pilih seperti berikut :

Type  : kali ini kita pilih app catalog agar bisa menginstall nginx

OS    : kita klik NGINX (ubuntu 21.04)



![image](https://user-images.githubusercontent.com/18206510/189028728-1e5f6267-acf7-428f-aedf-7f2583df6d65.png)


Location    : kita pilih indonesia


Size        : 1 cpu, 1GB ram, 20 GB disk


public ip   : kita select 


vpc network : kita biarkan saja default


username    : isi bebas


password    : bebas


![image](https://user-images.githubusercontent.com/18206510/189029328-5f8c9723-a687-4d2e-b6d5-111b034946d2.png)


confirm password : ulangi password yang sama


resource name : bebas


![image](https://user-images.githubusercontent.com/18206510/189029583-9f771627-1de2-4994-8ea0-d2d5c152f4f3.png)


lalu tunggu prosesnya hingga selesai


![image](https://user-images.githubusercontent.com/18206510/189029672-52518989-b19e-4784-880e-5a48303769d7.png)


begini tampilan server yang sudah kita buat tadi


![image](https://user-images.githubusercontent.com/18206510/189030079-29141224-a168-4ad1-beeb-a4d8d54a9fef.png)


selanjutnya lakukan remote server pada seerver yang sudah kita buat tadi dengan perintah


```ssh username@ip server```

![image](https://user-images.githubusercontent.com/18206510/189030530-984f3297-efa1-422c-a98e-bfd47450b2b7.png)


seperti biasa kita lakukan update dan upgrade 


![image](https://user-images.githubusercontent.com/18206510/189030806-fe5affb3-95a6-4c4d-89e1-5b39696a3e2f.png)


kemudian untuk cek nginx yang kita gunakan masukan perintah 

```nginx -v ```

![image](https://user-images.githubusercontent.com/18206510/189034438-f80391ae-02ba-4c48-9064-3a1f0394055e.png)


lalu kita masuk ke /etc/nginx/ untuk membuat folder dimana kita akan melakukan reverse proxy

![image](https://user-images.githubusercontent.com/18206510/189034807-25479054-d47b-4fe9-96bb-b4aabc04f19a.png)


selanjutnya kita buat file untuk menyimpan reverse proxy kita dengan perintah 

``` sudo nano proxy.conf```

lalu di dalamnya kita isi sebagai berikut 


![image](https://user-images.githubusercontent.com/18206510/189038783-2bb15bff-3b7a-46b4-9140-994d5c595393.png)

setelah itu tekan ctrl + x lalu Y kemudian enter untuk menyimpannya


kemudian kita masuk ke file nginx.conf untuk menambahkan konfigurasi proxy pass yang kita buat tadi pada bagian include


![image](https://user-images.githubusercontent.com/18206510/189039316-7f2a33a1-d0de-4997-b205-8de954abbbdf.png)


kemudian cek dengan perintah 

```sudo nginx -t```

kemudian reload nginx kita dengan perintah 


```sudo systemctl reload nginx```

![image](https://user-images.githubusercontent.com/18206510/189039480-e00fd5a7-23c8-4b22-b953-1bebc2fb1147.png)


kemudian di server aplikasi yang pertama kita install pm2 agar aplikasinya bisa berjalan secara background


masukan perintah 

```npm installn pm2 -g```


![image](https://user-images.githubusercontent.com/18206510/189044133-c7ff2c6b-e0ce-4e63-8234-2563dbac87fe.png)



lalu kita buat ekosistem pm2 nya dengan perintah 


``` pm2 ecosystem simple ```


![image](https://user-images.githubusercontent.com/18206510/189041033-f5783d9f-ddcc-4ff3-90d9-304720df9872.png)


lalu kita masuk ke file ecosystem.config.js

![image](https://user-images.githubusercontent.com/18206510/189041992-ece59e73-0774-45b3-9bba-0ac9cadf12c6.png)


di sini kita masukan nama app kita dan script npm start agar app kita secara automatis memulai npm 


![image](https://user-images.githubusercontent.com/18206510/189042121-9f9ca859-de59-48b5-9c8c-9e56d63c0d11.png)


lalu kita coba jalankan dengan perintah

```pm2 start ecosystem.config.js```

![image](https://user-images.githubusercontent.com/18206510/189042276-fc791d10-12f7-43a8-a893-18685a21a12f.png)


lalu kita cek pada browser kita


![image](https://user-images.githubusercontent.com/18206510/189045015-619d5098-e8d5-4fe6-bc37-4c739f77b357.png)


kemudian kali ini kita akan membuat DNS atau Domain name server 

apa itu DNS server? Singkatnya, DNS adalah sebuah sistem yang mengubah URL website ke dalam bentuk IP Address. Tanpa DNS, Anda harus mengetikkan IP Address secara lengkap ketika ingin mengunjungi sebuah website.


pertama lakukan registrasi di website cloudflare : https://www.cloudflare.com/


setelah itu klik di bagian student


![image](https://user-images.githubusercontent.com/18206510/189045906-93620b0b-c8b0-4c6a-b9f8-42e7ba325e5e.png)


lalu di sebelah kiiri masuk pada bilah DNS 


![image](https://user-images.githubusercontent.com/18206510/189046035-8bad81e5-4475-4155-9504-c66d8f29bf88.png)


pilih bagian add record lalu di sini kita isi dengan nama lalu ip dari server kedua tadi dan pada bagian proxy status kita isi dns only lalu pilih save


![image](https://user-images.githubusercontent.com/18206510/189046935-2a9d0ebb-683a-477c-98e5-8db8d8dcf6dd.png)


kemudian kembali lagi ke server nginx kita untuk melakukan konfigurasi proxy pada file /etc/nginx/dumbflix


![image](https://user-images.githubusercontent.com/18206510/189048891-a472a2b4-b7bd-4bd4-bc8d-ec3d8a9f53f6.png)


setelah itu simpan lalu kita cek dengan perintah 


```sudo nginx -t```


![image](https://user-images.githubusercontent.com/18206510/189049050-766aa650-97b2-4bf4-aafe-f868179e3637.png)


kemudian kita coba cek dengan browser kita


![image](https://user-images.githubusercontent.com/18206510/189049334-90078ec5-a9ec-4a9b-ae3f-a3f1af14dff3.png)


nah tapi di sini app kita masih bersifat http artinya keamanannya masih rendah untuk itu kita peerlu melakukan setup SSL

# Apa itu SSL?

SSL adalah singkatan dari Secure Socket Layer, salah satu komponen penting yang harus dimiliki website. Dengan SSL, transfer data di dalam website menjadi lebih aman dan terenkripsi. Bahkan saking pentingnya, Google Chrome melabeli website tanpa sertifikat SSL sebagai Not Secure.


Apabila sistem keamanan ini ditambahkan pada website Anda, maka URL website akan berubah menjadi HTTPS. Tujuan utama pemasangan SSL adalah sebagai pengaman pertukaran data yang terjadi melalui jaringan internet.


langkah pertama untuk melakukan itu kita masuk dulu ke akun cloudflare kita tadi lalu klik my profile dan pilih Api token


![image](https://user-images.githubusercontent.com/18206510/189050842-c763f09c-f56c-447f-b8c5-8840dd71642a.png)


klik pada bagian View global API key, dan masukan password cloudflare kita lalu copy token tersebut


![image](https://user-images.githubusercontent.com/18206510/189051344-a70eb55f-b3b3-40b1-ac8a-69a8437608be.png)


selanjutnya kembali ke server nginx kita tadi lalu buat direktori untuk konfigurasi cloudflarenya


![image](https://user-images.githubusercontent.com/18206510/189051751-38dffd69-05ca-4d0f-8d6f-89e911fce8b2.png)


di sini saya membuat file dengan nama .rahasia tujuan dari penggunaan titik tersebut adalah agar direktori tersebut di hidden



lalu di dalamnya kita buat lagi satu file untuk meletakan api token kita di dalamnya

![image](https://user-images.githubusercontent.com/18206510/189052742-6d66c7c7-8ba7-4d4b-a09d-317a3aa03546.png)

jika sudah lalu kita simpan dan atur permissionnya agar hanya bisa di read saja dengan perintah 


```chmod 400 nginx.coba```


![image](https://user-images.githubusercontent.com/18206510/189053103-78c8f287-1e33-4278-bb4f-d54326928317.png)



selanjutnya kita lakukan instalasi certbot dengan perintah 

```sudo snap install --classic certbot```

![image](https://user-images.githubusercontent.com/18206510/189054229-394d529f-ec75-4c2e-9816-57ed339ac417.png)



kemudian Masukan perintah berikut agar certbet bisa di akses menggunakan command


```sudo ln -s /snap/bin/certbot /usr/bin/certbot```


![image](https://user-images.githubusercontent.com/18206510/189054843-33652b32-a14d-46a9-9e37-a5032ca4da08.png)


lalu jalankan certbot dengan perintah 

``` sudo certbot```

![image](https://user-images.githubusercontent.com/18206510/189055622-6c9298b3-b585-4f87-828f-d2442b554ef9.png)

pertama masukan email cloudflare

kedua pilih Y untuk sertifikatnya 

ketiga pilih saja N untuk mengabaikan email jika akan ada expired pada sertifikat kita

keempat pilih domain yang akan dirubah dari http ke https

lalu jika sudah maka akan muncul seperti ini

![image](https://user-images.githubusercontent.com/18206510/189056076-4b5c1321-fd0a-47bd-86f5-dab11c9f0e42.png)


sekarang kita coba kembali akses melalui browser kita

![image](https://user-images.githubusercontent.com/18206510/189056246-ee827321-7b47-4e60-92e4-5aa552574d9b.png)

nah di sini domain kita sudah berubah menjadi HTTPS 




# Additional

jika merasa lelah memasukkan password setiap kali mengakses server melalui lokal kita maka bisa kita lakukan setting authorized key-nya


pertama masuk ke lokal kita lalu generate ssh dengan perintah 

```ssh-keygen```


![image](https://user-images.githubusercontent.com/18206510/189058968-5c417dc6-9e43-41d7-abb0-493a4d8a3c1e.png)

di situ karena saya sudah pernah melakukan generate maka tertulis overwrite .... 

jika belum maka tidak akan keluar 

kita tinggal enter saja

lalu kita copy ke server kita dengan perintah 

```scp -r  .ssh/id_rsa.pub indist@103.179.57.241:~/tempat_rsa.pub```

![image](https://user-images.githubusercontent.com/18206510/189060837-98a52854-cc14-4ff4-83f9-4d4fe78566ff.png)


masuk ke server tujuan tadi lalu di sini kita bisa lihat bahwa file sudah tercopy


langkah selanjutnya adalah masukan file tadi ke authorized key dengan cara 

``` cat tempat_rsa.pub >> .ssh/authorized_keys```

![image](https://user-images.githubusercontent.com/18206510/189062159-2386af0d-9124-4594-b496-dd43fb2f80c0.png)


selanjutnya tinggal exit lalu cek apakah kita masih dimintai password saat melakukan login ke server kita melalui lokal


![image](https://user-images.githubusercontent.com/18206510/189062568-2233eadc-ca57-4b11-953d-e8adfc198ea2.png)


dan di situ terlihat kita sudah tidak dimintai password











































































