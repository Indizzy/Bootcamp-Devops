# 1. Terminal
# 1.1 Apa itu Terminal?

Terminal adalah sebuah command prompt atau shell dimana kita dapat mengontrol file, membuat folder, membuat akses, mengubah akses ataupun membaca dan sebagainya. Sebelum ada GUI (Graphical User Interface), semua aktivitas komputer dilakukan dengan menggunakan terminal, dikarenakan proses tersebut lebih cepat dilakukan daripada menggunakan GUI.
# 1.2 Mengapa Mempelajari Terminal?

Pada sistem operasi server berbasis unix/linux memiliki tampailan berbasis text, tidak seperti sistem operasi windows yang memiliki interface yang dapat di klik-klik. Sehingga memerlukan keahlian khusus untuk memanajemen server-server linux.
# 1.3 Apa itu Bash

BASH (Bourne Again Shell) adalah bahasa yang berjalan di atas kernel (linux / unix), yang berfungsi sebagai penerjemah antara user dan sistem operasi.

Contoh :

      cp (name-file)

keterangan : untuk meng-copy suatu file
```
  mkdir (name-directory)
```  
keterangan : untuk membuat suatu directory/folder

```
  chown (your-user:your-user) (file/directory)
```

keterangan : untuk mengubah kepemilikan file maupun directory.

kali ini kita akan mencoba membuat file bash sederhana yang berfungsi untuk melakukan update dan upgrade pada server serta satu file sederhana lain untuk melakukan setup firewall pada port 22(port ssh), 80 (http) port 443 (port https)

sebelum melakukan setup pada firewall ada baiknya kita mengetahui dulu apa sih firewall itu?

Firewall adalahngaris pertahanan pertama dalam menjaga keamanan jaringan komputer. Firewall menjadi bagian penting dari teknologi sistem keamanan. Selain itu, berbagai jenis firewall bekerja sama untuk menyediakan suatu payung sistem perlindungan lengkap.

Risiko utama komputer atau jaringan yang tidak dilindungi oleh firewall adalah sebagai berikut:

- Tanpa firewall, komputer akan menerima setiap koneksi ke jaringan dari siapapun. Sehingga rentan terhadap kejahatan cyber.

- Tanpa firewall dapat membuat perangkat komputer memiliki akses terbuka, yang memungkinkan siapa saja dapat memegang kendali atas komputer dan jaringan pribadi. Peretas dapat melakukan pencurian data pribadi atau menghapus data tersebut.

# menginstall firewall

untuk menginstall firewall masukan perintah ```sudo apt install ufw -y```

![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/install.png)


kemudian setelah itu jika kita ingin melakukan setup firewall maka bisa kita gunakan perintah sebagai berikut 

```sudo ufw allow 22```   ini berfungsi untuk membuka akses port 22

```sudo ufw allow 80```   ini berfungsi untuk membuka akses port 80

```sudo ufw allow 443```  ini berfungsi untuk membuka akses port 443


![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/allow.png)


sekarang mari kita membuat file sederhana yang berisi command untuk melakukan update dan upgrade maupun melakukan setup firewall

Pertama-tama mari kita buat file yg berisikan script untuk melakukan update dan upgrade

kita bisa masukan perintah sudo nano (kemudian nama file yg kita inginkan)

setelah masuk pada nano editor kita masukan script berikut 

```
sudo apt update 
echo "Terupdate"

sudo apt upgrade
echo "Terupgrade"

```

![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/updetdangred.png)


jika sudah silakan keluar dari nano text editor dengan mengklik ctrl + x kemudian Y lalu enter

lalu selanjutnya yang harus kita lakukan adalah melakukan modifikasi pada file tadi agar bisa di eksekusi dengan cara menjalankan perintah 

```sudo chmod +x (nama file)```


![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/chmod.png)


kemudian baru kita jalankan file tadi dengan perintah './(nama file)

![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/jalankan.png)

Lalu tunggu sampai selesai


![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/selesai.png)


setelah itu lakukan langkah yang sama untuk membuat file sederhana yang mampu menjalankan setup pada firewall namun kali ini masukan perintah membuat firewall yang sudah kita pelajari tadi kedalam file nya dengan cara

`sudo nano` (nama file yang kita inginkan)

jika sudah maka sisipkan script ini pada file tersebut


```sudo ufw allow 22``` 

echo "22 ready" 

```sudo ufw allow 80```

echo "80 ready"

```sudo ufw allow 443``` 

echo "443 ready"


![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/scriptfire.png)

lakukan juga modifikasi seperti tadi agar file kita bisa tereksekusi

lalu jalankan filenya maka akan keluar hasil sebagai berikut :

![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/ready.png)


selain itu kita juga bisa memonitoring server kita dengan perintah htop

jika belum memiliki htop maka bisa menginstallnya dengan perintah 

```sudo apt install htop -y```


jika sudah maka masukan perintah ```htop``` untuk memonitoring server kita maka akan keluar hasil seperti ini

![image](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%202/images/Screenshot%20from%202022-09-01%2016-30-54.png)

Keterangan :

 CPU adalah berapa jumlah core yang kita miliki.
 Mem adalah total penggunaan memory.
 Swp adalah Memory cadangan.
 Tasks adalah aplikasi yang sedang berjalan di server.
 Load average adalah rata-rata aplikasi yang berjalan.
 Uptime adalah berapa lama server kita hidup.
 PID adalah nomor proses id setiap proses yang berjalan di linux.
 VIRT adalah memory yang terpakai.
 Command adalah perintah apa yang sedang di jalankan.

































