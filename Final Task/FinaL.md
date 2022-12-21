# Cloud Computing


- Setup 3 VMs with the following specs
     Appserver - 2 vCPU, 2GB RAM
     Gateway - 1 vCPU, 1GB RAM
     Monitoring - 2 vCPU, 2GB RAM
     
- 20 GB storage

-User login without password authentication
-Remove password login method
-All servers are **not allowed** to use *Public IP* (except Gateway)





- Create server



![image](https://user-images.githubusercontent.com/18206510/208793790-da7ae01e-f5d7-4d53-a398-70bd0b56cd62.png)




# set ssh 



generate ssh ke dalam file yg kita inginkan untuk meletakkan ssh




![image](https://user-images.githubusercontent.com/18206510/208817705-ea4e73ab-cb61-4d1d-8c06-6e63edbec521.png)





msukkan id_rsa.pub ke dalam authorized keys




![image](https://user-images.githubusercontent.com/18206510/208817895-f5fcf1e6-fb19-450f-a94c-1ed4342e8d09.png)




buat file untuk configurasi agar bisa masuk menggunakan alias



![image](https://user-images.githubusercontent.com/18206510/208815902-ca5fa728-ea94-4fae-938d-d9a63c583f25.png)




kirim isi file ``` .ssh ``` ke semua server 



buat file daftar server yg ingin dituju



![image](https://user-images.githubusercontent.com/18206510/208809607-cd64341b-cede-43b0-bb3f-bb974e3074a7.png)



kemudian jalankan perintah ``` scp -r (file) (user@ipuser) (lokasi) ```




![image](https://user-images.githubusercontent.com/18206510/208819611-b27d2b40-5e41-4667-8fa6-df8c9bbe3366.png)



coba masuk dengan ip



app server


![image](https://user-images.githubusercontent.com/18206510/208823336-458be5a7-ebde-4557-85f4-d12d5129b412.png)



gate server


![image](https://user-images.githubusercontent.com/18206510/208823466-0a394910-6b2d-4b06-a358-f39228c3ccb2.png)


 monitor server
 
 
![image](https://user-images.githubusercontent.com/18206510/208823596-5467fd36-9ba5-4ca3-b07b-662edca7b4d9.png)




coba masuk dengan user



# Repo




login github 


cek akun yg tersimpan dengan ```git config --list```


untuk masuk gunakan


``` git config --global user.name "user github" ```
``` git config --global user.email "email github" ```



![image](https://user-images.githubusercontent.com/18206510/208828801-b504c365-e530-4e3f-b581-89cd16258981.png)



kemudian copy ssh public ke dalam sttings/ssh and gpg keys pada github




![image](https://user-images.githubusercontent.com/18206510/208829013-0e738e0d-6c14-4b15-8bcc-7d6cd6cdb997.png)




![image](https://user-images.githubusercontent.com/18206510/208829095-8eb8ec2e-729a-44f2-8ddd-11e058de69aa.png)



di sini saya sudah masuk



![image](https://user-images.githubusercontent.com/18206510/208830014-800272f7-e161-49d2-b4fc-d16334969df3.png)




- Create repo 



fork file yang kita inginkan dengan masuk ke repositorinya lalu pada kanan atas klik fork



![image](https://user-images.githubusercontent.com/18206510/208827996-864ea570-9095-4a77-b804-6597b0115ea7.png)



bisa ganti namanya jika ingin diganti lalu klik create fork 



![image](https://user-images.githubusercontent.com/18206510/208828144-ce60db54-b399-414b-9cab-dc58ebdb9d0f.png)



- clone repo



masuk ke repo yg akan kita clone klik pada ```code``` lalu copy link SSH 



![image](https://user-images.githubusercontent.com/18206510/208830272-024ad0d4-ef1a-4545-bdb3-1a1acc548071.png)



lalu gunakan perintah git clone (link tadi) jalankan 


frontend


![image](https://user-images.githubusercontent.com/18206510/208837395-994e6b62-0da8-4424-8ef7-bbc913c79664.png)



backend



![image](https://user-images.githubusercontent.com/18206510/208837334-5e3a280c-f7c4-4a77-9b2a-d3514546ca8d.png)




- buat branches Development, staging, production



frontend

![image](https://user-images.githubusercontent.com/18206510/208837564-aac60e9d-4376-4dc4-a981-954e10f75ce0.png)


back end 



![image](https://user-images.githubusercontent.com/18206510/208837922-6ca14a5d-aaf7-4ea8-9e78-514ba7ce3780.png)



cek branches dengan git branch -a



- set repo ke private



# Deployment


- install docker 


buat configurasi untuk installasi docker



![image](https://user-images.githubusercontent.com/18206510/208956696-70636e01-f79e-413a-9ae1-fd6270add0fe.png)



jalankan 



![image](https://user-images.githubusercontent.com/18206510/208956836-2c10f540-db7c-47c3-b3c3-8d9241957e40.png)



cek 



![image](https://user-images.githubusercontent.com/18206510/208957845-ef984365-ee3e-4064-a99a-be136aebca5d.png)



login docker



![image](https://user-images.githubusercontent.com/18206510/208958657-49f6de7d-cde3-4cf6-8c93-ae09d1ea5955.png)
















