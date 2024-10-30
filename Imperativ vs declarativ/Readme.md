# Create imperativ new pod

- kubectl create -f <yml_file>

OR

- kubectl run <container_name> --image <image_name>

# Create declarative new pod

1) Prepper delarative file in .yml format

2) Apply changed

- kubectl apply -f <declarative_yml_file>