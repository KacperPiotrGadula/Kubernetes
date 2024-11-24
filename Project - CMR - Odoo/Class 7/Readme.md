# Run application

kubectl apply -f .\storage-class.yml -f .\namespace.yml -f .\services.yml -f .\odoo-pvc.yaml -f .\postgresql.yml -f .\ingress-resource.yml -f .\odoo.yml

# Delete application

kubectl delete -f .\storage-class.yml -f .\namespace.yml -f .\services.yml -f .\odoo-pvc.yaml -f .\postgresql.yml -f .\ingress-resource.yml -f .\odoo.yml

# Access to appplication via public address ip

1) Check Public IP for ingress

```
kubectl get ingress -n odoo

NAME               CLASS   HOSTS   ADDRESS        PORTS   AGE
ingress-resource   nginx   *       34.118.8.207   80      14m
```