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


buat file docker.yaml lalu masukan script berikut



![image](https://user-images.githubusercontent.com/18206510/191559153-31374c5f-12b9-4ded-9dfb-1b542b7a607c.png)



kita cek apakah ada salah pada syntax-nya, lalu kita jalankan



![image](https://user-images.githubusercontent.com/18206510/191624723-9b94a7b6-4990-43a7-bd54-f7bbf505b209.png)



lalu kita jalankan script tadi 



![image](https://user-images.githubusercontent.com/18206510/191625517-a3516780-d29b-49f1-8a9d-da181e25efed.png)



kemudian kita cek 



![image](https://user-images.githubusercontent.com/18206510/191627787-acab953a-455c-4656-a8d4-27642f12adef.png)



# Installasi node exporter, prometheus, grafana


- installasi node exporter


kita buat file dengan nama node-exporter.yaml lalu isi dengan setup berikut:


![image](https://user-images.githubusercontent.com/18206510/191650565-e2a4d8fd-fe04-4c96-b097-9adbe1a4f9a0.png)



lalu kita check apakah ada error, jika sudah maka tinggal kita jalankan



![image](https://user-images.githubusercontent.com/18206510/191630132-bef0b4b5-7f4b-4a74-a6b8-aaba42e66d14.png)



lalu kita check di browser apakah sudah berjalan dengan memasukkan ip dan port 9100



![image](https://user-images.githubusercontent.com/18206510/191630395-d1f6c244-2b86-45be-b4ff-44df1c36aaad.png)



selanjutnya kita buat direktori dengan nama files untuk menyimpan konfigurasi monitoring server kita


di sini saya akan membuat files dengan nama:

-node_exporter.service
-prometheus.yaml (untuk melakukan targeting terhadap server yang akan dimonitor)
-prometheus.service


di dalam node_exporter.service kita isikan:


![image](https://user-images.githubusercontent.com/18206510/191631319-f4269c52-80b8-45fa-97b6-60e2738603bf.png)


kemudian di dalam prometheus.service kita isikan:



![image](https://user-images.githubusercontent.com/18206510/191631423-9d06be0d-263e-4420-9537-f1d5440099d1.png)



di bagian prometheus.yaml kita isikan:



![image](https://user-images.githubusercontent.com/18206510/191650662-2586c59e-7bdf-48c7-8afc-e8178ffce9d7.png)




- installasi prometheus dan grafana



buat file dengan nama monitor.yaml lalu isikan script berikut:



![image](https://user-images.githubusercontent.com/18206510/191650802-2ff91247-e5db-41c9-903d-9b099949cdae.png)



lalu kita cek, jika tidak ada error lalu jalankan



![image](https://user-images.githubusercontent.com/18206510/191639042-c8b7b634-e421-44eb-838a-a713f11e399d.png)



kemudian kita cek pada browser



![image](https://user-images.githubusercontent.com/18206510/191639245-151ba26f-254d-4ed8-942c-27ecbf8d55c9.png)



konfigurasi yang kita buat tadi



![image](https://user-images.githubusercontent.com/18206510/191639672-923c610b-6790-4d86-a483-e9b7d7dddb36.png)


runtime aplikasi


![image](https://user-images.githubusercontent.com/18206510/191639775-049664d1-228f-4616-94ee-fffdfb84ec72.png)


targets


![image](https://user-images.githubusercontent.com/18206510/191639934-0c781e75-7bb2-494f-82a4-86e2d873de3d.png)



sekarang kita coba masuk pada grafana



di sini tinggal masuk dengan admin-admin



![image](https://user-images.githubusercontent.com/18206510/191640731-ef7e72f2-68a7-4d65-91aa-ec2d569ed89b.png)



kemudian masukan password baru



![image](https://user-images.githubusercontent.com/18206510/191640824-6c4b0d1c-6249-471d-b4d2-3752da95920a.png)



pada bilik kiri pilih konfiguration lalu data source kemudian add data source



![image](https://user-images.githubusercontent.com/18206510/191641433-e9ce4bad-11a6-4214-852e-66390b05c1c9.png)



pilih prometheus


![image](https://user-images.githubusercontent.com/18206510/191641596-36f12a98-e406-46a6-8a6e-73a980d40c17.png)



klik save & test 















