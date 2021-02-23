# kubernetes-cluster-nodejs

### Tagging the Repos
docker tag node-server bhushankumar3/kubernetes-cluster-nodejs
docker push bhushankumar3/kubernetes-cluster-nodejs:latest

## Deploy and POD Details
kubectl get deploy,po,svc

### Create the pod
kubectl create -f kuberbets-pod.yaml

### Create the NodePort
kubectl create -f kuberbets-nodeport-pod.yaml

### Get the Minicube IP
minikube ip
#192.168.49.2

### Test the app using CURL
curl 192.168.49.2:34567