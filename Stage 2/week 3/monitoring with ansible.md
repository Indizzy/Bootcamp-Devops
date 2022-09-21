# Ansible 

# Apa itu ansible?

Ansible merupakan salah satu automation tool dan infrastructure as a code yang tersedia secara open source. Dengan Ansible kita dapat melakukan


provisioning (semacam membuat/menghapus) server, configuration management, dan melakukan deployment aplikasi pada server.


Pertama sebelum melakukan installasi ansible di sini saya akan membuat sebuah server yang nantinya akan kita monitoring dengan ketentuan sebagai berikut :


![image](https://user-images.githubusercontent.com/18206510/191458473-edb07fe3-80a1-43e9-9e52-6ab47d61e30d.png)



``` 1 cpu, 2GB memory, 20GB Disk```



# Installasi Ansible


untuk menginstall ansible kita bisa menggunakan perintah berikut 

```
sudo apt-get update


sudo apt-get install software-properties-common


sudo apt-add-repository ppa:ansible/ansible


sudo apt-get update


sudo apt-get install ansible
```



![image](https://user-images.githubusercontent.com/18206510/191466819-236305c9-7968-4415-a970-9b7ac37eb4b5.png)



tunggu prosesnya hingga selesai


kemudian untuk mengeceknya bisa gunakan perintah

```
ansible --version
```


![image](https://user-images.githubusercontent.com/18206510/191467812-11306e1f-d075-45cd-890a-65fd2ea83e65.png)



kemudian di sini saya akan membuat sebuah file direktori dengan nama ansible untuk menyimpan file-file setup untuk monitoring server


![image](https://user-images.githubusercontent.com/18206510/191469804-dc218e63-8c3a-44d5-8746-ca4665f1033d.png)


- setup ssh 


kemudian di sini kita lakukan setup ssh agar lebih mudah memanage server kita


![image](https://user-images.githubusercontent.com/18206510/191475112-541490c4-e8d9-4c34-ab56-d0d0cc071b3f.png)



ssh private tadi kemudian kita buatkan file baru dengan nama sshkey.pem di dalam folder ansible pada lokal kita lalu mempaste isinya 



![image](https://user-images.githubusercontent.com/18206510/191475824-77b0c4ef-0c08-4c05-b1d4-afae6c77a254.png)



simpan kemudian lakukan pengetesan

sebelumnya kita modifikasi dulu filenya agar hanya bisa diread dengan perintah 


```chmod 400 sshkey.pem```  


lalu kita tes dengan perintah 


```ssh -i sshkey.pem awan@103.176.78.216```


![image](https://user-images.githubusercontent.com/18206510/191477068-760412c4-d3b7-4274-84a8-9a8fafe49919.png)



- melakukan setup pada ansible


pertama kita buat file dengan nama inventory lalu kita isikan file yang ingin kita monitor


![image](https://user-images.githubusercontent.com/18206510/191508221-a74f4c97-9a10-4b95-a638-d683de09baa0.png)



lalu kita buat lagi file dengan nama ansible.cfg lalu isikan seperti berikut



![image](https://user-images.githubusercontent.com/18206510/191510152-6194c861-a3bd-4fd2-82e0-be96be57d3b6.png)



kemudian simpan filenya lalu kita cek koneksi ke server tujuan kita dengan perintah 


```ansible all -m ping```


![image](https://user-images.githubusercontent.com/18206510/191510912-d314e4f7-2974-4051-8a70-86659a8f30f2.png)



di sini terlihat sudah berhasil


- Installasi Nginx 


pertama buat file dengan nama nginx.yaml lalu masukan script berikut



![image](https://user-images.githubusercontent.com/18206510/191518943-08715748-b452-4a6a-86a2-452e753d4791.png)



lalu kita check syntax yang sudah kita buat dengan perintah 



```ansible-playbook --syntax-check nginx.yaml```


![image](https://user-images.githubusercontent.com/18206510/191519098-fd1936b3-a52e-4904-8e4f-90232beacc5e.png)



kemudian kita coba install nginx-nya dengan perintah 


```ansible-playbook nginx.yaml```


![image](https://user-images.githubusercontent.com/18206510/191519896-8e7782e1-ecde-44ef-a1a2-83692783fa5f.png)



lalu kita coba cek melalui browser kita :



![image](https://user-images.githubusercontent.com/18206510/191520320-26c6bf13-3a55-4326-9195-85d75d648243.png)



- membuat user dengan ansible


pertama kita install whois untuk melakukan enkripsi pada password kita dengan perintah 


```sudo apt install whois```


![image](https://user-images.githubusercontent.com/18206510/191528822-ce71baaf-5c2a-4d3a-9169-4f268065ad6e.png)


kemudian masukan perintah ```mkpasswd --method=sha-512``` lalu masukan password yang kita inginkan



kemudian buat file .yaml untuk tempat usernya lalu pastekan password yg sudah terenkripsi tadi 



![image](https://user-images.githubusercontent.com/18206510/191540793-c03ef3b4-8be0-4a0d-97eb-d5cb0e2c871f.png)



kemudian kita coba cek, jika berhasil baru kita jalankan 



![image](https://user-images.githubusercontent.com/18206510/191541143-41c29e72-76f8-49bf-88fe-34d28f706245.png)



kemudian kita coba masuk dengan user baru kita



![image](https://user-images.githubusercontent.com/18206510/191554222-d1082096-194e-45e3-a305-679b0ae26f63.png)




- installasi docker

















