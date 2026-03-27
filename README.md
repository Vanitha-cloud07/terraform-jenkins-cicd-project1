# Terraform-Jenkins-cicd-Project1
# Project overview
This project demonstrates an end-to-end CI/CD pipeline where Terraform provisions AWS EC2 infrastructure, Jenkins automates build and deployment, and Docker runs a Python Flask application.
# Architecture
Terraform → EC2 → Jenkins → Docker → Flask App
Terraform creates EC2
Jenkins runs pipeline
Docker builds & runs app
# 4. Tech Stack
Terraform (IaC)
AWS EC2 (Compute)
Jenkins (CI/CD)
Docker (Containerization)
Python Flask (App)
# CI/CD Pipeline
Checkout code from GitHub
Build Docker image
Stop old container
Run new container
Verify app
# How to Run
Clone repo
Run Terraform
Access Jenkins
Run pipeline
# Bash code
git clone <repo>
cd project
terraform init
terraform apply
# Application Output
http://18.141.229.145:5000
# Key Features
Infrastructure as Code (Terraform)
Automated CI/CD pipeline
Containerized deployment
Deployment verification

