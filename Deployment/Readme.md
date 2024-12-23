Deployment > ReplicaSet > Pod

kubectl desribe <depoyment_name>

E.g.

PS C:\PATH\Deployment> kubectl describe deployment
Name:                   deployment
Namespace:              default
CreationTimestamp:      Thu, 31 Oct 2024 08:22:21 +0100
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision: 2
Selector:               name=deployment-k8s
Replicas:               3 desired | 3 updated | 3 total | 3 available | 0 unavailable    
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  name=deployment-k8s
  Containers:
   deployment-k8s-containers:
    Image:         k8smaestro/web-app:2.0
    Port:          <none>
    Host Port:     <none>
    Environment:   <none>
    Mounts:        <none>
  Volumes:         <none>
  Node-Selectors:  <none>
  Tolerations:     <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   deployment-5b85bc8649 (3/3 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  18m   deployment-controller  Scaled up replica set deployment-6846c969fd to 3
  Normal  ScalingReplicaSet  16m   deployment-controller  Scaled up replica set deployment-5b85bc8649 to 1
  Normal  ScalingReplicaSet  16m   deployment-controller  Scaled down replica set deployment-6846c969fd to 2 from 3
  Normal  ScalingReplicaSet  16m   deployment-controller  Scaled up replica set deployment-5b85bc8649 to 2 from 1
  Normal  ScalingReplicaSet  16m   deployment-controller  Scaled down replica set deployment-6846c969fd to 1 from 2
  Normal  ScalingReplicaSet  16m   deployment-controller  Scaled up replica set deployment-5b85bc8649 to 3 from 2
  Normal  ScalingReplicaSet  16m   deployment-controller  Scaled down replica set deployment-6846c969fd to 0 from 1


  # Decribe doployment after rollback

  PS C:\PATH\Deployment> kubectl describe deployment
Name:                   deployment
Namespace:              default
CreationTimestamp:      Thu, 31 Oct 2024 08:22:21 +0100
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision: 3
Selector:               name=deployment-k8s
Replicas:               3 desired | 3 updated | 3 total | 3 available | 0 unavailable    
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  name=deployment-k8s
  Containers:
   deployment-k8s-containers:
    Image:         k8smaestro/web-app:1.0
    Port:          <none>
    Host Port:     <none>
    Environment:   <none>
    Mounts:        <none>
  Volumes:         <none>
  Node-Selectors:  <none>
  Tolerations:     <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  deployment-5b85bc8649 (0/0 replicas created)
NewReplicaSet:   deployment-5bdb75bc44 (3/3 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  21m   deployment-controller  Scaled up replica set deployment-6846c969fd to 3
  Normal  ScalingReplicaSet  19m   deployment-controller  Scaled up replica set deployment-5b85bc8649 to 1
  Normal  ScalingReplicaSet  19m   deployment-controller  Scaled down replica set deployment-6846c969fd to 2 from 3
  Normal  ScalingReplicaSet  19m   deployment-controller  Scaled up replica set deployment-5b85bc8649 to 2 from 1
  Normal  ScalingReplicaSet  19m   deployment-controller  Scaled down replica set deployment-6846c969fd to 1 from 2
  Normal  ScalingReplicaSet  19m   deployment-controller  Scaled up replica set deployment-5b85bc8649 to 3 from 2
  Normal  ScalingReplicaSet  18m   deployment-controller  Scaled down replica set deployment-6846c969fd to 0 from 1
  Normal  ScalingReplicaSet  12s   deployment-controller  Scaled up replica set deployment-5bdb75bc44 to 1
  Normal  ScalingReplicaSet  9s    deployment-controller  Scaled down replica set deployment-5b85bc8649 to 2 from 3
  Normal  ScalingReplicaSet  9s    deployment-controller  Scaled up replica set deployment-5bdb75bc44 to 2 from 1
  Normal  ScalingReplicaSet  6s    deployment-controller  Scaled down replica set deployment-5b85bc8649 to 1 from 2
  Normal  ScalingReplicaSet  6s    deployment-controller  Scaled up replica set deployment-5bdb75bc44 to 3 from 2
  Normal  ScalingReplicaSet  3s    deployment-controller  Scaled down replica set deployment-5b85bc8649 to 0 from 1


# Check rollout history

PS C:\PATH\Deployment> kubectl rollout history deployment/deployment
deployment.apps/deployment 
REVISION  CHANGE-CAUSE
3         <none>
4         <none>

# Rollout deployment to before version

PS C:\PATH\Deployment> kubectl rollout undo deployment/deployment
deployment.apps/deployment rolled back