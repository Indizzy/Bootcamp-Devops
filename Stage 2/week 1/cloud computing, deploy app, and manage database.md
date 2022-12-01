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



install node.js








