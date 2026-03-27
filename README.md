# Terraform-Jenkins-cicd-Project1

# Project overview
This project demonstrates an end-to-end CI/CD pipeline where Terraform provisions AWS EC2 infrastructure, Jenkins automates build and deployment, and Docker runs a Python Flask application.

# Architecture
Terraform → EC2 → Jenkins → Docker → Flask App
- Terraform provisions EC2 instance(s)
- Jenkins runs on EC2 and executes the pipeline
- Docker builds and runs the application container
- Flask app is deployed and verified via HTTP request

#  Tech Stack

- **Terraform** – Infrastructure as Code (IaC)
- **AWS EC2** – Cloud compute
- **Jenkins** – CI/CD automation
- **Docker** – Containerization
- **Python Flask** – Web application
- **GitHub** – Source code management

# CI/CD Pipeline
**Checkout Code**
   - Jenkins pulls code from GitHub repository

 **Build Docker Image**
   ```bash
   docker build -t my-flask-app .
**Stop old container**
docker stop flask-container || true
docker rm flask-container || true

**Run new container**
docker run -d -p 5000:5000 --name flask-container my-flask-app
** Verify app **
curl http://localhost:5000
# Terraform Setup
Terraform is used to provision the EC2 instance where Jenkins is installed and runs the pipeline.
resource "aws_instance" "jenkins_server" {
  ami           = "ami-xxxxxxxx"
  instance_type = "t2.micro"
}
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

