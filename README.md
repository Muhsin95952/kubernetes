# Kubernetes 
## Setup and Architecture Guide

This repository provides a comprehensive overview of **Kubernetes**, including its **architecture**, and detailed **installation guides** using **Minikube** (for local development) and **Kops** (for production-grade clusters on the cloud).  
It’s designed for DevOps practitioners and learners who want to understand and deploy Kubernetes clusters effectively.

---

## 📘 Table of Contents

1. [Introduction](#introduction)
2. [Kubernetes Architecture](#kubernetes-architecture)
3. [Installation Guide](#installation-guide)
   - [Minikube Setup (Local Environment)](#minikube-setup-local-environment)
   - [Kops Setup (Cloud Environment)](#kops-setup-cloud-environment)
4. [Useful Commands](#useful-commands)
5. [References](#references)

---

## 🧠 Introduction

**Kubernetes (K8s)** is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.  
It abstracts the underlying infrastructure, allowing you to run and manage containers across multiple hosts seamlessly.

Key Features:
- Automated container deployment and scaling  
- Self-healing and rolling updates  
- Load balancing and service discovery  
- Infrastructure abstraction for portability  

Kubernetes helps you move from running containers individually to managing them efficiently across clusters.

---

## 🏗️ Kubernetes Architecture

Kubernetes follows a **master-worker (control plane - node)** architecture.

### 🔹 **Control Plane Components**
These manage the cluster’s overall state and scheduling:
- **API Server:** The front-end of the control plane that exposes the Kubernetes API.  
- **etcd:** A distributed key-value store that holds cluster state and configuration data.  
- **Controller Manager:** Ensures the desired state of the cluster by controlling replication, endpoints, and nodes.  
- **Scheduler:** Assigns workloads (pods) to nodes based on resource requirements and constraints.

### 🔹 **Node Components**
These run the actual workloads (containers):
- **Kubelet:** Communicates with the API server and ensures that containers are running as expected.  
- **Kube-Proxy:** Manages network rules and enables communication between pods and services.  
- **Container Runtime:** Software used to run containers (e.g., Docker, containerd, CRI-O).

### 🧩 **Kubernetes Objects**
- **Pod:** Smallest deployable unit (one or more containers).  
- **Deployment:** Manages pod replicas and updates.  
- **Service:** Provides stable networking and load balancing for pods.  
- **ConfigMap / Secret:** Store configuration data securely.  
- **Ingress:** Manages external HTTP/HTTPS access.

---

## ⚙️ Installation Guide

### 🧩 Minikube Setup (Local Environment)

Minikube is ideal for running Kubernetes locally for testing and development.

#### **Prerequisites**
- Installed Docker from here [Docker](https://docs.docker.com/get-docker/) OR 
  ##### Docker insallation
  ```bash
  sudo apt-get update
  sudo apt-get install docker.io -y
   ```

- Installed kubectl from here [kubectl](https://kubernetes.io/docs/tasks/tools/) OR
##### kubectl installation
```bash
sudo apt update
sudo snap install kubectl --classic
 ```

- Installed Minikube from here [Minikube](https://minikube.sigs.k8s.io/docs/start/) OR
  ##### Minikube Installation
  ```bash
  curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-linux-amd64
  sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
   ```

###### Start Minikube
```bash
minikube start
```
###### Verify the status
```bash
minikube status
```

###### View cluster info
```bash
kubectl cluster-info
```

###### List all nodes
```bash
kubectl get nodes
```
