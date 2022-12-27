ДЗ день 8

Build custom nginx image

cd kubernetes-monitoring/nginx
docker build . -t nginxhw8 
docker tag nginxhw8 pve.flerken.space:5000/nginxhw8
docker push pve.flerken.space:5000/nginxhw8

Deploy nginx custom image

kubectl apply -f kubernetes-monitoring/nginx/nginx.yaml



LATEST=$(curl -s https://api.github.com/repos/prometheus-operator/prometheus-operator/releases/latest | awk '/tag_name/{print $2}'|tr -d \",)
curl -sL https://github.com/prometheus-operator/prometheus-operator/releases/download/${LATEST}/bundle.yaml | kubectl create -f -