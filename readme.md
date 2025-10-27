# **TASK-5**  Kubernetes Deployment using Minikube

## Overview
This project demonstrates deployment and management of a containerized application using Kubernetes on Minikube.  
The goal is to automate the deployment, exposure, scaling, and inspection of workloads using declarative YAML manifests.

---

##  Objective
To deploy an application on a Kubernetes cluster created with Minikube, expose it to external traffic, and perform scaling and inspection operations.

---

## Tools Used
- Minikube  
- Kubectl  
- Docker  
- YAML  
- EC2 Instance  

---

### 1️⃣ Install and Start Minikube
Install Docker and Minikube.  
Start the Minikube cluster.
```
minikube start --driver=docker
```
Verify the cluster status.
```
minikube status
```
### 2️⃣ Create a Deployment
Create a deployment manifest file (deployment.yaml).
Apply the deployment configuration.
```
minikube kubectl -- apply -f deployment.yaml
```
Verify running pods.
```
minikube kubectl get pods
```
### 3️⃣ Expose the Application
Create a service manifest file (service.yaml).

Apply the service configuration.
```
minikube kubectl -- apply -f service.yaml
```
Verify running services.
```
minikube kubectl get svc
```
### 4️⃣ Access the Application
Retrieve the service URL.
```
minikube service nodejs --url
```
Forward the application port if needed.
```
minikube kubectl port-forward service/nodejs 8080:80 --address=0.0.0.0
```
Access the application using the displayed URL or port.

### 5️⃣ Scale the Deployment
Scale the number of replicas.
```
minikube kubectl -- scale deployment nodejs --replicas=3
Verify scaling.
```
minikube kubectl get pods
```
---
### 6️⃣ Inspect and Debug
Describe deployments and pods for detailed information.
```
minikube kubectl -- describe deployment <deployment-name>
```
```
minikube kubectl -- describe pod <pod-name>
```
View logs of a specific pod.
```
kubectl logs <pod-name>
```
### 7️⃣ Cleanup Resources
Delete the deployment and service.
```
minikube kubectl -- delete -f deployment.yaml
minikube kubectl -- delete -f service.yaml
```
Stop the Minikube cluster.
```
minikube stop
```
Deleting the cluster
```
minikube delete
```
### Output
Running pods in Running status.

Exposed service accessible via browser or port-forwarding.

Scalable and observable Kubernetes application.