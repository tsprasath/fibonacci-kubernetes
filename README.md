# fibonacci-kubernetes
An over-the-top implementation of calculating Fibonacci value, with Golang, React, Redis, Postgres, NGINX. All running in Docker containers, on a Kubernetes cluster. 

How to run it locally:
* Download the repo. Make sure you have Docker installed, kubectl installed, minikube installed. 
* Run `minikube start` to start a Minikube Kubernetes cluster.
* Run `kubectl apply -f k8s`. This will apply all of the Kubernetes configs to your local cluster.
* Run `kubectl create secret generic pgpassword --from-literal PGPASSWORD=abcde12345`. This sets the secret for Postgres password.
* Run `kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/mandatory.yaml`, and `minikube addons enable ingress` to configure NGINX Ingress Controller for minikube. Reference: https://kubernetes.github.io/ingress-nginx/deploy/. 
* Run `minikube ip` to get the IP address of the minikube cluster, e.g. `192.168.99.100`.
* The website is available when going into the minikube cluster IP address. 

Reference:
This project idea, and the React code is from the Udemy class by Stephen Grider. Docker and Kubernetes: The Complete Guide. (A great class!) https://www.udemy.com/docker-and-kubernetes-the-complete-guide/
