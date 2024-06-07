rbac stand for role based access control

which means for certain role we can give access

for example, lets say for developer only read and write access is provided for k8's resources and delete access is not granted.

in k8's user are not created using k8's resource or component. so we need to create user in different manner.

once user is created next step is to create a role using Role resource or component.

after user and role are created, we need to create a roleblinding component which is used to attch user and role.

we also have clusterRole and clusterRoleBinding components for cluster level access.

![Authentication and authorization](authandaoth.png)

whenever we crate a minikube cluster all the configuration related to the cluster is stored in /.kube/config file

in /.kube/config file we have all the configuration related to the cluster

we will have cluster name and users also

# Note : cluster will have certificate-authority from this authority only user has to get the certificate, then only user is authenticated or else not.\

so to authenticate aginist minikube we first need to generate certificate and that certificate has to be signed by certificate-authority which minikube cluster using.

# first we need to generate a private certificate using openssl

cmd : openssl genrsa -out yashas.key 2048

# Next we need to create certificate signing request for the user with above key

cmd : openssl req -new -key yashas.key -out yashas.csr -subj "/CN=yashas/O=dev/O=example.org"

CN stands for Command name/user name.

O acts as a group name. we can all user to a multiple group
