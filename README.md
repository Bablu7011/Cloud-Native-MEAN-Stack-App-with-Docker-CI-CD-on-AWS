# 🚀 Cloud-Native MEAN Stack Application Deployment
### Docker • GitHub Actions • AWS EC2

This project demonstrates a **production-ready MEAN stack application** fully containerized using Docker and deployed on AWS EC2 with an automated CI/CD pipeline using GitHub Actions.

The frontend is served via **Nginx inside a Docker container**, and all services are orchestrated using Docker Compose.

---

## 🔗 Repository

👉 https://github.com/Bablu7011/Cloud-Native-MEAN-Stack-App-with-Docker-CI-CD-on-AWS

---

## 📌 Project Overview

This application allows users to:

- ➕ Add tutorials  
- 📖 View tutorials  
- ✏️ Update tutorials  
- ❌ Delete tutorials  

---

## 🛠️ Tech Stack

- **Frontend:** Angular  
- **Backend:** Node.js, Express  
- **Database:** MongoDB  
- **Web Server:** Nginx  
- **Containerization:** Docker, Docker Compose  
- **CI/CD:** GitHub Actions  
- **Cloud:** AWS EC2 (Ubuntu)

---

## ⚙️ Key Features

✅ Full Dockerized MEAN Stack Application  
✅ Nginx Reverse Proxy for API routing  
✅ CI/CD Pipeline with GitHub Actions  
✅ Automated Deployment to AWS EC2  
✅ Zero manual deployment process  
✅ Clean Angular routing support  
✅ Scalable microservices-based architecture  

---

## 🔧 Changes & Improvements

### 🔹 Frontend Enhancements

**1. Nginx Configuration Added**
- File: `frontend/nginx/default.conf`
- Handles Angular routing
- Reverse proxies API requests to backend
- Enables cache control

**2. Updated API Base URL**
```ts
const baseUrl = '/api/tutorials';
````

✔ Enables communication via Nginx inside container

**3. Frontend Dockerfile**

* Builds Angular app
* Serves via Nginx container

---

### 🔹 Backend Enhancements

**1. Backend Dockerfile**

* Containerized Node.js application

**2. MongoDB Connection Update**

```js
url: "mongodb://mongo:27017/tutorial_db"
```

✔ Enables container-to-container communication

---

### 🔹 Root Configuration

**Docker Compose Setup**

* `frontend`
* `backend`
* `mongo`

**GitHub Actions CI/CD Pipeline**

* Builds Docker images
* Pushes to Docker Hub
* SSH into EC2
* Pulls latest code
* Runs docker-compose
* Deploys automatically

---

## ☁️ AWS EC2 Setup

Run on Ubuntu instance:

```bash
sudo apt update
sudo apt install docker.io -y
sudo apt install docker-compose -y
sudo usermod -aG docker $USER && newgrp docker
sudo systemctl enable docker
sudo systemctl start docker
```

---

## 🔐 GitHub Secrets

Add in:
**Repo → Settings → Secrets → Actions**

| Secret Name     | Description               |
| --------------- | ------------------------- |
| DOCKER_USERNAME | Docker Hub username       |
| DOCKER_PASSWORD | Docker Hub password/token |
| EC2_HOST        | EC2 Public IP             |
| EC2_USER        | ubuntu                    |
| EC2_SSH_KEY     | `.pem` key content        |

---

## ⚠️ Note on EC2 IP

* Using **t2.micro instance**
* No Elastic IP used
  ➡️ Public IP changes on restart
  ➡️ Update `EC2_HOST` secret each time

💡 Recommended: Attach Elastic IP for stability

---

## 🚀 How to Run (From Scratch)

### Step 1: Launch EC2

* Install Docker & Docker Compose

### Step 2: Clone Repo

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
```

### Step 3: Update DockerHub Username

* Edit `docker-compose.yml`

### Step 4: Add GitHub Secrets

### Step 5: Push Code

```bash
git push origin main
```

🎯 GitHub Actions will automatically:

* Build images
* Push to DockerHub
* SSH into EC2
* Deploy application

---

## 📂 Folder Structure

```
project-root/
│
├── backend/
│   ├── app/
│   ├── Dockerfile
│
├── frontend/
│   ├── nginx/default.conf
│   ├── src/
│   ├── Dockerfile
│
├── docker-compose.yml
└── .github/workflows/deploy.yml
```

---

## 🧪 Testing the Application

### API Test

```bash
curl http://YOUR_EC2_PUBLIC_IP/api/tutorials
```

### Frontend

```
http://YOUR_EC2_PUBLIC_IP
```

---

## 🎯 What This Project Demonstrates

* 🐳 End-to-end Dockerization
* 🔁 CI/CD automation with GitHub Actions
* ☁️ AWS EC2 deployment
* 🔐 Secure container communication
* ⚡ Production-ready architecture
* 🚀 Zero manual deployment workflow

---

## 👨‍💻 Author
**Bablu Kumar**
```
🔗 [https://github.com/Bablu7011](https://github.com/Bablu7011)
🔗 [https://www.linkedin.com/in/bablukumar70](https://www.linkedin.com/in/bablukumar70)
```
---

## ⭐ Final Note

This project showcases real-world DevOps practices including:

* Infrastructure automation
* Continuous delivery
* Container orchestration
* Cloud deployment



