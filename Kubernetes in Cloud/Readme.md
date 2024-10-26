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

5) Add and remove worker node from cluster via kubectl in host command line

- REMOVE 

gcloud container clusters resize k8smaestro --node-pool default-pool --num-nodes 0(set_up_0_workers_node_in_cluster) --zone <time_zone>

- ADD

gcloud container clusters resize k8smaestro --node-pool default-pool --num-nodes 3(set_up_3_workers_node_in_cluster) --zone <time_zone>

- we need it, becouse when we have workers node in cluster and we not use clsuter in something project, we will pay for cluster. When we don't having working node in cluster, we don't pay anothink becouse cluster is it not used

6) Understanding structure of folders in .kube
    - folder -> config -> shows information similar to the command "kubectl config get-context"
                       -> shows information similar to the command "kubectl config current-context"
