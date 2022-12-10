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



### создание minikube cluster с 2 нодами aи установка CNI=calico plugin
```
minikube start --network-plugin=cni --cni=calico --nodes 2 --kubernetes-version=v1.24.0
```

### Схема
