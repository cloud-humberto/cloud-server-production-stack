# 🚀 Complete Production-Ready Cloud Server Stack

An all-in-one, production-grade template for deploying, securing, and monitoring Linux Cloud Instances (AWS, Oracle Cloud, GCP, DigitalOcean) in under 24 hours.

This repository combines web proxy routing, containerization, automated SSL/TLS certificates, system hardening, and real-time server monitoring.

---

## 🛠️ Integrated Tech Stack & Features

- **Core OS & Containerization:** Linux (Ubuntu / Debian), Docker & Docker Compose
- **Web Proxy & Routing:** Nginx Reverse Proxy with automated header optimization
- **SSL / Security:** Let's Encrypt SSL/TLS certificates via Certbot (Auto-renew)
- **Server Hardening:** UFW Firewall rules, SSH security guidelines, and Fail2ban brute-force protection
- **Monitoring:** Lightweight real-time server metrics dashboard (CPU, RAM, Disk, Traffic)

---

## 📐 System Architecture Overview

> **Public Internet** (Ports 80 / 443)  
> └── **Fail2ban Filter** (Brute-force protection)  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── **UFW Firewall** (Filters ports: 80, 443, Custom SSH)  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── **Nginx Reverse Proxy** (SSL/TLS Termination)  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── **Application Container Stack** (Isolated Internal Port)  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── **Server Monitoring Service**

---

## 🚀 Quick Execution Guide

### 1. System Update & Dependencies
Update your Linux package manager and install Docker with security tools:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y docker.io docker-compose-plugin ufw fail2ban
```

### 2. Firewall & SSH Hardening
Enable basic firewall rules to expose only necessary ports:
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 22/tcp
sudo ufw enable
```
### 3. Clone & Launch Full Stack
Clone this repository and spin up all containers (Nginx Proxy + SSL + Monitoring):
```bash
git clone [https://github.com/cloud-humberto/cloud-server-production-stack.git](https://github.com/cloud-humberto/cloud-server-production-stack.git)
cd cloud-server-production-stack
docker compose up -d
```
