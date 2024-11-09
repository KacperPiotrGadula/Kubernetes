# Application of configmap

## Config map

```docker
apiVersion: v1
kind: ConfigMap
metadata:
  name: **dictionary**
data:
  **firstname**: Kacper
  **lastname**: Gadula
```

## Using the map configuration in the configuration file will give

```docker
apiVersion: v1
kind: Pod
metadata:
  labels:
    chapter: configmaps
  name: envpod
spec:
  containers:
    - name: ctr1
      image: busybox
      command: [ "/bin/sh", "-c", "watch -n 10 echo First name: $(FIRSTNAME) last name: $(LASTNAME)" ]
      env:
        - name: FIRSTNAME
          valueFrom:
            configMapKeyRef:
              name: **dictionary**
              key: **firstname**
        - name: LASTNAME
          valueFrom:
            configMapKeyRef:
              name: **dictionary**
              key: **lastname**
```

## Result:

```docker
Every 10.0s: echo First name: Kacper last name: Gadula      2024-11-09 18:29:29

First name: Kacper last name: Gadula
```

## Apply in kubernetes

1) Env File

``kubectl apply -f <configMap_file> ``

2) Yml file

``kubectl apply -f <yml_file>``