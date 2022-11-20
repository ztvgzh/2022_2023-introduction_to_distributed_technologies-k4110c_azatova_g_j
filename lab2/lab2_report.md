University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4110c

Author: Azatova Gulshad Jalgas kizi

Lab: Lab2

Date of create: 04.10.2022
Date of finished: 19.11.2022

# Развертывание веб сервиса в Minikube, доступ к веб интерфейсу сервиса. Мониторинг сервиса.  
## Ход работы 
1. Создаем файлы деплоймента (указываем количество реплик) и сервиса. 
```
kubectl apply -f deployment.yaml
```  
```
kubectl apply -f service.yaml
``` 
2. Просматриваем созданные сервисы  
```
kubectl get services
```  
3. Делаем пробрас портов и подключаемся к контейнерам через браузер    
 ```
kubectl port-forward svc/indfr-service 80:80
```   
Можем увидеть значения наших переменных в браузере и посмотреть подробную информацию о репликах в Lens. Название контейнера состоит из деплоймента, хэш реплики сет, случайно сгенерированные символы, чтобы различать поды между друг другом. 
## Схема
<div align = "center"><img src="https://"></div> 






