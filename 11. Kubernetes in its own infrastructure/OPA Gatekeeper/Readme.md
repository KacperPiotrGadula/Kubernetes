# Instalation

``kubectl apply -f https://raw.githubusercontent.com/open-policy-agent/gatekeeper/release-3.5/deploy/gatekeeper.yaml``

# Checking the status of instalation OPA Gatekeeper
```
kubectl get pods -n gatekeeper-system
kubectl get serviceaccount -n gatekeeper-system
kubectl get all -n gatekeeper-system
```

# Checking the status of implemented policies
```
kubectl get constrainttemplate
kubectl get constraint
```