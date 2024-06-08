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

# To list all the nodes in the cluster

minikube node list

# To remove a node from the cluster

minikube node delete <node-name>

# To overwrite a label of a node

kubectl label node minikube-m02 rank=4 --overwrite=true

# To Delete a label of a node

kubectl label node <node_name> <label_key>-

kubectl label nodes minikube-m02 rank-

# To taint a node we have a command

kubectl taint node <node_name> env=production:<taint_type>

## we have 3 types of taint 1) NoSchedule 2) PreferNoSchedule 3)NoExecute

example : kubectl taint node minikube-m02 env=production:NoExecute

# Manual scaling using kubectl

kubectl scale deployment <deployment-name> --replicas=<number-of-replicas>

# example :

kubectl scale deployment my-app --replicas=5

# To Switch context

kubectl config use-context <context_name>

# To list context

kubectl config get-contexts

# Port forward

kubectl port-forward <pod_name> <pod_container_port>:<port_forward_port>

example : kubectl port-forward node-example-h2323 8081:8080

# list in all namespaces

kubectl get pods -A --> -A mean all namespaces
