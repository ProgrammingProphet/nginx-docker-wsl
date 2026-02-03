# 🐳 Nginx with Docker Desktop on Windows (WSL2)

## 📌 Project Overview

This project demonstrates a **successful setup and validation of Docker Desktop with WSL2 on Windows**, followed by running **Nginx inside a Docker container**.

The goal of this project is to:

- Validate **WSL2 configuration**
- Ensure **Docker Desktop ↔ Ubuntu (WSL2) integration**
- Run and expose an **Nginx container**
- Build a strong **foundation for DevOps projects**

This setup closely mirrors **real-world DevOps local environments** used in the industry.

---

## 🧱 Tech Stack

- **Operating System**: Windows 10 (22H2)
- **WSL Version**: WSL2
- **Linux Distro**: Ubuntu 20.04 LTS
- **Container Runtime**: Docker Desktop
- **Web Server**: Nginx
- **Architecture**: Linux containers via WSL2 backend

---

## 🗂 Project Scope

✔ Enable CPU virtualization (BIOS)
✔ Install & configure WSL2
✔ Convert Ubuntu from WSL1 → WSL2
✔ Integrate Ubuntu with Docker Desktop
✔ Run Docker containers from Ubuntu
✔ Deploy Nginx using Docker
✔ Access Nginx via browser (`localhost`)

---

## ⚙️ System Prerequisites

- Windows 10 version **19045 (22H2)** or higher
- CPU with **virtualization support (VT-x / AMD-V)**
- Virtualization enabled in **BIOS**
- Internet access for Docker images

---

## 🔧 Setup & Configuration Steps

### 1️⃣ Verify WSL Installation

```bash
wsl --status
```

Expected:

```
Default Distribution: Ubuntu-20.04
Default Version: 2
```

---

### 2️⃣ Verify Ubuntu Version (WSL2 Required)

```bash
wsl -l -v
```

Expected:

```
Ubuntu-20.04   Running   2
docker-desktop Running   2
```

---

### 3️⃣ Docker Desktop Configuration

- Enable **Use WSL2 based engine**
- Enable **Ubuntu-20.04** under:

  ```
  Settings → Resources → WSL Integration
  ```

---

### 4️⃣ Verify Docker from Ubuntu

```bash
docker --version
docker run hello-world
```

Successful output confirms Docker is working inside WSL2.

---

## 🌐 Running Nginx Container

### Pull & Run Nginx

```bash
docker run -d -p 8080:80 --name nginx-test nginx
```

### Access in Browser

```
http://localhost:8080
```

Expected output:

```
Welcome to nginx!
```

---

## 📁 Recommended Working Directory

⚠ Avoid using `/mnt/c` for Docker workloads.

✅ Use Linux filesystem:

```bash
/home/<username>/devops
```

Benefits:

- Faster Docker builds
- Fewer permission issues
- Production-like behavior

---

## 🧪 Validation Checklist

| Check                   | Status |
| ----------------------- | ------ |
| WSL2 Installed          | ✅     |
| Ubuntu on WSL2          | ✅     |
| Docker Desktop Running  | ✅     |
| WSL Integration Enabled | ✅     |
| Docker CLI in Ubuntu    | ✅     |
| Nginx Container Running | ✅     |
| Browser Access Working  | ✅     |

---

## 📈 Learning Outcomes

- Deep understanding of **WSL1 vs WSL2**
- Real-world Docker Desktop troubleshooting
- Linux-based container execution on Windows
- Networking via Docker port mapping
- DevOps environment setup best practices

---

## 🚀 Next Enhancements (Future Scope)

- Docker Compose setup
- Nginx as reverse proxy
- SSL/TLS with Nginx
- CI/CD pipeline integration
- Deployment on AWS EC2

---

## 🧑‍💻 Author

**Aditya Vishwakarma**
Aspiring DevOps / Cloud Engineer
Focus: Docker • Nginx • AWS • Linux • Automation

---

## 📌 Conclusion

This project establishes a **strong DevOps foundation** by correctly configuring WSL2 and Docker Desktop and validating containerized Nginx execution.
The same setup can be **directly migrated to cloud environments** with minimal changes.

