Minikube has been installed and configured in the environment. Check that it is properly installed, by running the minikube version command:

`minikube version`{{execute}}

#### Start the cluster, by running the minikube start command:

`minikube start`{{execute}}

Great! You now have a running Kubernetes cluster in your online terminal. Minikube started a virtual machine for you, and a Kubernetes cluster is now running in that VM.


` minikube start --vm-driver=docker -p dc1`

useradd dc1 --create-home
useradd dc2 --create-home

usermod -a -G docker dc1

usermod -a -G docker dc2

minikube start --vm-driver=docker -p dc2 -v 8