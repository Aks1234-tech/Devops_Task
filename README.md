# 🚀 DevOps Hands-On Capstone Project

## CI/CD Pipeline for a VM-Deployed Web Application (Apache + VMware)

---

## 📌 Project Overview

This project demonstrates an **end-to-end DevOps CI/CD pipeline** for a web application deployed on a **VMware-hosted virtual machine** using the **Apache web server**.
It simulates a **real-world enterprise DevOps environment** where applications are deployed on **on-premise infrastructure** rather than cloud platforms.

The pipeline automates the complete software delivery lifecycle—from code commit to deployment—ensuring **fast, consistent, and reliable releases**.

---

## 🎯 Project Objectives

* Implement CI/CD automation using GitHub Actions
* Containerize a web application using Docker
* Deploy the application to a VMware-hosted Linux VM
* Serve the application using Apache HTTP Server
* Apply DevOps best practices for security and automation

---

## 🏗️ System Architecture

```
Developer
   ↓
GitHub Repository
   ↓
GitHub Actions (CI/CD)
   ↓
Docker Image Build
   ↓
Docker Hub Registry
   ↓
VMware Virtual Machine (Linux)
   ↓
Apache Web Server
   ↓
Live Web Application
```

---

## 🧰 Tools & Technologies

| Category              | Tool                      |
| --------------------- | ------------------------- |
| Version Control       | Git & GitHub              |
| CI/CD                 | GitHub Actions            |
| Containerization      | Docker                    |
| Container Registry    | Docker Hub                |
| Virtualization        | VMware Workstation / ESXi |
| OS                    | Ubuntu Linux              |
| Web Server            | Apache HTTP Server        |    |

---
---

### Pipeline Trigger

* Push to `main`
* Pull request to `main`

---

## ⚙️ CI/CD Pipeline Workflow

### Continuous Integration (CI)

* Triggered on every push
* Checkout source code
* Run basic validation checks
* Build Docker image
* Push image to Docker Hub

### Continuous Deployment (CD)

* SSH into VMware-hosted VM
* Pull latest Docker image
* Restart containers using Docker Compose
* Deploy updated Apache web application

---


## 🖥️ VMware Deployment Setup

* VMware Workstation / ESXi
* Ubuntu Linux VM
* Docker & Docker Compose installed
* Port forwarding / Bridged networking enabled
* Application accessible via VM IP address

🌐 **Live Application URL:**

```
https://nonallegiance-emilee-eccentrically.ngrok-free.dev/
```

---

## 🔐 Security Practices

* GitHub Secrets used for:

  * Docker Hub credentials
  * VM SSH credentials
  * No sensitive data committed to source code
  * SSH key-based authentication
  * Principle of least privilege applied

---

## 📦 Deliverables

* ✔️ GitHub repository with full source code
* ✔️ CI/CD pipeline configuration
* ✔️ Dockerized web application
* ✔️ Live deployed application on VMware VM
* ✔️ Detailed documentation (this README)


## 🧠 DevOps Concepts Demonstrated

* Continuous Integration & Deployment
* On-Prem Infrastructure Automation
* Containerization with Docker
* Apache Web Server Management
* Secure CI/CD pipelines
