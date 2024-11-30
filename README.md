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

