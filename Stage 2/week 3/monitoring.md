# monitoring server 


# installing node exporter, prometheus, and grafana




- INSTALL DOCKER 


buat script 


```
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
    
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg


echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  
  
  
sudo chmod a+r /etc/apt/keyrings/docker.gpg

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

```


![image](https://user-images.githubusercontent.com/18206510/207070571-8ce4324f-8993-465d-9111-35e1d6c57f90.png)


jalankan 




![image](https://user-images.githubusercontent.com/18206510/207070963-f370036b-04a9-407c-80e2-e5f3064fa370.png)





jika sudah cek apakah sudah terinstall atau belum




![image](https://user-images.githubusercontent.com/18206510/207071607-c27d2f6f-09b4-49de-8538-797e9940b7a3.png)




- Buat docker compose untuk install node, prometheus, grafana 

```
version: '3.7'
services: 
    node:
     image: bitnami/node-exporter
     container_name: node-exporter
     stdin_open: true
     ports:
      - 9100:9100

    promet:
     image: bitnami/prometheus
     container_name: prometheus
     stdin_open: true 
     ports:
      - 9090:9090

    grafa:
     image: grafana/grafana  
     container_name: grafana
     stdin_open: true
     ports:
      - 3000:3000

```


jalankan 




![image](https://user-images.githubusercontent.com/18206510/207075516-6bee20f1-ae49-409d-b2fe-87e075c1144a.png)



cek container 



![image](https://user-images.githubusercontent.com/18206510/207078945-c04468af-ce5d-4b3a-8091-d4091d3e0dd9.png)




cek pada browser



NODE EXPORTER 



![image](https://user-images.githubusercontent.com/18206510/207079150-deab1f62-17ab-42ce-9a39-b8bc49c66278.png)



PROMETHEUS


![image](https://user-images.githubusercontent.com/18206510/207079481-3109c132-4180-42ad-81b9-515468f684dc.png)



GRAFANA


![image](https://user-images.githubusercontent.com/18206510/207080114-b6ea138d-f242-4679-9cf7-9a2bb5ae56db.png)



masuk dengan user admin pass admin nanti akan diminta ganti yang baru




![image](https://user-images.githubusercontent.com/18206510/207080506-2df17a88-9fd1-4c45-890d-9cb26f951e8c.png)



tambahkan sumber data prometheus kita agar bisa di baca grafana


pilih prometheus


![image](https://user-images.githubusercontent.com/18206510/207083562-82017a4b-21e5-4d2c-b88a-52059bc6a91b.png)



isi sesuai kebutuhan



![image](https://user-images.githubusercontent.com/18206510/207084035-d6655a76-7df1-479c-95a4-5d65e16ea7d5.png)




klik save and test 



![image](https://user-images.githubusercontent.com/18206510/207084369-72a14570-5f0a-472f-8737-96bd11ee6571.png)



buat prometheus.yml untuk pointing server mana saja yang akan kita pantau




![image](https://user-images.githubusercontent.com/18206510/207093791-fc205bd3-a1a4-4617-b910-5127420b5c44.png)




balik ke grafana run queries CPU buat mantau cpu




![image](https://user-images.githubusercontent.com/18206510/207097350-6dfce2e0-9dd5-41e2-8aa6-b282eb1759ba.png)




Memory buat mantau memory 





![image](https://user-images.githubusercontent.com/18206510/207100797-0a6d4ab9-5df9-47b2-ab75-f5914e225663.png)





Tampilan dashboard




![image](https://user-images.githubusercontent.com/18206510/207101246-e63b4d30-fad1-420f-8447-7b74832cea0e.png)




- Reverse proxy 











