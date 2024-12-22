# HELM

## 1. Instalation

1) Instalation helm (external tools)
2) Search correct Helm Chart from [Link](https://artifacthub.io/)
3) helm repo add bitnami https://charts.bitnami.com/bitnami
4) helm install my-wordpress bitnami/wordpress

## 2. Katalogs in Helm

1) Chart.yaml
- Metadate information
- version

2) values.yaml
- parameters

3) values.schema.json
- schema data for values.yaml

4) templetes
- space for yml file with ours configuration

## Documentation

[Link](https://helm.sh/docs/intro/install/)

### Instaltion on windows

Members of the Helm community contributed to the compilation of the Helm package for Winget . This package is generally up to date.

``winget install Helm.Helm``

## Helm Hub

[Link](https://artifacthub.io/)

## Instalation procedur for Elastic

### Add repository

``helm repo add elastic https://helm.elastic.co``

!! Importnat !!
- only one sc should be stay on default status (kubectl get sc)

### Install chart

``helm install my-elasticsearch elastic/elasticsearch --version 8.5.1``

### Check status after intalation procedur
1. Check status for all cluster
  kubectl get all
2. Watch all cluster members come up.
  kubectl get pods --namespace=default -l app=elasticsearch-master -w
3. Retrieve elastic user's password.
  kubectl get secrets --namespace=default elasticsearch-master-credentials -ojsonpath='{.data.password}' | base64 -d
4. Test cluster health using Helm test.
  helm --namespace=default test my-elasticsearch