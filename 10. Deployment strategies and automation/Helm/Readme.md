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

## Helm Command

``helm list`` -> Listing of all revisions that have been implemented
``helm upgrade`` -> Update the deployed version on cluster
``helm delete`` -> Removal of deployed configuration
``helm show`` -> Allows you to show the contents of any default configuration file for a given prepared helm chart
``helm get manifest <name of helm chart implementation>`` -> Displaying information on what, based on the helm chart, has been deployed on the infrastructure
``helm create custom-helm-chart creating custom-helm-chart`` -> Initiate the configuration of your own helm chart
``helm history <project_chart_name>`` -> show history release of <project_chart_name>
``helm rollback <project_chart_name> <REVISION_number>`` -> rollback to seted REVISION_number