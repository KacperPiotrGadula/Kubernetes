nginx.ingress.kubernetes.io/canary: "true" -> Change configuration to desited use strategy release "Canary"
nginx.ingress.kubernetes.io/canary-weight: "30" -> Disused how much request will go to new version

# Ingress: Instalacion

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.5.1/deploy/static/provider/cloud/deploy.yaml
kubectl get pods -n ingress-nginx -l name=ingress-nginx --watch
kubectl get svc --namespace=ingress-nginx

# nip.io

info.app.34.118.47.15.nip.io

nip.io service that will create a dns entry for 34.118.47.15. It will direct traffic to it. It is not required to create your own domain to connect it to the ip address