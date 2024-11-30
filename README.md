# task01
This repository contains the solution to deploy a simple Node.js web application in a cloud-based Kubernetes environment. The application consists of a static content page, and the solution includes infrastructure-as-code (IAC) templates, Kubernetes deployment files, monitoring configuration, and a Dockerfile to containerize the application.
Navigate to the `terraform/` directory and initialize Terraform:
# mkdir terraform
```bash
terraform init
terraform apply
```
# access the new EKS cluster
```bash
aws eks --region <region> update-kubeconfig --name <cluster-name>
```
### 2. Build the Docker Image for the Node.js Application

Navigate to the root directory of the project where the `Dockerfile` is located, and build the Docker image:

```bash
docker build -t node-web-app .
docker tag nodejs-web-app aniket329/nodejs-web-app:latest
docker push aniket329/nodejs-web-app:latest
```
# Apply the Prometheus deployment configuration to your cluster
```bash
kubectl apply -f deployment.yml
kubectl get pods
```
# Prometheus Setup and Access
## 1. Install Prometheus with Helm
```bash
helm upgrade --install prometheus prometheus-community/kube-prometheus-stack --namespace monitoring --create-namespace --wait
```
# Find the Prometheus Pod Name
```
kubectl --namespace monitoring get pods -l "release=prometheus"
```
#   Port Forward to Local Machine
```
kubectl --namespace monitoring port-forward prometheus-prometheus-server-<pod_name> 9090:9090
```
# Access Prometheus in Your Browser
