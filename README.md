# kubernetes-cluster-nodejs

### Tagging the Repos
docker build -t node-server .
docker tag node-server bhushankumar3/kubernetes-cluster-nodejs
docker push bhushankumar3/kubernetes-cluster-nodejs:latest

### Remove Minukube to start fresh
minikube delete

### Remove the deployment
kubectl delete -f kuberbets-deploy.yaml

### Create the deployment
kubectl apply -f kuberbets-deploy.yaml

## Deploy and POD Details
kubectl get deploy,po,svc