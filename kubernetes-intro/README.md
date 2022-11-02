
Выполнено ДЗ №

Для выполнения домашней работы необходимо создать Dockerfile, в котором будет описан образ: 
- Запускающий web-сервер на порту 8000 (можно использовать любой способ); 
- Отдающий содержимое директории /app внутри контейнера (например, если в директории /app лежит файл homework.html , то при запуске контейнера данный файл должен быть доступен по URL http://localhost:8000/homework.html ); Работающий с UID 1001

 Задание со *

В процессе сделано:

При удалении подов "kubectl delete": kube-proxy - создается заново с помощью контроллера daemonset ( на всех нодах с меткой kubernetes.io/os=linux ) 
coredns - создается заново контроллером replicaset ( который поддеживает 1 реплику ) 
etcd-minikube, kube-apiserver-minikube, kube-controller-manager-minikube, kube-scheduler-minikube - работают из статических манифестов

При удалении контейнеров системой контейнеризации "docker rm", kubelet запускает из заного поддерживая работоспособность контейнеров.

Созданы dockerfile на базе образа httpd, apache.

Создал свой docker registry и залил туда образ 
Образ располагается в репозитории https://pve.flerken.space:5000/web
Создан манифест web-pod.yml.
Для применения манифеста используется команда kubectl apply -f web-pod.yml
Запуск приложения проверяется через проброс порта с использованием port-forward:
kubectl port-forward --address 0.0.0.0 pod/web 8000:8000

Как запустить проект:

kubectl apply -f web-pod.yaml
kubectl port-forward --address 0.0.0.0 pod/web 8000:8000

Как проверить работоспособность:

Перейти по ссылке http://localhost:8080

