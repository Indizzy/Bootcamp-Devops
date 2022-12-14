# Task Version Control System
# Git

Git adalah suatu perangkaat lunak yang diciptakan untuk mencatat dan memanage perubahan file maupun repository salah satunya yang paling terkenal adalah github yang akan kita bahas kali ini

Git Configuration
Step 1 - Konfigurasi Git dengan Github
![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-20-13.png)


Jika sudah menginstall git , maka selanjutnya masuk ke terminal , kemudian masukan perintah di bawah ini :

git config --global user.name ".................."

isi titik-titik diatas menggunakan username github

git config --global user.email "................."

isi titik-titik diatas dengan menggunakan email di github

git config --list

![IMG](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-24-40.png)

perintah diatas untuk mengecek apakah configurasi yang kita lakukan sudah berhasil atau blum

Step 2 - Menghubungkan SSH

1.SSH memungkinkan kita untuk melakukan push ke repository github tanpa login. Berbeda dengan cara yang biasa (melalui HTTPS), kita harus memasukkan username dan password setiap kali melakukan push. Tapi dengan SSH kita tidak akan melakukan itu lagi.

Untuk generate nya, masukan perintah berikut :

ssh-keygen

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-26-36.png)

SSH key Location

Jika kalian sudah menjalankan perintah sebelumnya maka kalian sudah berhasil untuk men-generate SSH key yang akan kalian gunakannya. Untuk lokasi SSH key yang sudah kalian generate tadi berada di .ssh/id_rsa.pub. Jika sudah lakukan copy pada SSH-key tersebut.

cat .ssh/id_rsa.pub

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-33-35.png)

Add new SSH to github settings

Tahap selanjutnya setelah kalian melakukan copy SSH-key adalah memasukkannya kedalam config github dengan membuka https://github.com/settings/keys.

Jika sudah langsung tekan saja di bagian New SSH key.

Setelah itu masukkan saja SSH key yang sudah kalian copy tadi kebagian key. Jika sudah Langsung saja save dengan menge-klik bagian Add SSH key.

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-29-49.png)

Check Connection

Jika kalian sudah melakukan semua step di atas maka kalian sudah berhasil meng-koneksikan local kalian dengan Github.

Untuk memastikan apakah sudah terkoneksi kita bisa menggunakan perintah di bawah ini.

ssh -T git@github.com

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-36-59.png)

Jika muncul teks seperti gambar diatas. maka kalian sudah berhasil mengkoneksikan local kalian dengan Github.


Step 3 - Membuat 3 Buah Repository Untuk apk NodeJs, Golang & python

apa itu Repository? Repositori atau repo adalah direktori penyimpanan file proyek. Di sini, Anda bisa menyimpan apa pun yang berkaitan dengan proyek yang sedang Anda buat, misalnya file kode, gambar, atau audio. Repo sendiri bertempat di penyimpanan atau storage GitHub atau repositori lokal di komputer Anda

Pertama kita buat Repository NodeJs Terlebih dahulu dengan membuat direktorinya terlebih dahulu kemudian inisiasi git didalamnya menggunakan perintah berikut :

mkdir nodejs

cd nodejs

git init

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-57-06.png)


Setelahnya kita membuat repository pada github juga, dengan masuk ke profile github dan klik "new repository" dibagian kanan kemudian beri nama repository nya dan klik "create new repository" di bagian bawahnya

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-57-58.png)


 Sekarang kita remote dengan perintah dibawah ini dengan paste kan link ssh tadi

git remote add origin https://github.com/indizzy/nodejss.git

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2022-59-29.png)

dan masukan perintah di bawah ini untuk mengecek nya

git remote -v

kemudian kita lakukan remote pada github kita

git remote set-url origin git@github.com:

![IMG](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2023-28-08.png)

link diatas diambil dari github dengan cara klik pilihan "ssh" nya

Setelah Selesai me-remote, kita akan menambahkan file, aplikasi dan lain sebagainya ke dalam github melalui git,

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2023-34-53.png))

ada 3 tahapan dalam git, yaitu : modify, staging dan commit.

tahap pertama yaitu modify, kita buat file yang akan kita tambahkan, apabila ada yang tidak perlu ditambahkan ke github, kita bisa menggunakan ".gitignore" dengan cara menuliskan nama filenya dalam git.ignore

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2023-49-17.png)


file yang coba kita abaikan

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2023-46-18.png)

Setelahnya Kita bisa cek Status Nya menggunakan "git status" apakah semuanya berjalan sesuai rencana :

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-25%2023-47-06.png)


Setelah Modify semua file, kita masuk ke tahap staging,

sekarang kita add semua file yang ada dengan perintah

git add .

setelah nya kita cek statusnya

Kemudian untuk tahapan selanjutnya yaitu commit atau production, kita akan menggunakan perintah berikut :

git commit -m "................"

titik-titik diatas diisi dengan pesan apa yang akan kita isi

git status

sebelum melakukan push, perintah diatas berfungsi juga untuk mengetahui pada branch apa kita berada

git push origin master

karena kita berada di branch master, kita push ke branch itu :

nah, dari gambar tersebut, dapat disimpulkan bahwa kita berhasil melakukan push

Kemudian kita cek github kita pakah benar sudah ter-push

dan dari gambar tersebut itu berarti kita berhasil melakukan push

Tahap Selanjutnya, kita akan membuat 3 buah branch baru, yaitu : Development, Staging, dan Production

Untuk Membuat Branch, Kita gunakan perintah :

git branch development

git branch staging

git branch production

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-04-37.png)


![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-08-45.png)

dan perintah berikut untuk mengecek branch yang tersedia :

git branch -a

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-05-22.png)

Setelahnya, Kita akan push ke semua branch

kita bisa berpindah branch dengan perintah

git checkout (name branch)

Pertama Development


Ke-2 Staging

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-09-58.png)


ke-3 Production

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-08-05.png)

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-09-53.png)

dari gambar diatas, sudah terbukti bahwan branch nya sudah ada semua.


dari 3 gambar diatas, sudah terbukti bahwa di masing-masing branch, sudah ter-push juga semua filenya.


Tugas NodeJs Sudah selesai, Sekarang kita akan melakukan hal yang sama untuk aplikasi Golang dan Python.

Berikut hasil untuk aplikasi Python

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-46-12.png)

Berikut hasil Untuk aplikasi Golang

![IMG 1](https://github.com/Indizzy/Bootcamp-Devops/blob/main/Stage%201/week%201/images%204/Screenshot%20from%202022-08-26%2000-38-47.png)
