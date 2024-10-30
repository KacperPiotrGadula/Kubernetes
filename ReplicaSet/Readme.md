replicaSet is recommended and endorsed by kubernetes

replicas - specifies the number of sub-cows

selector - defines which containers it has to take care of

# Check replication status

PS C:\<PATH>>\ReplicaSet> kubectl get rs
NAME         DESIRED   CURRENT   READY   AGE
kubernetes   3         3         3       90s

