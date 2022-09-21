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
















