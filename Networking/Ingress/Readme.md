# Ingress 

Ingress Controller-options

## We have several options:
1) Load Balancer in GCP-GCE/Azure/AWS
2) NGINX
3) Contour
4) HAProxy
5) Traefik

## Ingress Controller-tasks
1) This is not a LoadBalancer-LoadBalancer is in this
Ingress Controller
2) Continuous monitoring of the cluster
3) Detection of new Service and Ingress Resource definitions
4) Server configuration (e.g. NGINX) according to current
things to do in Kubernetes
5) Directing traffic to appropriate Services based on
definitions in Ingress Resource

# Ingress deployment

[LINK](https://kubernetes.github.io/ingress-nginx/deploy/)

[Support version](https://github.com/kubernetes/ingress-nginx#supported-versions-table)