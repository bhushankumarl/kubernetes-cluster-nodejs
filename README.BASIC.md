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