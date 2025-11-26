# devops-project
Clear, professional, shows DevOps + Linux + Infra.
DevOps Linux Infra Project

A complete end-to-end DevOps project using Linux, Docker, Terraform, Ansible, AWS EC2, and GitHub Actions.

This project is designed to build real DevOps skills from scratch, perfect for learning and interview preparation.

Project Overview

This project deploys a simple web application using a full DevOps pipeline:

• Build app locally → Dockerize it
• Automate infra creation using Terraform
• Configure EC2 using Ansible
• Deploy using GitHub Actions
• Implement monitoring later (Prometheus + Grafana)
• Document everything for resume/interview

Technologies Used

Linux
AWS EC2
Terraform
Ansible
Docker
GitHub Actions
Basic Networking
CI/CD

Architecture Diagram (simple)
Local Machine (Linux VM / Windows WSL)
        |
        | Terraform
        v
AWS Cloud ----------------------------
|   EC2 Instance (Ubuntu)            |
|   Docker Installed via Ansible     |
|   App Container runs on Port 3000  |
--------------------------------------
        ^
        |
 GitHub Actions (CI/CD)

Stages of the Project
Stage 1 — Simple App & Docker (local)

Create a very small web app and run it via Docker.

Commands:

docker build -t devops-app .
docker run -p 3000:3000 devops-app

Stage 2 — Push Project to GitHub

Initialize the project:

git init
git add .
git commit -m "initial project setup"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main

Stage 3 — AWS Setup

Configure AWS CLI:

aws configure


Enter region: ap-south-1.

Stage 4 — Terraform (Infrastructure as Code)

Terraform will create:

• EC2 (t2.micro – free-tier)
• Security Group
• SSH key
• Output the public IP

You will run:

terraform init
terraform plan
terraform apply

Stage 5 — Ansible (Configuration Management)

Ansible installs Docker on EC2 and prepares deployment.

Run:

ansible-playbook -i hosts site.yml

Stage 6 — CI/CD with GitHub Actions

On every push to main:

• Build Docker image
• Push to Docker Hub
• SSH into EC2
• Pull & restart container

Stage 7 — Monitoring (Optional but Good for Resume)

• Prometheus Node Exporter
• Grafana dashboard

Repository Structure
devops-linux-infra-project
│
├── app/                 (web app + Dockerfile)
│
├── infra/               (terraform scripts)
│
├── ansible/             (playbooks)
│
├── ci-cd/               (GitHub Actions pipeline)
│
└── README.md            (this documentation)

What You Learn From This Project

• How real DevOps pipeline works
• How infra is written using Terraform
• How configuration is automated using Ansible
• How containers run in servers
• How CI/CD automates deployment
• How to secure, monitor, and improve systems

Interview Explanation (Use This)

“In my DevOps project, I built a complete deployment pipeline using Linux, Terraform, Ansible, AWS EC2, Docker, and GitHub Actions. I automated infrastructure creation using Terraform, configured servers with Ansible, containerized a web app using Docker, and set up a CI/CD pipeline that automatically deploys the application to AWS on every push.”

Next Steps

Follow project stages one by one.
Each stage is fully independent and beginner-friendly.
