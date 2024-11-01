# Default namespace in kubernetes

In Kubernetes defaylt namespace has name "default". Any new object which we are creating will add to default namespace when we don't set up it in configuration before starting apply infrastructure to cluster.

# Command

kubectl get namespace -> Showing list of namespaces in cluster

-> kube-system -> this namespace has pod member which one responsible for action cluster

kubectl get pods -n <name_of_namespace> -> Showing pods in namespace which you are choosing 


kubectl get all -n <name_of_namespace> -> Showing members  in namespace which you are choosing 

# Check recources which will add to default namespace

PS C:\PATH\Kubernetes> kubectl api-resources --namespaced=true
NAME                           SHORTNAMES         APIVERSION                       NAMESPACED   KIND
bindings                                          v1                               true  
       Binding
configmaps                     cm                 v1                               true  
       ConfigMap
endpoints                      ep                 v1                               true  
       Endpoints
events                         ev                 v1                               true  
       Event
limitranges                    limits             v1                               true  
       LimitRange
persistentvolumeclaims         pvc                v1                               true  
       PersistentVolumeClaim
pods                           po                 v1                               true  
       Pod
podtemplates                                      v1                               true  
       PodTemplate
replicationcontrollers         rc                 v1                               true  
       ReplicationController
resourcequotas                 quota              v1                               true  
       ResourceQuota
secrets                                           v1                               true  
       Secret
serviceaccounts                sa                 v1                               true  
       ServiceAccount
services                       svc                v1                               true  
       Service
controllerrevisions                               apps/v1                          true  
       ControllerRevision
daemonsets                     ds                 apps/v1                          true  
       DaemonSet
deployments                    deploy             apps/v1                          true  
       Deployment
replicasets                    rs                 apps/v1                          true  
       ReplicaSet
statefulsets                   sts                apps/v1                          true  
       StatefulSet
localsubjectaccessreviews                         authorization.k8s.io/v1          true  
       LocalSubjectAccessReview
horizontalpodautoscalers       hpa                autoscaling/v2                   true  
       HorizontalPodAutoscaler
provisioningrequests           provreq,provreqs   autoscaling.x-k8s.io/v1beta1     true  
       ProvisioningRequest
cronjobs                       cj                 batch/v1                         true  
       CronJob
jobs                                              batch/v1                         true  
       Job
backendconfigs                 bc                 cloud.google.com/v1              true  
       BackendConfig
leases                                            coordination.k8s.io/v1           true  
       Lease
endpointslices                                    discovery.k8s.io/v1              true  
       EndpointSlice
events                         ev                 events.k8s.io/v1                 true  
       Event
capacityrequests               capreq             internal.autoscaling.gke.io/v1   true  
       CapacityRequest
pods                                              metrics.k8s.io/v1beta1           true  
       PodMetrics
operatorconfigs                                   monitoring.googleapis.com/v1     true  
       OperatorConfig
podmonitorings                                    monitoring.googleapis.com/v1     true  
       PodMonitoring
rules                                             monitoring.googleapis.com/v1     true  
       Rules
frontendconfigs                                   networking.gke.io/v1beta1        true  
       FrontendConfig
managedcertificates            mcrt               networking.gke.io/v1             true  
       ManagedCertificate
serviceattachments                                networking.gke.io/v1             true         ServiceAttachment
servicenetworkendpointgroups   svcneg             networking.gke.io/v1beta1        true         ServiceNetworkEndpointGroup
ingresses                      ing                networking.k8s.io/v1             true         Ingress
networkpolicies                netpol             networking.k8s.io/v1             true         NetworkPolicy
updateinfos                    updinf             nodemanagement.gke.io/v1alpha1   true         UpdateInfo
poddisruptionbudgets           pdb                policy/v1                        true         PodDisruptionBudget
rolebindings                                      rbac.authorization.k8s.io/v1     true         RoleBinding
roles                                             rbac.authorization.k8s.io/v1     true         Role
volumesnapshots                vs                 snapshot.storage.k8s.io/v1       true         VolumeSnapshot
csistoragecapacities                              storage.k8s.io/v1                true         CSIStorageCapacity