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



selanjutnya kita akan mengaktifkan pubkeyauthentication dan passwordauthentication dengan cara masuk ke

``` sudo nano /etc/ssh/sshd_config ``` 

![image](https://user-images.githubusercontent.com/18206510/188975652-38bb19c6-8d27-45ef-8c25-abd656bd245c.png)


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












































