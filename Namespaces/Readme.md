# Default namespace in kubernetes

In Kubernetes defaylt namespace has name "default". Any new object which we are creating will add to default namespace when we don't set up it in configuration before starting apply infrastructure to cluster.

# Command

kubectl get namespace -> Showing list of namespaces in cluster

-> kube-system -> this namespace has pod member which one responsible for action cluster

kubectl get pods -n <name_of_namespace> -> Showing pods in namespace which you are choosing 


kubectl get all -n <name_of_namespace> -> Showing members  in namespace which you are choosing 

# Check recources which will be add to default namespace

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


# Check recources which won't be add to default namespace

PS C:\PATH\Kubernetes> kubectl api-resources --namespaced=false
NAME                                SHORTNAMES          APIVERSION                        NAMESPACED   KIND
componentstatuses                   cs                  v1                                false        ComponentStatus
namespaces                          ns                  v1                                false        Namespace
nodes                               no                  v1                                false        Node
persistentvolumes                   pv                  v1                                false        PersistentVolume
mutatingwebhookconfigurations                           admissionregistration.k8s.io/v1   false        MutatingWebhookConfiguration
validatingadmissionpolicies                             admissionregistration.k8s.io/v1   false        ValidatingAdmissionPolicy
validatingadmissionpolicybindings                       admissionregistration.k8s.io/v1   false        ValidatingAdmissionPolicyBinding
validatingwebhookconfigurations                         admissionregistration.k8s.io/v1   false        ValidatingWebhookConfiguration
customresourcedefinitions           crd,crds            apiextensions.k8s.io/v1           false        CustomResourceDefinition
apiservices                                             apiregistration.k8s.io/v1         false        APIService
selfsubjectreviews                                      authentication.k8s.io/v1          false        SelfSubjectReview
tokenreviews                                            authentication.k8s.io/v1          false        TokenReview
selfsubjectaccessreviews                                authorization.k8s.io/v1           false        SelfSubjectAccessReview
selfsubjectrulesreviews                                 authorization.k8s.io/v1           false        SelfSubjectRulesReview
subjectaccessreviews                                    authorization.k8s.io/v1           false        SubjectAccessReview
allowlistedv2workloads                                  auto.gke.io/v1                    false        AllowlistedV2Workload
allowlistedworkloads                                    auto.gke.io/v1                    false        AllowlistedWorkload
workloadallowlists                                      auto.gke.io/v1                    false        WorkloadAllowlist
certificatesigningrequests          csr                 certificates.k8s.io/v1            false        CertificateSigningRequest
computeclasses                      cc,ccs              cloud.google.com/v1               false        ComputeClass
flowschemas                                             flowcontrol.apiserver.k8s.io/v1   false        FlowSchema
prioritylevelconfigurations                             flowcontrol.apiserver.k8s.io/v1   false        PriorityLevelConfiguration
memberships                                             hub.gke.io/v1                     false        Membership
nodes                                                   metrics.k8s.io/v1beta1            false        NodeMetrics
clusternodemonitorings                                  monitoring.googleapis.com/v1      false        ClusterNodeMonitoring
clusterpodmonitorings                                   monitoring.googleapis.com/v1      false        ClusterPodMonitoring
clusterrules                                            monitoring.googleapis.com/v1      false        ClusterRules
globalrules                                             monitoring.googleapis.com/v1      false        GlobalRules
gkenetworkparamsets                                     networking.gke.io/v1              false        GKENetworkParamSet
networks                                                networking.gke.io/v1              false        Network
servicefunctionchains                                   networking.gke.io/v1              false        ServiceFunctionChain
trafficselectors                                        networking.gke.io/v1              false        TrafficSelector
ingressclasses                                          networking.k8s.io/v1              false        IngressClass
gcpresourceallowlists                                   node.gke.io/v1                    false        GCPResourceAllowlist
runtimeclasses                                          node.k8s.io/v1                    false        RuntimeClass
clusterrolebindings                                     rbac.authorization.k8s.io/v1      false        ClusterRoleBinding
clusterroles                                            rbac.authorization.k8s.io/v1      false        ClusterRole
priorityclasses                     pc                  scheduling.k8s.io/v1              false        PriorityClass
volumesnapshotclasses               vsclass,vsclasses   snapshot.storage.k8s.io/v1        false        VolumeSnapshotClass
volumesnapshotcontents              vsc,vscs            snapshot.storage.k8s.io/v1        false        VolumeSnapshotContent
csidrivers                                              storage.k8s.io/v1                 false        CSIDriver
csinodes                                                storage.k8s.io/v1                 false        CSINode
storageclasses                      sc                  storage.k8s.io/v1                 false        StorageClass
volumeattachments                                       storage.k8s.io/v1                 false        VolumeAttachment
audits                                                  warden.gke.io/v1                  false        Audit

# Testing namespace

PS C:\PATH\Namespaces> kubectl get all -n k8s-namespace
NAME                             READY   STATUS    RESTARTS   AGE
pod/webapp-k8s-f9cb4cc9f-j9q4z   1/1     Running   0          60s
pod/webapp-k8s-f9cb4cc9f-mfv8z   1/1     Running   0          60s
pod/webapp-k8s-f9cb4cc9f-v7b7q   1/1     Running   0          60s

NAME                         READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/webapp-k8s   3/3     3            3           61s

NAME                                   DESIRED   CURRENT   READY   AGE
replicaset.apps/webapp-k8s-f9cb4cc9f   3         3         3       61s

# Status namespace default vs k8s

PS C:\PATH\Namespaces> kubectl get pods -n k8s-namespace
NAME                         READY   STATUS    RESTARTS   AGE
webapp-k8s-f9cb4cc9f-j9q4z   1/1     Running   0          9m58s
webapp-k8s-f9cb4cc9f-mfv8z   1/1     Running   0          9m58s
webapp-k8s-f9cb4cc9f-v7b7q   1/1     Running   0          9m58s
PS C:PATH\Namespaces> kubectl get pod
No resources found in default namespace.

# Multi object deleting

PS C:\PATH\Namespaces> kubectl delete -f .\namespace.yml
namespace "k8s-namespace" deleted
deployment.apps "webapp-k8s" deleted

# Zmiana defaultowego namespace

kubectl config set-contest -- current --namespace=<new_name_space>