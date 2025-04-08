# CI/CD Pipeline with Jenkins and Docker 🚀

This project demonstrates a **simple CI/CD pipeline** using **Jenkins** and **Docker** to build, test, push, and deploy a sample application to an AWS EC2 instance.

---

## 📦 Project Structure


## 🛠️ Tech Stack

- **Jenkins** (installed on AWS EC2)
- **Docker** (for containerization and deployment)
- **GitHub** (code repository)
- **Python + Flask** (simple app, can be replaced with any language)

---

## 📄 Jenkinsfile Overview

The `Jenkinsfile` includes the following pipeline stages:

1. **Checkout** – Pulls code from GitHub
2. **Build** – Builds a Docker image from the Dockerfile
3. **Test** – Runs test placeholder (can be replaced with real tests)
4. **Push Image** – Pushes the Docker image to Docker Hub
5. **Deploy** – Deploys the app by running a Docker container on the Jenkins host (EC2)

---

## 🚀 How to Run This Pipeline

### 1. Clone the Repo
git clone https://github.com/yourusername/my-ci-cd-app.git
cd my-ci-cd-app


### 2. Update Docker Image Name
Open the Jenkinsfile and update this line:
environment {
    DOCKER_IMAGE = 'yourdockerhubusername/yourapp:latest'
}
Replace yourdockerhubusername with your actual Docker Hub username.

### 3. Add Docker Hub Credentials in Jenkins
Go to Jenkins Dashboard → Manage Jenkins → Credentials
Add Docker Hub credentials (username & password)
Note the ID (e.g., docker-hub-credentials-id)
Use that ID in the Jenkinsfile here:docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials-id')


### 4. Create a New Jenkins Pipeline Job
Go to Jenkins → New Item
Choose Pipeline
Scroll to Pipeline script from SCM
SCM: Git
Repo URL: https://github.com/kavya9864/my-ci-cd-app.git
Script Path: Jenkinsfile

### 5. Run the Pipeline
Click "Build Now" in Jenkins.
Jenkins will:Clone the repo
Build Docker image
Push to Docker Hub
Deploy to your EC2 instance

🌐 Access the App
Visit:http://<your-ec2-public-ip>
You should see your app (e.g., Flask app homepage).

✅ Completed Milestones

 1. Jenkins installed on EC2

 2. Docker installed and running

 3. GitHub repo with Jenkinsfile and Dockerfile

 4. Jenkins pipeline created

 5. Docker image pushed to Docker Hub

 6. App deployed via Docker container
