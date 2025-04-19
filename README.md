# TASK-8

# 🔍 System Monitoring with Netdata (Docker)

This project demonstrates real-time monitoring of system metrics using **Netdata**, a powerful monitoring solution, deployed via **Docker**. It includes CPU, Memory, Disk, Network usage stats, and more — all visualized through a beautiful web dashboard.

---

## 🚀 Project Setup

### ✅ Prerequisites

- Docker installed on your system
- A modern web browser
- Port `19999` open (Netdata’s default web port)

### 🐳 Running Netdata via Docker

You can quickly spin up Netdata with the following command:

```bash
docker run -d --name=netdata \
  -p 19999:19999 \
  -v netdataconfig:/etc/netdata \
  -v netdatalib:/var/lib/netdata \
  -v netdatacache:/var/cache/netdata \
  -v /etc/passwd:/host/etc/passwd:ro \
  -v /etc/group:/host/etc/group:ro \
  -v /proc:/host/proc:ro \
  -v /sys:/host/sys:ro \
  -v /etc/os-release:/host/etc/os-release:ro \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```
🖥️ Netdata Dashboard
Once the container is running, visit http://localhost:19999 in your browser to access the dashboard.

📸 Dashboard Screenshots
![Screenshot 2025-04-19 143005](https://github.com/user-attachments/assets/d90846b5-a21a-47b3-b960-f0ac3d703cb8)

Overview Page
Detailed Metrics (CPU, Load, Memory)
![Screenshot 2025-04-19 150351](https://github.com/user-attachments/assets/67e28a98-7d05-47eb-8bf6-4270810882ec)
![Screenshot 2025-04-19 150451](https://github.com/user-attachments/assets/86656ec6-9e9d-415d-b740-697c32b5ca63)
