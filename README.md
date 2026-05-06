# 🚀 Azure Docker CI/CD Pipeline with Jenkins Auto Deployment

## 📌 Project Overview

This project demonstrates a complete CI/CD pipeline implementation using **Azure Linux VM**, **Docker**, **Jenkins**, **GitHub Webhooks**, and **Nginx** for automated deployment.

The objective was to simulate a real-world client requirement where every code push to GitHub automatically triggers a Jenkins pipeline that rebuilds and redeploys the application inside a Docker container without manual intervention.

---

# 🧑‍💼 Client Requirement

The client wanted:

* Automated deployment workflow
* Zero manual deployment steps
* Fast update delivery after every code change
* Containerized application deployment
* CI/CD integration with GitHub
* Production-like deployment environment on Azure VM

---

# 🏗️ Solution Architecture

```text
Developer Pushes Code to GitHub
              ↓
GitHub Webhook Trigger
              ↓
Jenkins Pipeline Starts Automatically
              ↓
Docker Image Build
              ↓
Old Container Removed
              ↓
New Container Deployed
              ↓
Application Updated Automatically
```

---

# ⚙️ Technologies Used

* Microsoft Azure VM
* Ubuntu Linux
* Jenkins
* Docker
* GitHub
* GitHub Webhooks
* Nginx
* HTML
* Linux Commands

---

# 🔥 Key Features

✅ Automated CI/CD Pipeline
✅ GitHub Webhook Integration
✅ Dockerized Deployment
✅ Jenkins Auto Build Trigger
✅ Azure VM Hosting
✅ Zero Manual Deployment
✅ Real-Time Deployment Updates
✅ Production-Style Workflow

---

# 📂 Project Structure

```text
azure-cicd-project/
│
├── Dockerfile
├── index.html
└── README.md
```

---

# 🛠️ Implementation Steps

## 1️⃣ Azure VM Setup

* Created Ubuntu Linux VM on Microsoft Azure
* Opened required ports:

  * 8080 (Jenkins)
  * 8081 (Application)
  * 50000 (Jenkins Agent)

---

## 2️⃣ Jenkins Installation

* Installed Jenkins inside Docker container
* Configured Jenkins dashboard
* Created freestyle CI/CD pipeline job

---

## 3️⃣ Docker Configuration

* Installed Docker on Azure VM
* Created Dockerfile for application deployment
* Configured Docker permissions for Jenkins

---

## 4️⃣ GitHub Integration

* Connected GitHub repository with Jenkins
* Configured SCM polling and GitHub webhook trigger

---

## 5️⃣ Auto Deployment Setup

Configured deployment commands:

```bash
docker stop mysite || true
docker rm mysite || true
docker build -t mywebsite .
docker run -d -p 8081:80 --name mysite mywebsite
```

---

# ⚠️ Challenges Faced & Solutions

## ❌ Problem 1: `sudo: not found`

### Cause:

Jenkins container did not support sudo commands.

### Solution:

Removed `sudo` from deployment commands.

---

## ❌ Problem 2: Docker Permission Denied

### Error:

```bash
permission denied while trying to connect to docker.sock
```

### Cause:

Jenkins container lacked Docker socket access.

### Solution:

Mounted Docker socket and binary inside Jenkins container:

```bash
-v /var/run/docker.sock:/var/run/docker.sock
-v /usr/bin/docker:/usr/bin/docker
```

Also updated permissions:

```bash
sudo chmod 666 /var/run/docker.sock
```

---

## ❌ Problem 3: Docker Not Found Inside Jenkins

### Cause:

Docker binary unavailable inside container.

### Solution:

Mapped Docker binary from host system into Jenkins container.

---

# 📸 Project Screenshots

## 🔹 Live Auto Deployment Result

![Auto Deployment](images/auto-deployment-working.png)

---

## 🔹 GitHub Repository

![GitHub Repo](images/github-repository.png)

---

## 🔹 Jenkins Dashboard

![Jenkins Dashboard](images/jenkins-dashboard.png)

---

## 🔹 Successful Jenkins Build Output

![Build Output](images/jenkins-build-output.png)

---

## 🔹 Azure VM Terminal

![Azure VM](images/azure-vm-terminal.png)

---

## 🔹 GitHub Webhook Success

![Webhook](images/github-webhook-success.png)

---

# 🌐 Live Demo

```text
http://20.244.114.96:8081
```

---

# 📈 Final Outcome

Successfully implemented a fully automated Docker CI/CD pipeline where:

* GitHub push automatically triggers Jenkins
* Jenkins rebuilds Docker image
* Old container is removed
* New container is deployed automatically
* Updated application becomes live instantly

---

# 🧠 Skills Demonstrated

* Azure Administration
* Linux Administration
* Docker Containerization
* Jenkins Automation
* CI/CD Pipeline Design
* GitHub Webhooks
* Troubleshooting & Debugging
* Production Deployment Workflow

---

# 👨‍💻 Author

**Amit Kumar**

DevOps | Azure | Docker | Jenkins | Linux | CI/CD
