# Run Application

``kubectl apply -f storage-class.yml -f redis-configmap.yml -f redis-cluster.yml -f redis-service.yml``

``kubectl apply -f app-deploy.yml -f app-svc.yml``

# Delete Application
``kubectl delete -f redis-configmap.yml -f redis-cluster.yml -f redis-service.yml -f app-deploy.yml -f app-svc.yml -f storage-class.yml``

# More command:

``kubectl get pods`` -> View pods
``kubectl get pv`` -> View Persistent volume
``kubectl get sts`` -> View StatefulSet
``kubectl get st`` -> View StorageClass
``kubectl delete pvc --all`` -> Delete all pvc from kubernetes
``kubectl delete -f .\<folder_name>\`` -> Delete full yml configuration in kubernetes visibility in .\folder\

# Redis command

## Check pods internal ip
```
kubectl get pods -l app=redis-cluster -o jsonpath='{range.items[*]}{.status.podIP}:6379 '
kubectl exec -it redis-cluster-0 -- sh
```

## Create redis cluster
``redis-cli --cluster create --cluster-replicas 1 10.100.0.7:6379 10.100.1.9:6379 10.100.2.13:6379 10.100.0.8:6379 10.100.1.10:6379 10.100.2.14:6379``

## Addpods to cluster
``kubectl exec -it redis-cluster-0 -- redis-cli cluster info``

# Check pods role in redis cluster
``kubectl exec -it <pod_name> -- redis-cli role``