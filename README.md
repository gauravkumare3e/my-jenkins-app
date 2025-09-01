🚀 Jenkins CI/CD Pipeline Project

This project demonstrates how to set up a CI/CD pipeline using Jenkins and Docker to build and deploy a simple Node.js application.

📌 Project Overview

The goal of this project is to automate the software delivery process with Jenkins.

Whenever code is pushed to GitHub, Jenkins automatically:
1️⃣ Pulls the latest code
2️⃣ Builds a Docker image
3️⃣ Runs a container
4️⃣ Deploys the app to http://localhost:3000

🛠️ Tools & Technologies

⚙️ Jenkins – CI/CD Automation Server

🐳 Docker – Containerization

🌐 Git & GitHub – Version Control & Repo Hosting

🟩 Node.js – Simple application (Hello from Jenkins CI/CD)

📂 Project Structure
my-jenkins-app/

├── app.js          # Node.js app file

├── package.json    # Dependencies

├── Dockerfile      # Steps to build container image

└── Jenkinsfile     # Jenkins pipeline definition

⚙️ Jenkins Pipeline

Jenkinsfile used in this project 👇

pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-jenkins-app .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker run -d -p 3000:3000 --name my-jenkins-app my-jenkins-app'
            }
        }
    }
}

▶️ How It Works

📝 Push Code to GitHub → Jenkins auto-detects changes

🏗️ Build Stage → Docker builds an image (my-jenkins-app)

🚀 Deploy Stage → Jenkins runs the container on port 3000

🌍 Access Application → Open http://localhost:3000

🏗️ Architecture Diagram

💻 Developer 
   ⬇️ Push Code
   
🌐 GitHub Repo 
   ⬇️ Trigger
   
⚙️ Jenkins Pipeline

   ├── 🏗️ Build Docker Image
   
   ├── 🧪 (Optional) Run Tests
   
   └── 🚀 Deploy Container
        ⬇️
🐳 Docker Engine → 🌍 http://localhost:3000

✅ Expected Output:

Hello from Jenkins CI/CD

🎯 Deliverables

✅ Automated Jenkins pipeline

✅ Dockerized Node.js app

✅ Continuous Integration & Deployment setup

✨ This project helped me learn how CI/CD pipelines work in real life using Jenkins and Docker
