<div align="center">
  
# Pollhammer Mail Archiv <br>
</div>
<p align="center">
</p>

<br>

## 🛠 Personal Fork & Private Mail Archive

> This is a personal fork of [Open Archiver](https://github.com/LogicLabs-OU/OpenArchiver), created for learning, experimentation, and hobby projects. It is also used as my private email archiving solution for my personal domain **"pollhammer.org"**. The focus is on exploring new ideas, testing custom features, and adapting the platform to my individual needs, while staying close to the upstream project to benefit from ongoing improvements and updates.




## Overview

Pollhammer-Mail-Archiv is a self-hosted email archiving solution designed for secure, long-term storage and easy search of email data.  
It is based on the Open Archiver project and adapted for a production-ready Pollhammer deployment.

---

## System Requirements

- Linux server (recommended: Ubuntu 22.04 LTS or newer)
- Docker (v20+)
- Docker Compose Plugin (v2+)
- Minimum 2 GB RAM (recommended: 4 GB+)
- At least 20 GB free disk space

---

## Installation Guide
### 1. Clone the Repository

Clone this fork directly to your server:

```bash
git clone https://github.com/pollhammer/Pollhammer-Mail-Archiv.git
cd Pollhammer-Mail-Archiv
```
---
### 2. Prepare Data Directory

Create a local directory for persistent data storage to avoid permission issues:

```bash
sudo mkdir -p /var/data/pollhammer-mail-archiv
sudo chown -R $(id -u):$(id -g) /var/data/pollhammer-mail-archiv
```
---
### 3. Configuration (.env)

Copy the example environment file and customize your security keys:

```bash
cp .env.example.docker .env
nano .env
```

## Important:
You must change the following values for security reasons:

- POSTGRES_PASSWORD
- MEILI_MASTER_KEY
- ENCRYPTION_KEY
---
### 4. Launch the Containers

Start the archiving system using Docker Compose:
```bash
docker compose up -d
```

Check container status:
```bash
docker compose ps
```
---
### 5. Initial Setup

Access the web interface via your browser:
```bash
http://<your-server-ip>:3000
```

Follow the setup wizard to:

- Create your admin account
- Configure your first mail source
- Verify indexing and archive synchronization
---
## Updating

To update the system:
```bash
git pull
docker compose pull
docker compose up -d
```
