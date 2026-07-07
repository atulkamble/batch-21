# DevOps Lab Environment Setup Guide (Windows + AWS EC2)

## Objective

This guide helps you prepare a complete DevOps lab environment on Windows and AWS EC2. After completing these steps, you will have the required tools for Git, Docker, Kubernetes, Terraform, Jenkins, AWS CLI, Ansible, Python, and Grafana.

---

# Prerequisites

* Windows 10/11 (64-bit)
* Administrator privileges
* Stable Internet connection
* AWS Account
* AWS EC2 (Amazon Linux 2023 recommended)
* Visual Studio Code

---

# Install Visual Studio Code

Download and install Visual Studio Code.

Recommended Extensions:

* Microsoft Terraform
* HashiCorp Terraform
* Ansible

These extensions provide:

* Terraform syntax highlighting
* IntelliSense
* Validation
* Ansible playbook support
* YAML assistance

---

# Install Windows Subsystem for Linux (WSL)

Open **PowerShell as Administrator**.

Install the default Linux distribution:

```powershell
wsl --install
```

Or install Ubuntu directly:

```powershell
wsl --install -d Ubuntu
```

Verify installation:

```powershell
wsl --status
```

---

# Install Chocolatey Package Manager

Install Chocolatey by following the official installation instructions.

Once installed, verify:

```powershell
choco --version
```

---

# Install Development Tools using Chocolatey

## Git

```powershell
choco install git -y
```

Verify:

```powershell
git --version
```

---

## Python

```powershell
choco install python -y
```

Verify:

```powershell
python --version
pip --version
```

---

## Minikube

```powershell
choco install minikube -y
```

Start Minikube:

```powershell
minikube start
```

Check status:

```powershell
minikube status
```

---

## Kubernetes CLI (kubectl)

```powershell
choco install kubernetes-cli -y
```

Verify:

```powershell
kubectl version --client
```

---

## Terraform

```powershell
choco install terraform -y
```

Verify:

```powershell
terraform --version
```

---

# Install AWS CLI

Download from:

https://aws.amazon.com/cli/

Verify:

```powershell
aws --version
```

Configure AWS:

```powershell
aws configure
```

---

# Install PowerShell 7

Download:

https://learn.microsoft.com/en-us/powershell/scripting/install/install-powershell?view=powershell-7.6

Verify:

```powershell
pwsh
```

---

# Install Docker Desktop

Download:

https://www.docker.com/products/docker-desktop/

After installation:

* Enable WSL Integration
* Start Docker Desktop

Verify:

```powershell
docker --version
docker ps
```

---

# Minikube Documentation

Official Documentation:

https://minikube.sigs.k8s.io/docs/

---

# Jenkins Installation on AWS EC2

## Security Group

Allow the following ports:

| Port | Purpose          |
| ---- | ---------------- |
| 22   | SSH              |
| 8080 | Jenkins          |
| 80   | HTTP (Optional)  |
| 443  | HTTPS (Optional) |

---

# Install Required Packages

```bash
sudo yum install python python-pip aws-cli git docker -y
```

---

# Configure Git

```bash
sudo git config --global user.name "Atul Kamble"
sudo git config --global user.email "atul_kamble@hotmail.com"
```

Verify:

```bash
git config --global --list
```

---

# Start Docker

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

Check Docker:

```bash
sudo systemctl status docker
docker --version
```

---

# Install Java 21

Search available packages:

```bash
sudo yum search java-21
```

Install OpenJDK 21:

```bash
sudo yum install fontconfig java-21-openjdk
```

Verify:

```bash
java -version
```

---

# Install Jenkins Repository

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/rpm-stable/jenkins.repo
```

Update packages:

```bash
sudo yum upgrade -y
```

Install Jenkins:

```bash
sudo yum install jenkins
```

Reload systemd:

```bash
sudo systemctl daemon-reload
```

---

# Start Jenkins

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

Check status:

```bash
sudo systemctl status jenkins
```

Access Jenkins:

```
http://<EC2-Public-IP>:8080
```

Retrieve initial administrator password:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

---

# Install Terraform on Amazon Linux

Install required utilities:

```bash
sudo yum install -y yum-utils shadow-utils
```

Add the HashiCorp repository:

```bash
sudo yum-config-manager --add-repo \
https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
```

Install Terraform:

```bash
sudo yum install terraform
```

Verify:

```bash
terraform --version
```

---

# Install Grafana Enterprise

Update the system:

```bash
sudo yum update -y
```

Install prerequisites:

```bash
sudo yum install wget tar make -y
```

Install Grafana Enterprise:

```bash
sudo yum install -y \
https://dl.grafana.com/grafana-enterprise/release/12.2.1/grafana-enterprise_12.2.1_18655849634_linux_amd64.rpm
```

Enable and start Grafana:

```bash
sudo systemctl enable grafana-server
sudo systemctl start grafana-server
```

Check status:

```bash
sudo systemctl status grafana-server
```

Verify version:

```bash
grafana-server --version
```

Access Grafana:

```
http://<EC2-Public-IP>:3000
```

Default credentials:

```
Username: admin
Password: admin
```

---

# Install Ansible (Optional)

Search available package:

```bash
sudo yum search ansible
```

Install:

```bash
sudo yum install ansible -y
```

Verify:

```bash
ansible --version
```

---

# Verify All Installed Software

## Windows

```powershell
git --version
python --version
pip --version
aws --version
docker --version
terraform --version
kubectl version --client
minikube status
```

---

## Amazon Linux EC2

```bash
git --version
aws --version
python --version
pip --version
docker --version
terraform --version
grafana-server --version
ansible --version
```

---

# Verify Running Services

Docker

```bash
sudo systemctl status docker
```

Jenkins

```bash
sudo systemctl status jenkins
```

Grafana

```bash
sudo systemctl status grafana-server
```

---

# Lab Outcome

After completing this guide, you will have a fully configured DevOps environment with:

* Visual Studio Code
* WSL (Ubuntu)
* Chocolatey
* Git
* Python
* AWS CLI
* Docker Desktop
* Minikube
* Kubernetes CLI (kubectl)
* Terraform
* Jenkins
* Grafana Enterprise
* Ansible

This environment is suitable for learning and practicing:

* Linux Administration
* Git & GitHub
* Docker
* Kubernetes
* Jenkins CI/CD
* Infrastructure as Code with Terraform
* Configuration Management with Ansible
* AWS Cloud Services
* Monitoring with Grafana
