University: ITMO University

Faculty: FICT

Course: Introduction to distributed technologies

Year: 2022/2023

Group: K4110c

Author: Azatova Gulshad Jalgas kizi

Lab: Lab4

Date of create: 20.11.2022

Date of finished: 10.12.2022


# Сети связи в Minikube, CNI и CoreDNS



### Создание minikube cluster с 2 нодами и установка CNI=calico plugin
```
minikube start --network-plugin=cni --cni=calico --nodes 2 --kubernetes-version=v1.24.0
```
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab4/img/lab4.1.png"></div><br>  

### Установка label на узлы
```
kubectl label nodes multinode zone=east
node/multinode labeled
kubectl label nodes multinode-m02 zone=west
node/multinode-m02 labeled
```

### Далее необходимо установить calicoctl как модуль кубернетис

```
kubectl apply -f calicoctl.yaml  
``` 
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab4/img/lab4.2.png"></div><br> 

### Создаем манфест ippool, где указываем ip адреса и зоны.

```
kubectl exec -i -n kube-system calicoctl -- /calicoctl create -f - <  C:\distributedTech\kubernetes\ip_pool.yaml 
``` 
В результате успешно создались два ippool-а
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab4/img/lab4.4.png"></div><br> 

Посмотрим более подробно

<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab4/img/lab4.5.png"></div><br> 

### Далее запукаем деплоймент, конфигмап и сервис. Ждем, когда поды будут запущены. 
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab4/img/lab4.6.png"></div><br> 

### Пробрасывем порты и смотрим результат в браузере 
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab4/img/lab4.7.png"></div><br>

## и снова Failure

## Схема
<div align = "center"><img src="https://github.com/ztvgzh/2022_2023-introduction_to_distributed_technologies-k4110c_azatova_g_j/blob/main/lab4/img/scheme.png"></div> 



