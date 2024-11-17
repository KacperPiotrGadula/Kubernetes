# Command

``kubectl get svc -o wide`` -> Similar situation to ClusterIP
```
kubectl apply -f loadbalancer.yml
kubectl get svc -o wide
kubectl describe svc webapp-client-svc
kubectl delete -f loadbalancer.yml
```

# Access to service in local port

[http://public_ADRES_IP](http://public_ADRES_IP)

# Local Cluster

``kubectl cluster-info`` -> Information about curent cluster
``kubectl config use-context gke_kubernetes-439319_europe-central2-a_kubernetes`` -> Change kubernetes context from romote to local
``kubectl config get-contexts`` -> List of kubectl context cluster

# Loadbalancer test

1) Attempt to enter the public address of the host

``http://34.118.41.13/``

2)When using curl
```
PS C:\PATH\Loadbalancer> curl -v http://34.118.41.13/
VERBOSE: GET http://34.118.41.13/ with 0-byte payload
VERBOSE: received -1-byte response of content type 


StatusCode        : 200
StatusDescription : OK
Content           : {89, 111, 117, 39...}
RawContent        : HTTP/1.1 200 OK
                    Connection: keep-alive
                    Transfer-Encoding: chunked
                    Date: Sun, 17 Nov 2024 13:37:32 GMT

                    You've hit web-app-599cc486d6-f7j55

Headers           : {[Connection, keep-alive], [Transfer-Encoding, chunked], [Date,  
                    Sun, 17 Nov 2024 13:37:32 GMT]}
RawContentLength  : 36
```