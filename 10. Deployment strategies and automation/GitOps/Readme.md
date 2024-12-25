# GitLab

Important things: - never click Create Remode.md file when you initialization new procjekt and you know push in the next step projeckt what you created before on github. (You propably have big problem with push file to remote gilab repo. A lots of conflick which one hard to anderstend)

# Instalacja ArgoCD

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


# Information about ArgoCD
- ArgoCD in default hadn't have access to external network. Access to ArgoCD shoudl be only allow in inside prive network.