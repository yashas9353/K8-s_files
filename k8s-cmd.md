minikube start --vm-driver=docker

minikube stop

minikube ssh

minikube addons list

minikube addons enable metrix-server

minikube start --nodes 4

# to add node to a existing cluster

minikube node add

# to add labels to a node :

kubectl label node <node_name> <label_name (key=value pair)>

example: kubectl label node minikube team=yashas

# to list labels with node we have a command

kubectl get nodes --show-labels

# command to list node based on label

kubectl get nodes -l team=yashas

# to get pods more details

kubectl get pods -o wide

# apply command

kubectl apply -f deployment.yaml

# delete command

kubectl delete deployment.yaml

# docker command to no-cache

docker build --no-cache -f <path_of_dockerfile> .

# no-cache will use new configuration while building
