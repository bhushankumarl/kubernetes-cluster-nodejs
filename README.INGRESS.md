### Apply Nginx Ingress Service
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.44.0/deploy/static/provider/cloud/deploy.yaml


### Get INGRESS Details
kubectl get pods -n ingress-nginx

### Enable Minikube Ingress
minikube addons enable ingress

### References
- https://kubernetes.github.io/ingress-nginx/deploy/