# Meet with issue:

PS C:\PATH\POD> kubectl apply -f .\pod.yml
error: error when retrieving current configuration of:
Resource: "/v1, Resource=pods", GroupVersionKind: "/v1, Kind=Pod"
Name: "", Namespace: "default"
from server for: ".\\pod.yml": resource name may not be empty
PS C:\PATH\POD> kubectl apply -f .\pod.yml
Error from server (BadRequest): error when creating ".\\pod.yml": Pod in version "v1" cannot be handled as a Pod: strict decoding error: unknown field "spec.containers[0].-containerPort"
PS C:\PATH\POD> kubectl apply -f .\pod.yml
The Pod "first_pod" is invalid: metadata.name: Invalid value: "first_pod": a lowercase RFC 1123 subdomain must consist of lower case alphanumeric characters, '-' or '.', and must start and end with an alphanumeric character (e.g. 'example.com', regex used for validation is '[a-z0-9]([-a-z0-9]*[a-z0-9])?(\.[a-z0-9]([-a-z0-9]*[a-z0-9])?)*')

# Delarativ & Imperativ

Declarativ

kubectl apply -f .\pod.yml

Imperativ

kubectl run secend-pod --image dnaprawa/hello-kubernetes:1.0
