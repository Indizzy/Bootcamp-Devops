# Cloud Computing 

Cloud komputing atau komputasi awan simplenya adalah proses penyimpanan server kita di internet agar tidak membebani penyimpanan lokal

contoh di sini saya menggunakan IDCH (ID Cloud host) 


pertama masuk ke ``` IDcloudhost.com ``` lalu buat console acccount karena kita akan membuat server 



![image](https://user-images.githubusercontent.com/18206510/204974031-e9bfc605-c0a8-4531-b58f-2f8dd5bbe475.png)



pada menu compute pilih : 

- virtual machine
- ubuntu 20.04 lts
- location bebas
- size tergantung kebutuhan 

sisanya diisi bebas terserah kita


![image](https://user-images.githubusercontent.com/18206510/204973731-39376ce0-3b1e-4710-9c0e-9d09dd1bf579.png)


klik create lalu tunggu



lalu kita buat satu server lagi sebagai gateaway server



![image](https://user-images.githubusercontent.com/18206510/205004712-c39a281b-a96c-48a0-bdf8-2bfd6117f6f9.png)



# Koneksi ke server IDCH dengan menggunakan SSH 


![image](https://user-images.githubusercontent.com/18206510/205010218-89083b0d-4926-441f-84c8-9719df6c4462.png)


di sini masih pake password, kita set supaya tidak pakai password



kita buatkan tempat di server yang ingin kita remote di sini saya namai secret



![image](https://user-images.githubusercontent.com/18206510/205019867-f33a7312-4257-463c-b277-4d6228d66ff7.png)



copy id_rsa.pub dari lokal ke server tujuan 



![image](https://user-images.githubusercontent.com/18206510/205020275-12c3c6d1-1ade-4335-9577-a6c884db3eb2.png)



lalu copy isinya ke dalam authorized key pada direktori .ssh



![image](https://user-images.githubusercontent.com/18206510/205020770-1dc7a798-2ad4-481a-a6eb-9c233187b2bd.png)


paste dan simpan


![image](https://user-images.githubusercontent.com/18206510/205021237-a77096db-323b-46a4-ac41-cac5857b9739.png)



dan sudah bisa diakses tanpa password



![image](https://user-images.githubusercontent.com/18206510/205021501-0f74a0e7-d04b-4d2a-aa49-cafd340bb479.png)




# Deploy aplikasi menggunakan database MYSQL



- install node.js


![image](https://user-images.githubusercontent.com/18206510/205023405-746a66b6-252f-47a6-b0a4-54ab6c8c14a7.png)



- cloning app



![image](https://user-images.githubusercontent.com/18206510/205024552-8b16c559-d533-4bb7-9996-cb601f180118.png)



# Setup frontend



- install npm 



![image](https://user-images.githubusercontent.com/18206510/205025480-b874f2d5-4266-4987-84d6-0d164e9e415f.png)



- install pm2 



![image](https://user-images.githubusercontent.com/18206510/205026309-ef0feee2-cc69-4086-aa43-92f3f16a563d.png)


jalankan command ``` pm2 init simple ```  untuk membuat script ecosystem file 



![image](https://user-images.githubusercontent.com/18206510/205026845-750edc5a-ad38-4f96-9931-074474f1a972.png)



edit script menjadi ```npm start```


![image](https://user-images.githubusercontent.com/18206510/205027171-9cd8aa83-df38-4501-b6f4-33d4fc2fbeb8.png)



coba jalankan script 


pm2 start ecosystemfile.config.js



![image](https://user-images.githubusercontent.com/18206510/205027403-b7f56cf6-ac17-4067-bbd8-451f41f527bc.png)



coba jalankan di browser dengan port 3000



![image](https://user-images.githubusercontent.com/18206510/205027987-6df5ead9-fcc2-4379-ad07-2eecf55034d1.png)



- Buat DNS di cloudflare


pada bilah kiri klik DNS kemudian add record 



![image](https://user-images.githubusercontent.com/18206510/205029566-82ee8ef7-af61-4c93-97fa-d84fff4822e1.png)


lalu save



![image](https://user-images.githubusercontent.com/18206510/205029885-a9d69afa-3526-4ad3-a146-61bdd10dc564.png)



- install nginx pada server gateaway



![image](https://user-images.githubusercontent.com/18206510/205030442-2b416656-acbc-43e3-bbd8-cb3e0fe2311d.png)



buat reverse proxy file pada ```etc/nginx/sites-enabled```


![image](https://user-images.githubusercontent.com/18206510/205034951-e821c9b6-1116-4b3e-96d1-31e7dfe62d2d.png)




cek config ``` sudo nginx -t```



![image](https://user-images.githubusercontent.com/18206510/205033298-cb249795-1546-4115-8866-0e90e0355194.png)



reload nginx 


![image](https://user-images.githubusercontent.com/18206510/205033563-e3d9e0cc-6658-4c73-9f7f-c3c12199dbca.png)



cek pada browser



![image](https://user-images.githubusercontent.com/18206510/205034824-0e1d7fb2-0447-4c4e-b935-d82215f79cb7.png)




# Setup Backend dan database


- Installasi mysql 



``` sudo apt install mysql-server```



![image](https://user-images.githubusercontent.com/18206510/205055552-d063b63f-95e9-4a20-b10e-ac56797b4a8d.png)



setup agar bisa diakses dengan user root



![image](https://user-images.githubusercontent.com/18206510/205057582-ade91322-8051-4110-bcd4-1a64c53ae817.png)



lalu kita lakukan secure installation agar database kita terinstall secara aman 



dengan command ```mysql_secure_installation```



![image](https://user-images.githubusercontent.com/18206510/205058534-314bdbb1-7feb-4f39-bbec-c3c7c6edc8b2.png)



dan sekarang kita sudah bisa mengaksesnya dengan user root


![image](https://user-images.githubusercontent.com/18206510/205058773-505a9d55-a5bf-49e8-8807-f2cd5580e065.png)



selanjutnya membuat user dan pass untuk database kita



![image](https://user-images.githubusercontent.com/18206510/205060451-7736f28b-9951-4950-9c31-c2ca9efa15fb.png)




disana perintah ``` GRANT ALL PRIVILEGES ON *.* TO 'awan'@'%'; ``` berguna untuk memberi akses pada user awan terhadap database kita


coba masuk 


![image](https://user-images.githubusercontent.com/18206510/205061152-e2992a85-730f-4ebe-9974-1881eac2e4ba.png)



buat database



![image](https://user-images.githubusercontent.com/18206510/205061770-cf349e5d-a62a-4f25-a206-a9ced753657e.png)





- lakukan migrasi database 



masuk ke ``` dumbflix-backend``` lalu ganti ```config.json``` sesuai dengan database yang kita buat




![image](https://user-images.githubusercontent.com/18206510/205062998-88b9ca87-1e7e-489b-b75b-8686877c4952.png)



- install sequelize untuk setup database



![image](https://user-images.githubusercontent.com/18206510/205067921-bc81ea1c-26f1-439b-92b0-2bc00ff4a47f.png)



lalu masukkan perintah ```npx sequelize-cli db:create```



kemudian ```npx sequelize-cli db:migrate```




![image](https://user-images.githubusercontent.com/18206510/205079242-14f0a93b-d95f-4705-890c-225114451ea6.png)



- setup backend




instal pm2 pada backend seperti pada frontend lalu ganti ```ecosystem file``` dengan npm start seperti pada frontend kemudian jalankan




![image](https://user-images.githubusercontent.com/18206510/205066396-5a39e4a0-781d-493c-bfb1-5c53c45c5eef.png)



coba jalankan di browser



![image](https://user-images.githubusercontent.com/18206510/205084814-6240d50d-187a-4b76-a1e3-4b6d8088f57c.png)



- buat dns untuk backend



![image](https://user-images.githubusercontent.com/18206510/205085221-51d62bc8-7b68-4d90-b96e-6a4aa0f4e3d3.png)



 - reverse proxy backend



![image](https://user-images.githubusercontent.com/18206510/205087910-a753f247-d6bf-4ec7-bbea-6587d5cd7405.png)



# hubungkan FE dan BE 



edit base url pada file ```/src/config/api.js``` pada frontend sesuai domain backend kita




![image](https://user-images.githubusercontent.com/18206510/205089159-b333d8ff-77a2-4900-8ef3-7a9417cd7c10.png)







# install certbot















