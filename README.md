# Student Management System

A Spring Boot-based Student Management System deployed on AWS EC2 using Docker, Jenkins, and Kubernetes (Minikube).

## Application URL

Access the application:

http://13.233.2.50:9090/

### Sample Data

| ID | Name          | Email                                                       | Course |
| -- | ------------- | ----------------------------------------------------------- | ------ |
| 3  | Kapil Chavhan | [kapilchavhan88@gmail.com](mailto:kapilchavhan88@gmail.com) | IT     |

---

# Project Architecture

GitHub Repository
↓
Jenkins Pipeline
↓
Maven Build
↓
Docker Image Build
↓
Docker Hub
↓
Kubernetes Deployment (Minikube)
↓
AWS EC2 Hosting

---

# Technology Stack

* Java 21
* Spring Boot
* Spring Data JPA
* MySQL
* Maven
* Docker
* Kubernetes
* Minikube
* Jenkins
* Git & GitHub
* AWS EC2

---

# Project Structure

studentmanagement/

├── src/

├── k8s/

├── Dockerfile

├── Jenkinsfile

├── pom.xml

├── README.md

└── target/

---

# Clone Repository

```bash
git clone https://github.com/chavhankapil/studentmanagement.git

cd studentmanagement
```

---

# Run Application Locally

## Build

```bash
./mvnw clean package
```

## Run

```bash
java -jar target/*.jar
```

Application URL:

```text
http://localhost:8080
```

---

# Docker Commands

## Build Docker Image

```bash
docker build -t kapilchavhan/student-app:latest .
```

## Run Docker Container

```bash
docker run -d -p 8080:8080 kapilchavhan/student-app:latest
```

## Verify Container

```bash
docker ps
```

---

# Docker Hub

Push image:

```bash
docker login

docker push kapilchavhan/student-app:latest
```

Pull image:

```bash
docker pull kapilchavhan/student-app:latest
```

---

# Kubernetes Deployment

## Check Cluster

```bash
kubectl get nodes
```

## Deploy Application

```bash
kubectl apply -f k8s/
```

## Verify Pods

```bash
kubectl get pods
```

## Verify Services

```bash
kubectl get svc
```

## Check Deployment

```bash
kubectl get deployment
```

---

# Kubernetes Troubleshooting

Check Pods

```bash
kubectl get pods -o wide
```

Describe Pod

```bash
kubectl describe pod <pod-name>
```

View Logs

```bash
kubectl logs <pod-name>
```

Restart Deployment

```bash
kubectl rollout restart deployment student-app-deployment
```

Deployment Status

```bash
kubectl rollout status deployment student-app-deployment
```

---

# Minikube Commands

Start Minikube

```bash
minikube start
```

Status

```bash
minikube status
```

IP Address

```bash
minikube ip
```

Service URL

```bash
minikube service student-app-service --url
```

Load Image into Minikube

```bash
minikube image load kapilchavhan/student-app:latest --overwrite=true
```

---

# Jenkins CI/CD Pipeline

Pipeline Stages:

1. Clone Source Code
2. Maven Build
3. Docker Image Build
4. Docker Image Push
5. Kubernetes Deployment
6. Verification

## Jenkins Access

```text
http://<EC2-PUBLIC-IP>:8080
```

## Trigger Pipeline

1. Login to Jenkins
2. Open Job
3. Click Build Now
4. Monitor Console Output

---

# Git Workflow

Check Status

```bash
git status
```

Add Files

```bash
git add .
```

Commit

```bash
git commit -m "Update project"
```

Pull Latest Changes

```bash
git pull origin main --rebase
```

Push Changes

```bash
git push origin main
```

Create Feature Branch

```bash
git checkout -b feature/new-feature
```

---

# EC2 Verification Steps

SSH into EC2

```bash
ssh -i key.pem ec2-user@<EC2-PUBLIC-IP>
```

Check Docker

```bash
docker ps
```

Check Kubernetes

```bash
kubectl get pods

kubectl get svc

kubectl get deployment
```

Check Minikube

```bash
minikube status
```

Check Application

```bash
curl http://192.168.49.2:30007
```

Port Forward

```bash
kubectl port-forward --address 0.0.0.0 svc/student-app-service 9090:8080
```

Application URL

```text
http://13.233.2.50:9090
```

---

# API Endpoints

Get All Students

```http
GET /students
```

Get Student By ID

```http
GET /students/{id}
```

Create Student

```http
POST /students
```

Update Student

```http
PUT /students/{id}
```

Delete Student

```http
DELETE /students/{id}
```

---

# Author

Kapil Chavhan

DevOps Engineer | AWS Cloud Engineer | Kubernetes Administrator | CI/CD Engineer

