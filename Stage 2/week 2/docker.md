# Docker 


Docker adalah aplikasi untuk menyatukan berbagai file software dan pendukungnya dalam sebuah wadah (container) agar memudahkan proses pengembangan software.

- Fungsi Docker

1. Mempermudah Pengembangan Aplikasi
2. Menyederhanakan Konfigurasi
3. Memudahkan Pengembangan Kode Pipeline
4. Bisa Digunakan untuk Debugging
5. Mendukung Multitenancy
6. Meningkatkan Sumber Daya dengan Cepat



# setup frontend 


- cloning app


![image](https://user-images.githubusercontent.com/18206510/205825447-197cc834-32b9-4c7e-8351-86f0b3b6bd5a.png)



masuk ke frontend edit file api.js arahkan ke backend



![image](https://user-images.githubusercontent.com/18206510/205826330-d0484313-4064-409f-80e4-fd819e1535ed.png)



buat Dockerfile untuk intsall node




![image](https://user-images.githubusercontent.com/18206510/205835155-5e27a4ff-0fe8-4f08-9cd2-785b5bee825e.png)







# installasi nginx


- masuk ke server gateaway



![image](https://user-images.githubusercontent.com/18206510/205839170-906d5afb-571b-41d7-987c-4cf7c5bd0f6b.png)




- Buat file untuk reverse proxy


Frontend

![image](https://user-images.githubusercontent.com/18206510/205840563-1b4b392b-5a42-4afb-9935-49255c5bc26b.png)


Backend

![image](https://user-images.githubusercontent.com/18206510/205840714-40626304-1ba2-4955-a5ac-b6f79186d66a.png)


include direktori tadi dalam nginx.conf






