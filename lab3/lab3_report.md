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
1. Создаем деплоймент и конфигмап 
```
kubectl apply -f cm.yaml -f deployment.yaml  
``` 
Просматриваем ConfigMap в Lens:
<div align = "center"><img src=""></div><br> 

Просматриваем значения переменных и делаем проброс портов:
<div align = "center"><img src=""></div><br>

Результат отображается в браузере - перменные удалось успешно передать с помощью конфигмапа:
<div align = "center"><img src=""></div><br>
2. Включаем ingress  
    
```
minikube addons enable ingress   
```

Устанавливаем ingress controller
```
kubectl apply -f https://projectcontour.io/quickstart/contour.yaml
``` 
После чего создаем файл сервиса и ингресса, вносим изменения в деплоймент и выполняем команду:
```
kubectl apply -f cm.yaml -f deploy.yaml -f service.yaml -f ingress.yaml    
``` 
Вносим в hosts minikube ip и доменное имя, которое указано в ингрессе. Выполняем команду:

```
minikube tunnel
```

Проверяем работоспособность нашего ингресса - вводим это доменное имя в браузер и видим, что все работает корректно - наш ингресс смог достучаться до сервиса, а сервис до пода:

<div align = "center"><img src=""></div><br>


 
## Схема
<div align = "center"><img src="https://github.com/maesrto2000/-2022_2023-introduction_to_distributed_technologies-k4113c-ryltsyn_s_a/blob/main/Lr3/img/v1.png"></div> 


