# task01
This repository contains the solution to deploy a simple Node.js web application in a cloud-based Kubernetes environment. The application consists of a static content page, and the solution includes infrastructure-as-code (IAC) templates, Kubernetes deployment files, monitoring configuration, and a Dockerfile to containerize the application.
Navigate to the `terraform/` directory and initialize Terraform:
# mkdir terraform
```bash
terraform init
terraform apply
##access the new EKS cluster
```bash
aws eks --region <region> update-kubeconfig --name <cluster-name>




cd node-js-application
### 2. Build the Docker Image for the Node.js Application
```bash
docker build -t node-web-app .
Once the image is built, you can tag it with your Docker Hub repository name and push it to Docker Hub:
```bash
docker tag nodejs-web-app aniket329/node-web-app:latest
docker push aniket329/node-web-app:latest

