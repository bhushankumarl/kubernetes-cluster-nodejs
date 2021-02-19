# kubernetes-cluster-nodejs

### Tagging the Repos
docker tag node-server bhushankumar3/kubernetes-cluster-nodejs
docker push bhushankumar3/kubernetes-cluster-nodejs:latest

### Create the deployment
kubectl create -f kuberbets-deploy.yaml

### Delete the deployment
kubectl delete -f kuberbets-deploy.yaml

### Get the Minicube IP
minikube ip

### External IP Expose 
kubectl create -f minicube-ip-config.yaml

### Remove Loadblancer
kubectl delete svc nodejs-deployment
