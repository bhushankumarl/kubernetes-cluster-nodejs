# kubernetes-cluster-nodejs

### Tagging the Repos
docker tag node-server bhushankumar3/kubernetes-cluster-nodejs
docker push bhushankumar3/kubernetes-cluster-nodejs:latest

### Delete the deployment
kubectl delete -f kuberbets-deploy.yaml

### Create the deployment
kubectl create -f kuberbets-deploy.yaml

## Deploy and POD Details
kubectl get deploy,po

### Get the Minicube IP
minikube ip

### Create a IP Config 
kubectl create -f minicube-ip-config.yaml

### Remove a IP Config 
kubectl delete -f minicube-ip-config.yaml

## Get configs
kubectl get configmaps metallb-system -o yaml

### Remove Load Balancer
kubectl delete svc nodejs-deployment

### Expose Load Balancer
kubectl expose deployment nodejs-deployment --type="LoadBalancer"

### Get Details
kubectl get svc
