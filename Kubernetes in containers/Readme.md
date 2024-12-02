# Implementation MySQL in containers

1. ``kubectl create -f gcp-storage-class.yml``
2. ``kubectl apply -f mysql-configmap.yml -f mysql-service.yml -f mysql-replicated.yml``

## Testing

```
kubectl run mysql-client -it --image=mysql:5.7 -- bash

mysql -h mysql-0.mysql <<EOF
CREATE DATABASE k8smaestro;
CREATE TABLE k8smaestro.inputs (input VARCHAR(250));
INSERT INTO k8smaestro.inputs VALUES ('an input from k8smaestro using mysql-client');
EOF
exit

kubectl delete pod mysql-client
kubectl run mysql-client --image=mysql:5.7 -it --rm --restart=Never -- mysql -h mysql-read -e "SELECT * FROM k8smaestro.inputs"

kubectl run mysql-client-in-loop --image=mysql:5.7 -it --rm --restart=Never -- bash -ic "while sleep 1; do mysql -h mysql-read -e 'SELECT @@server_id,NOW()'; done"
```

## High avability

```
kubectl run mysql-client-in-loop --image=mysql:5.7 -it --rm --restart=Never -- bash -ic "while sleep 1; do mysql -h mysql-read -e 'SELECT @@server_id,NOW()'; done"

kubectl delete pod mysql-1 --force
```

## Scaling

```
kubectl scale statefulset mysql --replicas=3

kubectl run mysql-client-in-loop --image=mysql:5.7 -it --rm --restart=Never -- bash -ic "while sleep 1; do mysql -h mysql-read -e 'SELECT @@server_id,NOW()'; done"

kubectl run mysql-client --image=mysql:5.7 -it --rm --restart=Never -- mysql -h mysql-2.mysql -e "SELECT * FROM k8smaestro.inputs"

kubectl -n mysql  scale statefulset mysql --replicas=2

kubectl get pvc -l app=mysql
```