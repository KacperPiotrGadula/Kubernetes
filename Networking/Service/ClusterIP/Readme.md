# Kubectl proxy

Command to forwarding bah way request from outside of containers to inside & vice versa
``kubectl proxy``

[Link to webpage](http://localhost:8001/api/v1/namespaces/default/services/http:webapp-client-svc:/proxy/)

# Use full command

``kubectl get pods -o wide`` -> Information about pods. This way it is clear which nodes the container is worining.

``kubectl get svc -o wide`` -> Information about service in cluster and namespace default