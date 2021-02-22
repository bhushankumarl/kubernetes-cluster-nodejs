# kubernetes-cluster-nodejs

### Tagging the Repos
docker tag node-server bhushankumar3/kubernetes-cluster-nodejs
docker push bhushankumar3/kubernetes-cluster-nodejs:latest

## Deploy and POD Details
kubectl get deploy,po,svc

### Remove the deployment
kubectl delete -f kuberbets-deploy.yaml

### Create the deployment
kubectl create -f kuberbets-deploy.yaml

## Deploy and POD Details
kubectl get deploy,po,svc

### Get the Minicube IP
minikube ip
#192.168.49.2

### Install MetaLab
kubectl apply -f https://raw.githubusercontent.com/google/metallb/v0.9.3/manifests/namespace.yaml
kubectl apply -f https://raw.githubusercontent.com/google/metallb/v0.9.3/manifests/metallb.yaml # On the first install only
kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)"

### Remove a IP Config 
kubectl delete -f minicube-ip-config.yaml

### Create a IP Config 
kubectl create -f minicube-ip-config.yaml

### Remove Load Balancer
kubectl delete svc nodejs-deployment

### Expose Load Balancer
kubectl expose deployment nodejs-deployment --type="LoadBalancer"

### Get Details
kubectl get deploy,po,svc

### Get the PORT Details
minikube service nodejs-deployment

### Sample Docker
docker run -d --publish 3000:3000 bhushankumar3/kubernetes-cluster-nodejs:latest

### Patch Service
kubectl patch svc nodejs-deployment -n default -p '{"spec": {"externalIPs":["192.168.49.1"]}}'
kubectl patch svc kubernetes -n default -p '{"spec": {"externalIPs":["192.168.49.1"]}}'

kubectl patch svc kubernetes -n default -p '{"spec": {"externalIPs":["188.34.205.172"]}}'
kubectl patch svc nodejs-deployment -n default -p '{"spec": {"externalIPs":["188.34.205.172"]}}'

curl 192.168.49.1:3000

kubectl get pod nodejs-deployment-76b74655b6-2vqrb --template='{{(index (index .spec.containers 0).ports 0).containerPort}}{{"\n"}}'

kubectl port-forward nodejs-deployment-76b74655b6-2vqrb 80:80
