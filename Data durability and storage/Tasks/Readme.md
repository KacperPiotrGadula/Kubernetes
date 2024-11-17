# Run application

kubectl apply -f .\storage-class.yml -f .\odoo-pvc.yaml -f .\namespace.yml -f .\services.yml -f .\postgresql.yml -f .\ingress-resource.yml -f .\odoo.yml

# Delete application

kubectl delete -f .\storage-class.yml -f .\odoo-pvc.yaml -f .\namespace.yml -f .\services.yml -f .\postgresql.yml -f .\ingress-resource.yml -f .\odoo.yml