# Udacity Kubrenetes NginX Reverse Proxy Assignment

This repo implements a Kubernetes-based NginX service that forwards requests to a SimpleExpress server. There are two extenral dependencies:

**Simple Express** - A simple server based on the following code repo: [Simple Express](https://github.com/udacity/nd9990-c3-microservices-exercises/tree/master/lesson-5-kubernetes-for-production/exercises/simple-express)

**NginX** - A web server

After deploying Simple Express to our Kubernetes cluster, we will deploy the reverse proxy to forward traffic from NginX to the Simple Express server.

## Setup Steps

1. Download source code for simple-express project from Github.
2. Create an Elastic Kubernetes Service (EKS) cluster in AWS.
3. Create a Kubernetes nodegroup inside the cluster.
4. Deploy the SimpleExpress service.yaml and deployment.yaml files to the cluster using ```kubectl apply -f```.
5. Deploy the Nginx Reverse Proxy service.yaml and deployment.yaml files from this repo to the same cluster.
6. Confirm the name of the pods: ```kubectl get pods```
7. Open a shell to either of the kubernetes pods: e.g. ```kubectl exec -it my-app-2-7d8696f755-n28g2 /bin/bash``` 
8. Check the original service URL health endpoint: ```curl http://my-app-2-svc:8080/health```
9. Check the reverse proxy endpoint: ```curl http://reverseproxy-svc:8080/api/health```

