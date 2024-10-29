1) Checking status of pods in kubernetes

kubectl get pods 

No resources found in default namespace.

2) Run first pod

kubectl run <pods_name> --image=<image_name>:<version>

pod/first-pod created

kubectl get pods 
NAME        READY   STATUS    RESTARTS   AGE
first-pod   1/1     Running   0          44s

3) Delete first pod

kubectl delete pod <pod_name>

pod "first-pod" deleted

kubectl get pods
No resources found in default namespace.

4) Check kubernetes version

kubectl vesrion

5) Check information about pod

kubectl describe pod <pod_name>

State:          Running

6) Config file for yml to use in created kubernetes object

YML:
-> apiVersion -> information with api will use
-> kind -> defined which one kubernetes object will create
-> metadata -> information about pod 
-> spec -> space where define information about containers
-> containers -> space where configure container
-> --- -> end and start new section for information about new kubernetes object in one yml file

7) Imperativ vs declarativ

- imperativ we should use only in dev, qa or int stage

- declarativ (yml) we can use in prod stage