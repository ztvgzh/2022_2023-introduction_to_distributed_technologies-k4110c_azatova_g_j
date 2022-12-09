University: ITMO University

Faculty: FICT

Course: Introduction to distributed technologies

Year: 2022/2023

Group: K4110c

Author: Azatova Gulshad Jalgas kizi

Lab: Lab3

Date of create: 20.11.2022

Date of finished: 09.12.2022

# Сертификаты и "секреты" в Minikube, безопасное хранение данных.
## Ход работы 
1. Создаем CongigMap и deployment 
```
kubectl apply -f cm.yaml -f deployment.yaml  
``` 
Просматриваем ConfigMap в Lens:
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img1.png"></div><br> 

Просматриваем значения переменных и делаем проброс портов:
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img2.png"></div><br>
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img3.png"></div><br>

Результат должен был отобразитться в браузере, у меня, к сожалению, не получислось:
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img4.png"></div><br>

Двигаемся дальше:
2. Включаем ingress  
    
```
minikube addons enable ingress   
```
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img6.png"></div><br>
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img5.png"></div><br>

Устанавливаем ingress controller
```
kubectl apply -f https://projectcontour.io/quickstart/contour.yaml
``` 
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img7.png"></div><br>

После чего создаем файл сервиса и ингресса, вносим изменения в деплоймент и выполняем команду:
```
kubectl apply -f cm.yaml -f deploy.yaml -f service.yaml -f ingress.yaml    
``` 
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img8.png"></div><br>

Вносим в hosts minikube ip и доменное имя, которое указано в ингрессе. Выполняем команду:

```
minikube tunnel
```

<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/img9.png"></div><br>


 
## Схема
<div align = "https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab3/img/ingress%20(2).png"></div> 


