# DOCKER

Docker adalah layanan yang menyediakan kemampuan untuk mengemas dan menjalankan sebuah aplikasi dalam sebuah lingkungan terisolasi yang disebut dengan

container. Dengan adanya isolasi dan keamanan yang memadai memungkinkan kamu untuk menjalankan banyak container di waktu yang bersamaan pada host tertentu.

- installasi docker


kita akan menginstall docker dengan menjalankan file yang sudah dimasukkan script installasi docker agar tidak ribet

isi script ini ke dalam file dengan nama yg diinginkan

```
sudo apt-get update
sudo apt-get install \
ca-certificates \
curl \
gnupg \
lsb-release
    
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```


kemudian jalankan dengan perintah bash indock (ganti dengan nama file anda)


![image](https://user-images.githubusercontent.com/18206510/190321884-aaa31677-39a9-444c-ae59-8e488c5c2b3b.png)


lalu tunggu hingga prosesnya selesai


























































# SETUP BACKEND 

pertama kita lakukan clone dulu terhadap aplikasi docker yg kita akan gunakan dengan perintah 

```
git clone https://github.com/dumbwaysdev/wayshub-backend
```

lalu kita install environment buat aplikasinya dengan perintah:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```


lalu kemudian kita buat file dengan nama Dockerfile untuk melakukan build image di aplikasi kita dengan perintah 

```
sudo nano Dockerfile
```

lalu di dalamnya kita isikan seperti berikut: 


![image](https://user-images.githubusercontent.com/18206510/190444161-c0584ae8-afa4-4a98-8f4d-10676492e69e.png)


kemudian di bagian config.json kita isikan seperti berikut



![image](https://user-images.githubusercontent.com/18206510/189695030-5ff9c749-8810-4ac4-93b3-a03ea5ba840d.png)


laluuu



![image](https://user-images.githubusercontent.com/18206510/189697987-4063f72e-5cbb-49d8-ae2a-96da4b1444ac.png)




terussss cek docker images untuk melihat apakah sudah berhasil


![image](https://user-images.githubusercontent.com/18206510/189699700-67616a2c-2bfa-4171-ac14-34c82370eef3.png)















