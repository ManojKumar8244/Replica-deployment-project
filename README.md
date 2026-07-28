# Deploying Scalable Applications using ReplicaSets and Deployments

## 📌 Project Overview

This project demonstrates how to deploy a scalable and highly available web application on Kubernetes using **ReplicaSets** and **Deployments**. ReplicaSets ensure that the desired number of Pod replicas are always running, while Deployments provide declarative updates, rolling updates, rollbacks, and simplified application lifecycle management. A Kubernetes Service is used to expose the application and distribute traffic across healthy Pods.

---

## 🎯 Objectives

- Deploy a web application using Kubernetes ReplicaSets.
- Manage application lifecycle using Kubernetes Deployments.
- Ensure high availability through multiple Pod replicas.
- Enable seamless rolling updates and rollbacks.
- Expose the application using a Kubernetes Service.
- Understand Kubernetes self-healing and scaling capabilities.

---

## 🏗️ Architecture

The project consists of the following Kubernetes resources:

- **ReplicaSet** – Maintains the desired number of application Pods and automatically recreates failed Pods.
- **Deployment** – Manages ReplicaSets, application updates, rollbacks, and scaling.
- **Service** – Provides network access to the application and balances traffic across available Pods.

---

## 🛠️ Technologies Used

- Kubernetes
- Docker
- kubectl
- YAML
- HTML
- Minikube / Amazon EKS

---

## 📂 Project Structure

```text
replicaset-deployment/
│
├── screenshots/
│
├── Architecture.png
├── Dockerfile
├── README.md
├── deployment.yaml
├── index.html
├── replicaset.yaml
└── service.yaml
```

---

## 🚀 Deployment Steps

### 1. Build the Docker Image

```bash
docker build -t web-app .
```

---

### 2. Deploy the ReplicaSet

```bash
kubectl apply -f replicaset.yaml
```

Verify the ReplicaSet:

```bash
kubectl get replicasets
kubectl get pods
```

---

### 3. Deploy the Deployment

```bash
kubectl apply -f deployment.yaml
```

Verify the Deployment:

```bash
kubectl get deployments
kubectl get replicasets
kubectl get pods
```

---

### 4. Create the Service

```bash
kubectl apply -f service.yaml
```

Verify the Service:

```bash
kubectl get services
```

---

### 5. Scale the Application

Increase the number of replicas:

```bash
kubectl scale deployment <deployment-name> --replicas=5
```

Verify:

```bash
kubectl get pods
kubectl get deployments
```

---

### 6. Perform a Rolling Update

Update the application image:

```bash
kubectl set image deployment/<deployment-name> \
<container-name>=<new-image>:<tag>
```

Monitor the rollout:

```bash
kubectl rollout status deployment/<deployment-name>
```

---

### 7. Roll Back the Deployment (Optional)

View rollout history:

```bash
kubectl rollout history deployment/<deployment-name>
```

Rollback to the previous version:

```bash
kubectl rollout undo deployment/<deployment-name>
```

---

## 🔍 Verification Commands

```bash
kubectl get deployments
kubectl get replicasets
kubectl get pods
kubectl get services

kubectl describe deployment <deployment-name>
kubectl describe replicaset <replicaset-name>

kubectl rollout status deployment/<deployment-name>
kubectl rollout history deployment/<deployment-name>
```

---

## 📊 Key Features

- Kubernetes ReplicaSet for maintaining desired Pod replicas
- Kubernetes Deployment for application lifecycle management
- Self-healing Pods
- Rolling updates with zero downtime
- Rollback support
- Horizontal scaling
- Service-based load balancing
- Declarative Infrastructure as Code using YAML

---

## 📚 Learning Outcomes

Through this project, I gained hands-on experience with:

- Kubernetes ReplicaSets
- Kubernetes Deployments
- Kubernetes Services
- Application scaling
- Rolling updates
- Rollbacks
- Self-healing workloads
- Kubernetes workload management

---

## ✅ Project Outcome

Successfully deployed a scalable web application using Kubernetes ReplicaSets and Deployments. ReplicaSets ensured application availability by maintaining the desired number of Pod replicas, while Deployments simplified application lifecycle management through rolling updates, rollbacks, and scaling. The Kubernetes Service provided reliable access to the application, resulting in a resilient, highly available, and production-ready deployment.

---

## 👨‍💻 Author

**Manoj Kumar Nagamulla**

- GitHub: https://github.com/ManojKumar8244
