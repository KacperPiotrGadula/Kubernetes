1) Apply infrastructure in your cluster

kubectl apply -f game.yml

2) Create proxy to service

kubectl proxy

3) Open link in browser

http://localhost:8001/api/v1/namespaces/game/services/http:service-2048:/proxy/