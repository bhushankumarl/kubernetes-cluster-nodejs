# kubernetes-cluster-nodejs

## Deploy and POD Details
kubectl get deploy,po,svc

### Delete the pod
kubectl delete -f kuberbets-pod.yaml

### Create the pod
kubectl create -f kuberbets-pod.yaml

### Create the NodePort
kubectl create -f kuberbets-nodeport-pod.yaml

### Update existing POD
kubectl apply -f kuberbets-pod.yaml

### Get the Minicube IP
minikube ip
#192.168.49.2

### Test the app using CURL
curl 192.168.49.2:34567

### Pod Details
kubectl describe pod nodejs-pod

## Set the Image
kubectl set image deployment/nodejs-deployment node-sample=bhushankumar3/kubernetes-cluster-nodejs:latest

## Login into the Minikube Docker
eval $(minikube docker-env)

## NodeJS console.log/debug
kubectl get pods
kubectl logs nodejs-deployment-787c6b6fdb-fm2z2

## Login into the container
kubectl get pods
kubectl exec nodejs-deployment-787c6b6fdb-fm2z2 -it sh

## Create the cluster IP
kubectl create -f kuberbets-cluster-ip.yaml

### Sample Docker (Running app with DOCKER)
docker run -d --publish 3000:3000 bhushankumar3/kubernetes-cluster-nodejs:latest