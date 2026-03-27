# Terraform-Jenkins CI/CD Project

---

## Project Overview

This project demonstrates an end-to-end CI/CD pipeline where Terraform provisions AWS EC2 infrastructure, Jenkins automates build and deployment, and Docker runs a Python Flask application.

---

## Architecture

Terraform → EC2 → Jenkins → Docker → Flask App  

- Terraform provisions EC2 instance(s)  
- Jenkins runs on EC2 and executes the pipeline  
- Docker builds and runs the application container  
- Flask app is deployed and verified via HTTP request  

---

## Tech Stack

- Terraform – Infrastructure as Code (IaC)  
- AWS EC2 – Cloud compute  
- Jenkins – CI/CD automation  
- Docker – Containerization  
- Python Flask – Web application  
- GitHub – Source code management  

---

## CI/CD Pipeline

### 1. Checkout Code
- Jenkins pulls code from GitHub repository  

### 2. Build Docker Image
docker build -t my-flask-app .

### 3. Stop Old Container
docker stop flask-container2 || true  
docker rm flask-container2 || true  

### 4. Run New Container
docker run -d -p 5000:5000 --name flask-container2 my-flask-app  

### 5. Verify Application
curl http://localhost:5000  

---

## Terraform Setup

Terraform is used to provision the EC2 instance where Jenkins is installed and runs the pipeline.

resource "aws_instance" "jenkins_server" {
  ami           = "ami-0e7ff22101b84bcff"
  instance_type = "t3.micro"
}

---

## How to Run

1. Provision Infrastructure  
terraform init  
terraform apply  

2. Access Jenkins  
Open Jenkins using EC2 public IP  
Configure pipeline with GitHub repository  

3. Run Pipeline  
Execute Jenkins pipeline to build and deploy application  

---

## Application Output

http://18.141.229.145:5000  

---

## Pipeline Result

- Application successfully built and deployed  
- Docker container running on EC2  
- Jenkins pipeline completed with SUCCESS  
- Application verified using curl  

---

## Key Features

- Infrastructure provisioning using Terraform  
- Automated CI/CD pipeline using Jenkins  
- Containerized deployment using Docker  
- Deployment verification step included  
