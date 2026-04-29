# 🐧 Linux Notes (Beginner to Practical)

## 📌 1. Introduction to Linux

* **Linux** = Open-source Operating System
* Based on **Linus Torvalds**
* Inspired by **Unix**
* Used in:

  * Servers (~90% of servers run Linux)
  * Cloud (AWS, Azure, GCP)
  * DevOps & Containers (Docker, Kubernetes)

---

## 📌 2. Popular Linux Distributions (Distros)

* **Ubuntu** (Beginner-friendly)
* **CentOS** (Enterprise stable)
* **Red Hat Enterprise Linux (RHEL)** (License-based)
* **Fedora** (Cutting-edge)
* **Kali Linux** (Security/Pen-testing)
* **Manjaro** (Arch-based user-friendly)

---

## 📌 3. Package Management

### Debian-based (Ubuntu)

* Extension: `.deb`
* Package Manager: `apt`

```bash
sudo apt update -y
sudo apt upgrade -y
sudo apt search <package>
sudo apt install <package>
```

### RedHat-based

* RHEL (paid)
* CentOS (community)
* Fedora (open-source)

Package Manager:

```bash
yum install <package>
dnf install <package>
```

---

## 📌 4. Shell

* Default shell: **Bash (Bourne Again Shell)**
* Used for:

  * Command execution
  * Scripting
  * Automation

---

## 📌 5. Windows Setup (WSL)

### Install WSL:

```bash
wsl --install
```

OR

```bash
wsl --install -d Ubuntu
```

Steps:

1. Run PowerShell as Administrator
2. Restart system
3. Create username (e.g., `atul`)

---

## 📌 6. Enable Required Features (Windows)

* Go to:

  ```
  Start → Windows Features
  ```
* Enable:

  * Windows Subsystem for Linux
  * Hyper-V / Hypervisor

---

## 📌 7. AWS & Azure Account Setup

### AWS

* Website: [https://aws.amazon.com](https://aws.amazon.com)
* Requirements:

  * Debit/Credit Card
  * Email
  * Mobile Number

### Azure

* Website: [https://portal.azure.com](https://portal.azure.com)
* Free Tier Available

---

## 📌 8. Linux Installation (VirtualBox / VMware)

### Steps:

1. Download ISO
   👉 [https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop)
2. Install VirtualBox / VMware
3. Create VM
4. Allocate:

   * RAM: **8GB (recommended)**
5. Attach ISO & install OS

---

## 📌 9. SSH Access (AWS EC2 Example)

```bash
chmod 400 key.pem
ssh -i "key.pem" ubuntu@<public-ip>
```

Example:

```bash
ssh -i "key.pem" ubuntu@ec2-13-220-226-147.compute-1.amazonaws.com
```

---

## 📌 10. Basic Linux Commands

### Navigation

```bash
pwd        # present working directory
ls         # list files
cd         # change directory
```

### Directory Operations

```bash
mkdir project
cd project
```

### File Operations

```bash
touch file.txt
nano file.txt
cat file.txt
```

---

## 📌 11. System & Package Commands

```bash
sudo apt update -y
sudo apt list --upgradable
sudo apt upgrade -y
history
clear
```

---

## 📌 12. Software Installation Examples

### Python

```bash
python3 --version
sudo apt install python-is-python3
```

### Java

```bash
sudo apt search java
sudo apt install javacc
java --version
```

### Tree Utility

```bash
sudo apt install tree -y
tree --version
```

---

## 📌 13. Sample Workflow (Hands-on)

```bash
mkdir project
cd project

touch helloworld.py
nano helloworld.py

# Add Python code
print("Hello World")

python helloworld.py
cat helloworld.py
```

---

## 📌 14. Useful Commands from History

```bash
history        # show command history
clear          # clear terminal
exit           # exit session
```

---

## 📌 15. Key Points to Remember (Exam + Interview)

* Linux = Open Source OS
* Bash = Default Shell
* `.deb` → Debian systems (apt)
* `yum/dnf` → RedHat systems
* `chmod 400` → Secure SSH key
* WSL → Run Linux on Windows
* 90% servers run Linux
* Used heavily in Cloud & DevOps

---

## 📌 16. Quick Cheat Sheet

| Task            | Command                  |
| --------------- | ------------------------ |
| Update system   | `sudo apt update -y`     |
| Install package | `sudo apt install <pkg>` |
| Create file     | `touch file`             |
| Edit file       | `nano file`              |
| Run Python      | `python file.py`         |
| SSH login       | `ssh -i key.pem user@ip` |
| Check history   | `history`                |

---
