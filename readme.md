# Microservices Application Deployment with Docker & Kubernetes (AKS)

This project demonstrates a **microservices-based web application** deployed on **Azure Kubernetes Service (AKS)**. It integrates a modern DevOps lifecycle — from containerization to orchestration — using cloud-native tools and practices.

---

## 🖼️ Architecture And Workflow
![Alt text](diagram-images/diagram1.png)

![Alt text](diagram-images/ss1.png)

![Alt text](diagram-images/ss2.png)

## 🧩 Project Overview

The application consists of multiple microservices:
- **Frontend Service** – A user-facing web interface built with modern frontend technologies.
- **Auth Service** – Handles user authentication.
- **User Service** – Manages user profiles and related data.
- **Survey Service** – Provides survey creation, participation, and results management.
- **Database** – MySQL used as the persistent data store.

Each service has its own **Dockerfile**, Kubernetes **Deployment**, **Service**, **ConfigMap**, **Horizontal Pod Autoscaler**, and **Secret** configuration.

---

## 🚀 Key Features

- Fully containerized microservices using **Docker**
- Managed orchestration using **Kubernetes (AKS)**
- Secure environment variables using **ConfigMaps** and **Secrets**
- **Ingress Controller** for unified access to services
- **Horizontal Pod Autoscaling (HPA)** for scalability
- **Namespace isolation** for better environment organization
- Includes **frontend**, **backend microservices**, and **database integration**
- Configured **MySQL** both locally and in external environments (Railway/AKS)
- Learned and implemented **debugging**, **cluster monitoring**, and **service discovery**

---

## 🏗️ Kubernetes Components Used

| Component     | Description |
|----------------|-------------|
| **Deployment** | Defines pod replicas and manages application updates |
| **ReplicaSet (RS)** | Ensures the desired number of pod replicas are running |
| **Service** | Exposes the application to other pods or externally |
| **ConfigMap** | Stores non-sensitive configuration data |
| **Secret** | Stores sensitive information like database credentials |
| **Ingress** | Manages external access to the cluster |
| **HorizontalPodAutoscaler (HPA)** | Automatically scales pods based on CPU utilization |
| **Namespace** | Segregates and organizes cluster resources logically |

---

## 🧰 Tools & Technologies

- **Docker** – Containerization
- **Kubernetes (AKS)** – Orchestration and deployment
- **MySQL** – Database management
- **Nginx Ingress Controller** – Routing and load balancing
- **Helm (optional)** – Simplified deployment management
- **kubectl** – Kubernetes CLI for managing resources
- **VS Code** – Development environment
- **Railway / Local MySQL** – Database hosting and testing

---

## ⚙️ Deployment Steps

Follow the steps below to build, push, and deploy the application to your Kubernetes cluster (local Minikube or AKS):

```bash
# 1️⃣ Build Docker Images for All Services
docker build -t myapp/frontend ./frontend
docker build -t myapp/auth-service ./auth-service
docker build -t myapp/user-service ./user-service
docker build -t myapp/survey-service ./survey-service

# 2️⃣ Push Images to Container Registry (e.g., Docker Hub, ACR)
docker push <registry>/myapp/frontend
docker push <registry>/myapp/auth-service
docker push <registry>/myapp/user-service
docker push <registry>/myapp/survey-service

# 3️⃣ Apply Kubernetes Namespace and Configurations
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/configmap.yaml
kubectl apply -f k8s/secret.yaml

# 4️⃣ Deploy All Microservices and Components
kubectl apply -f k8s/ . 

# 5️⃣ Verify Deployment Status
kubectl get pods -n microservice-ap
kubectl get svc -n microservice-ap
kubectl get ingress -n microservice-app

# 6️⃣ Access the Application
# For AKS or Cloud Environment:
# Access via Ingress Domain
# Example: http://myapp.example.com
```


## 📫 Contact & Support

### About Me
**Habibullah Jubair**  
DevOps Practitioner | Cloud & Kubernetes Enthusiast  
*Actively learning and implementing cloud-native technologies*

### Connect With Me
-  LinkedIn: [linkedin.com/in/habibullah-jubair](https://linkedin.com/in/habibullah-jubair)
-  GitHub: [github.com/jubair2002](https://github.com/jubair2002)
-  Email: habibullah.jubair2002@outlook.com

### Learning Journey
- Currently focusing on Cloud-Native architectures
- Exploring Kubernetes and Container Orchestration
- Building practical DevOps implementations
- Open to collaboration and knowledge sharing

### Feedback & Collaboration
If you have suggestions or want to collaborate:
- Open an issue in the GitHub repository
- Connect with me on LinkedIn
- Share your insights and experiences