# Default namespace in kubernetes

In Kubernetes defaylt namespace has name "default". Any new object which we are creating will add to default namespace when we don't set up it in configuration before starting apply infrastructure to cluster.

# Command

kubectl get namespace -> Showing list of namespaces in cluster

-> kube-system -> this namespace has pod member which one responsible for action cluster