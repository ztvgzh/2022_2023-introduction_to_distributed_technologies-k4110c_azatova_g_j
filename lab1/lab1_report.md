University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4110c

Author: Azatova Gulshad Jalgas kizi

Lab: Lab1

Date of create: 04.10.2022

Date of finished: 19.11.2022

# Создание манифеста  
## Ход работы 
1. Создаем файл манифеста, где указываем образ `vault`  
2. Создаем под с помощью команды 
```
kubectl apply -f pod.yml
```  
3. Проверяем статус пода  
 ```
kubectl get pods
```   
4. Создаем сервис 
 ```
minikube kubectl -- expose pod vault --type=NodePort --port=8200
```
5. Прокидываем порт для доступа к сервису 
 ```
minikube kubectl -- port-forward service/vault 8200:8200
```

# Схема 1
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab1/img/scheme1.png"></div> 
# Схема 2
<div align = "center"><img src=""></div> 


