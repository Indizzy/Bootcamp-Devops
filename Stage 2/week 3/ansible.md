# Ansible 




Ansible merupakan salah satu automation tool dan infrastructure as a code yang tersedia secara open source. Dengan Ansible kita dapat melakukan provisioning


(semacam membuat/menghapus) server, configuration management, dan melakukan deployment aplikasi pada server.





- Installasi ansible




install pip dari python3 agar bisa install ansible



![image](https://user-images.githubusercontent.com/18206510/207551165-a34581ba-fdf5-4698-a239-d5296866ca34.png)



cek pip


![image](https://user-images.githubusercontent.com/18206510/207552544-736a45f1-681d-48ec-86a2-6571d2d3993a.png)



install ansible 



![image](https://user-images.githubusercontent.com/18206510/207553233-012bcdf5-0fa5-42d6-8c3a-c5281f9397d7.png)



disini saya sudah ada 


buat file inventory berisi server tujuan 



![image](https://user-images.githubusercontent.com/18206510/207586452-5579e7e0-25f0-488a-8848-ea0f49185973.png)


coba ping server


![image](https://user-images.githubusercontent.com/18206510/207586378-01027c1c-a0d6-4e66-b4af-f68c63e0bc83.png)



- ganti user 


buat password terenkripsi dengan whois



![image](https://user-images.githubusercontent.com/18206510/207587641-cb9d75b2-9552-46f8-ac73-9203ece5d0b0.png)




buat file user.yml



![image](https://user-images.githubusercontent.com/18206510/207592669-7b0f8de0-12c1-44ff-95de-d6ec4a754920.png)



jalankan 



![image](https://user-images.githubusercontent.com/18206510/207592941-b3d0e9ec-f179-4f2c-9cd3-e5e65469aaef.png)



coba masuk dengan user baru



![image](https://user-images.githubusercontent.com/18206510/207593745-935c3737-af08-40fb-b34d-9957ea4d8c94.png)




- Install docker using ansible


buat docker.yml 



![image](https://user-images.githubusercontent.com/18206510/207615569-b369639f-f06e-4aa2-a1dc-58e48d259120.png)


jalankan



![image](https://user-images.githubusercontent.com/18206510/207615118-f2280795-d131-4b1c-93aa-0d0924bc552e.png)



cek



![image](https://user-images.githubusercontent.com/18206510/207616464-30e4b18b-33e7-46ce-b4ce-b76ba8b46043.png)




- Installasi node exporter (semua server), prometheus, grafana (pada server monitoring)
























