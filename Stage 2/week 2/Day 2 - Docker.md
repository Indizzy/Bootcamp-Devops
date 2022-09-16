

![image](https://user-images.githubusercontent.com/18206510/190534684-4162ee1c-666c-4dd8-a270-6f29a5a7df16.png)







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


# setup frontend


masuk ke server lalu clone aplikasinya dengan perintah :

```
git clone https://github.com/dumbwaysdev/housy-frontend.git
```

lalu lakukan setup pada file api.js


![image](https://user-images.githubusercontent.com/18206510/190451147-d5598b33-95b8-4f3f-83eb-7aaa3b1fae8a.png)



kemudian kita buat dockerfile dengan settingan seperti berikut



![image](https://user-images.githubusercontent.com/18206510/190451646-95ec9a50-04a7-4bc3-b8b1-4140dd0e560c.png)



# Docker Compose 

- Mysql


buat file docker compose dengan nama mysql.yaml lalu masukan settingan berikut



![image](https://user-images.githubusercontent.com/18206510/190452134-f808dc49-14cc-4f10-aeeb-8fee9acb4850.png)



kemudian jalankan dengan perintah 

```
docker compose -f mysql.yaml up -d
```


![image](https://user-images.githubusercontent.com/18206510/190452291-a0d12583-3318-40f7-825a-f30bbb3f0b62.png)


- masuk ke mysql dengan perintah :

```
docker exec -it grup3-mysql-1 /bin/bash
mysql -u housy -p
```

![image](https://user-images.githubusercontent.com/18206510/190455401-eaf3e679-6647-459b-9131-91dbc8580ce5.png)




kemudian untuk melihat isi database kita bisa gunakan perintah 

```
show databases;
```


![image](https://user-images.githubusercontent.com/18206510/190456130-52e930d9-a48b-47a1-b0ed-5b643b80f6b6.png)



# setup docker compose untuk FE dan BE


buat file docker compose-nya 

```nano docker-compose.yaml```


lalu masukan seperti berikut :


![image](https://user-images.githubusercontent.com/18206510/190456773-78224953-bfb3-40d7-a278-76699640c4ea.png)


kemudian jalankan perintah 


```docker compose up -d```


![image](https://user-images.githubusercontent.com/18206510/190457300-86f75104-74bd-45ff-8886-32e8f3b6c1c8.png)



kita bisa mengecek docker image dan container dengan perintah 


```docker images```

dan

```docker ps -a```



![image](https://user-images.githubusercontent.com/18206510/190457696-4f8357d0-1b71-4383-b8ee-e62e665e2eeb.png)



# Membuat Reverse proxy


masuk ke server getaway kita lalu install nginx

```ssh user@ip-server```


```
sudo apt install nginx
```



![image](https://user-images.githubusercontent.com/18206510/190459198-85b4bb74-1be4-44d9-96fb-69b5fa7f39c8.png)



kemudian buat direktori dan buat sebuah file untuk reverse proxy

```
  mkdir rp && cd rp
  sudo nano reverse1.conf
  ```


![image](https://user-images.githubusercontent.com/18206510/190460211-9f5f6c26-7bb9-4f2f-b87f-1c8849b584d2.png)



kemudian buat satu file lagi dengan untuk reverse proxy backend


```sudo nano reverse2.conf```



![image](https://user-images.githubusercontent.com/18206510/190460789-ad491372-9cbd-4bd2-8f18-c468a5855d7d.png)




lalu kita include ke nginx.conf



![image](https://user-images.githubusercontent.com/18206510/190461131-cbf16b8d-cd6a-44b4-9a43-c7d07b12ce72.png)


# SETUP BACKEND 


pertama kita lakukan clone dulu terhadap aplikasi docker yg kita akan gunakan dengan perintah 

```
git clone https://github.com/dumbwaysdev/housy-backend
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



![image](https://user-images.githubusercontent.com/18206510/190444930-fa99434c-2c10-4bfd-a0d7-0222a4eb3c6e.png)



lalu cek docker images untuk melihat apakah sudah berhasil



![image](https://user-images.githubusercontent.com/18206510/189699700-67616a2c-2bfa-4171-ac14-34c82370eef3.png)


kita coba jalankan backend kita 



![image](https://user-images.githubusercontent.com/18206510/190547391-426c7d72-b496-4840-b665-a540fde4663d.png)




# sekarang kita coba jalankan aplikasi frontend nya



![image](https://user-images.githubusercontent.com/18206510/190531265-bc4fd7f0-74f8-45e9-b6ba-b7de518e74e1.png)




lalu kita coba register 




![image](https://user-images.githubusercontent.com/18206510/190531420-5fe6657b-a9fc-46d0-80ae-7cd49111f7e8.png)



dan berhasil 



![image](https://user-images.githubusercontent.com/18206510/190531480-384fdb5c-7ad2-425b-b2fe-eab2f17ca4be.png)




lalu kita coba logout kemudian sign in lagi




![image](https://user-images.githubusercontent.com/18206510/190531657-aea0d014-beb7-4621-9d10-3fcad247d903.png)



dan berhasil


![image](https://user-images.githubusercontent.com/18206510/190531585-31bc38a3-5bb4-4dba-9da6-cb62fcf8a43d.png)




# Push Docker images ke DockerHub



jika belum memiliki akun Docker maka silakan register dulu di 


https://www.docker.com/


lalu kemudian login akunnya ke dalam server yang akan kita push lalu masuk dengan perintah 


```docker login```


dan masukkan password dari docker kita


kita ketikan ```docker images``` untuk melihat images yg akan kita push 


lalu masukan 

```
docker tag <image> <user>/<image>
```


untuk melakukan perubahan pada tag image kita



kemudian lakukan push dengan perinta 



```docker push (user)/(nama image)```



![image](https://user-images.githubusercontent.com/18206510/190534534-2868615f-0d67-4d64-bb27-df1b0f160e03.png)



lalu kita cek docker kita




![image](https://user-images.githubusercontent.com/18206510/190534629-e248011d-abe3-4402-bc78-f0dc87220730.png)



dan berhasil 







