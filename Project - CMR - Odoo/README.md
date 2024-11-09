# Start CRM App via kubernetes

1) Command

```
kubectl apply -f namespace.yml
kubectl apply -f services.yml
kubectl apply -f postgresql.yml
kubectl apply -f odoo.yml
kubectl get pod -n odoo
```

2) Check odoo pod name

NAME                         READY   STATUS    RESTARTS   AGE
odoo-app-7c8b7f76f5-gq95s    1/1     Running   0          13s
postgresql-c59d45d4d-jghp9   1/1     Running   0          17s

- ``odoo-app-7c8b7f76f5-gq95s``

3) Command

```
kubectl port-forward odoo-app-7c8b7f76f5-gq95s 8080:8069 -n odoo
```

or

```
kubectl port-forward deployment/odoo-app 8080:8069 -n odoo
```

Example:

deployment/odoo-app: The type of resource (in this case Deployment) and its name.
8080:8069: It redirects the local port 8080 to port 8069 pods. Once launched, you can open a browser on http://localhost:8080 to access Odoo.
-n odoo: Namespace in which it runs under (if it runs in default, it can be omitted).

4) Link to you app

``http://localhost:8080``

or 

``http://localhost:8080/web``