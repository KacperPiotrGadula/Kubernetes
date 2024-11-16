# Service

Type of service:

1) ClusterIP
2) NodePort
3) LoadBalancer
4) ExternalName

```The kubernetes -> EP (Endpoint) object is responsible for storing and assigning IP addresses.```

# ClusterIP

- Default Service type
- Gets its own IP address
- Only available inside the cluster

# NodePort

- Port assigned for the entire cluster available on every node
- Something ala 'docker run-p' but available on all nodes, not on the one machine
- Also available outside the cluster

When enabling an application on a given port, we specify that the service will be enabled on that port from each sub-port

# LoadBalancer
- Designed for Kubernetes in cloud
- Integrates with Cloud Load Balancer
- It is also used below NodePort, and directs traffic to individual nodes
- the nodeport-like application is made available on the specified port
- the loadbalancer as a service receives an external ip address
- when traffic arrives at the loadbalancer from outside, it forwards the traffic to the corresponding port where the application is running

# External
- Maps Service to DNS entry
- Only IPv4 compliant DNS name is accepted (IP addresses are not supported)
- Does not work on labels
- It may work when migrating parts of the system to
Kubernetes
- E.g.: communication between Kubernetes and an external database data