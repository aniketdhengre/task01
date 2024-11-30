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
