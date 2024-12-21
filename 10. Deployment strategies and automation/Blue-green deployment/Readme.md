# Blue-green deployment

guarantees us zero time during the release of a new version of the application for productions

Implementation sequence:

1. ``kubectl apply -f passage-v1.yml -f web-api-v1.yml -f ingress-v1.yml``
2. ``kubectl apply -f passage-v2.yml -f web-api-v2.yml`` → we are implementing a new version of the application
3. ``kubectl apply -f ingress-v2.yml`` → we are implementing a new version of ingress
4. ``kubectl delete -f passage-v1.yml -f web-api-v1.yml`` → remove the old version of the application

The definition in the matadate section for the ingress controller must be identical in both configuration files - we refer to one ingress controller, but recongize it for the new version of the application

Rollback startegy

``kubectl apply -f ingress-v1.yml``

Usuwanie calego skonfigurowanego strodowiska dla 
kubectl delete all -l part-of=blue-green-demo

Delete ingress-nginx engine

``kubectl delete -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.5.1/deploy/static/provider/cloud/deploy.yaml``