# Implementation apliaction in kontainers

1) Build docker image
```
docker build -t kacpergadula/projectapp-backend:1.0 .
docker build -t kacpergadula/projectapp-frontend:1.0 .
```
2) Push image to the docker hub
```
docker push kacpergadula/projectapp-backend:1.0
docker push kacpergadula/projectapp-frontend:1.0
```
3) Apply yml files
```
kubectl apply -f .\backend.yml
kubectl apply -f .\frontend-configmap.yml
kubectl apply -f .\
```