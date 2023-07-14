# Домашнее задание к занятию «Установка Kubernetes»

1. Машины c ubuntu для кластера развёрнуты:  
   ![VMs](./pictures/single%20master/VMs.PNG)  
   На kube-master и kube-worker'ы установлен containerd:  
   ![kube-master containerd](./pictures/single%20master/kube-master%20containerd.PNG)  
   ![kube-workers containerd](./pictures/single%20master/kube-workers%20containerd.PNG)  
   Kubernetes кластер инициализирован при помощи kubeadm:  
   ![kubeadm init](./pictures/single%20master/kubeadm%20init.PNG)  
   ![kube-master not ready](./pictures/single%20master/kube-master%20not%20ready.PNG)  
   Kubectl get nodes после применения flannel в качестве cni:  
   ![kube-master ready](./pictures/single%20master/kube-master%20ready.PNG)  
   kube-wroker'ы присоеденены к кластеру при помощи команды из вывода kubeadm init:  
   ![kube-workers joined](./pictures/single%20master/kube-workers%20joined.PNG)  
   Запущенный в поднятом kubernetes под с nginx:  
   ![nginx pod](./pictures/single%20master/nginx%20pod.PNG)

2. Данное задание выполняется на виртуальных машинах личного ПК. В связи с ограниченностью ресурсов все 3 мастера будут выполнять, в том числе, и функции воркеров.  
   Машины с ubuntu развёрнуты:  
   ![VMs](./pictures/multimaster/VMs.PNG)  
   Конфигурационные файлы KeepAlived:  
   [kube-master1-keepalived.conf](./files/kube-master1-keepalived.conf)  
   [kube-master2-keepalived.conf](./files/kube-master2-keepalived.conf)  
   [kube-master3-keepalived.conf](./files/kube-master3-keepalived.conf)  
   KeepAlived запущен:  
   ![keepalived Virtual IP](./pictures/multimaster/keepalived%20Virtual%20IP.PNG)  
   Файлы сервиса ETCD:  
   [kube-master1-etcd.service](./files/kube-master1-etcd.service)  
   [kube-master2-etcd.service](./files/kube-master2-etcd.service)  
   [kube-master3-etcd.service](./files/kube-master3-etcd.service)  
   Запущенный ETCD кластер:  
   ![ETCD](./pictures/multimaster/ETCD.PNG)  
   На все машины установле containerd:  
   ![containerd](./pictures/multimaster/containerd.PNG)  
   Конфигурационный файл инициализации Kubernetes кластера:  
   [config.yaml](./files/config.yaml)  
   Первая нода инициализирована:  
   ![kube-master1 initialized](./pictures/multimaster/kube-master1%20initialized.PNG)  
   ![kubectl get nodes](./pictures/multimaster/kubectl%20get%20nodes.PNG)  
   Оставшиеся две ноды также успешно присоеденены к кластеру:  
   ![kube-master2-3 initialized](./pictures/multimaster/kube-master2-3%20initialized.PNG)  
   ![kubectl get nodes 2](./pictures/multimaster/kubectl%20get%20nodes%202.PNG)  
   Kubectl get nodes после применения flannel в качестве cni:  
   ![kubectl get nodes 3](./pictures/multimaster/kubectl%20get%20nodes%203.PNG)  
   Запущенный в поднятом kubernetes под с nginx:  
   ![nginx](./pictures/multimaster/nginx.PNG)