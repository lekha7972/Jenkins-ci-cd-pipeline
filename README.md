🚀 CI/CD Pipeline using Jenkins, Docker & AWS

📌 Project Overview

This project demonstrates an end-to-end CI/CD pipeline for deploying a Node.js application using Jenkins, Docker, and AWS EC2.

The pipeline automates the process of building, testing, containerizing, and deploying the application.

---

🏗️ Architecture

GitHub → Jenkins → Docker → AWS EC2

---

🔧 Tools & Technologies

- AWS (EC2)
- Jenkins
- Docker
- Git & GitHub
- Node.js
- Linux

---

⚙️ Pipeline Workflow

1. Developer pushes code to GitHub
2. Jenkins triggers pipeline using webhook
3. Jenkins pulls latest code
4. Build the application
5. Create Docker image
6. Push image (optional: DockerHub/ECR)
7. Deploy container on EC2
8. Application is accessible via public IP

---

📂 Project Structure

.
├── app/
├── Dockerfile
├── Jenkinsfile
├── package.json
└── README.md

---

🧪 Jenkins Pipeline (Example)

pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 my-app'
            }
        }
    }
}

---

🐳 Dockerfile

FROM node:14
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 3000
CMD ["npm", "start"]

---

📸 Screenshots

- Jenkins Pipeline Execution
- Docker Build
- Application Running on EC2

(Screenshots are available in the screenshots folder)

---

🌐 Output

Application deployed successfully and accessible via EC2 public IP.

---

📌 Key Learnings

- CI/CD pipeline automation
- Docker containerization
- Jenkins pipeline setup
- AWS EC2 deployment

---

👤 Author

Lekha Priya
