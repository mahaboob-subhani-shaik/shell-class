# 🚀 RoboShop Microservices – End-to-End Ansible Automation

This repository contains a complete **Infrastructure as Code (IaC)** implementation for deploying the **RoboShop microservices application** using Ansible.

The project replaces traditional shell-based provisioning with **declarative, idempotent, and modular Ansible playbooks** to automate infrastructure configuration and service deployment.

---

## 🏗️ Project Architecture Overview

RoboShop is a distributed microservices-based e-commerce platform composed of multiple services written in different programming languages and backed by various datastores.

### 🔹 Application Components Automated

### 🌐 Frontend
- NGINX (Reverse Proxy & Static Web Server)

### 🗄️ Databases & Messaging
- MongoDB
- Redis
- MySQL
- RabbitMQ

### ⚙️ Backend Microservices
- Catalogue (NodeJS)
- User (NodeJS)
- Cart (NodeJS)
- Shipping (Java)
- Payment (Python)
- Dispatch (Go)

---

## 🎯 Automation Objectives

This project was designed with enterprise DevOps practices in mind:

### ✅ Idempotent Deployment
All playbooks can be executed multiple times without breaking existing configurations.


### ✅ Service Management
- Systemd service files automated
- Services enabled on boot
- Dependency ordering maintained

### ✅ Configuration Management
- Repository files managed
- Application configs templated
- NGINX reverse proxy configured

---

## 🛠️ Technology Stack

| Layer | Technology |
|-------|------------|
| Configuration Management | Ansible |
| OS | CentOS / RHEL / Amazon Linux 2 |
| Web Server | NGINX |
| Backend | NodeJS, Java, Python, Golang |
| Databases | MySQL, MongoDB, Redis |
| Messaging | RabbitMQ |





## 📂 Repository Structure

### ✅ Modular Structure
Each component has its own dedicated playbook for clean separation of concerns:

ROBOSHOP-ANSIBLE-AUTOMATION/
│
├── inventory.ini
├── nginx.conf
├── mongo.repo
├── rabbitmq.repo
│
├── 01-create-infrastructure.yaml
├── 02-mongodb.yaml
├── 03-catalogue.yaml
├── 04-cart.yaml
├── 05-frontend.yaml
├── 06-mysql.yaml
├── 07-user.yaml
├── 08-redis.yaml
├── 09-payment.yaml
├── 10-shipping.yaml
├── 11-rabbitmq.yaml
│
├── *.service files
└── README.md


---

## 🚀 How to Execute

### 1️⃣ Verify Inventory

Ensure your `inventory.ini` contains correct host groups:

```ini
[frontend]
<frontend-private-ip>

[backend]
<backend-private-ip>

[database]
<database-private-ip>
