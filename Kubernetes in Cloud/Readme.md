# Free sandbox

[Google Cloud Platform](https://cloud.google.com/)

# Configuration local connection to GCP cluster

1) Instalation GCP CLI

[LINK](https://cloud.google.com/sdk/docs/quickstart)

2) Autorization to GCP

gcloud auth login
gcloud config set project <procjet_name>
gcloud container clusters get-credentials <cluster_name> --zone <your_cluster_zone>

3) Check cluster info and context

kubectl config current-context
kubectl cluster-info

4) Install plugin for kubectl > 1.25 version for auth with GCP from you local command line

[LINK](https://cloud.google.com/blog/products/containers-kubernetes/kubectl-auth-changes-in-gke)