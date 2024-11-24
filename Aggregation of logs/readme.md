# Check cluster context
```
kubecetl cluster-info
```

1. Connect to the Kibana container

``kubectl exec -it elasticsearch-6568bf6b8f-8tjwk /bin/bash``

2. Go to the bin location for the elasticsearch user

``cd /usr/share/elasticsearch/bin``

3. Run the script to generate the token

``./elasticsearch-create-enrollment-token --scope kibana``

