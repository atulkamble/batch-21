# 📘 Linux Fundamentals – Beginner to Practical Guide

## 📌 Overview

This guide covers **Linux basics, file system, commands, editors, and AWS EC2 hands-on**, designed for:

* Beginners 👶
* DevOps / Cloud learners ☁️
* Interview preparation 🎯

---

# 🐧 Introduction to Linux Operating System

## 🔹 What is Linux?

* Open-source Operating System
* Based on Unix architecture
* Created by Linus Torvalds
* Used in **90%+ servers globally**

## 🔹 Why Linux?

* Free & Open Source
* Highly Secure 🔐
* Stable for Production
* Lightweight & Fast ⚡

---

# ⭐ Features of Linux

* Multi-user support 👥
* Multi-tasking 🧠
* High security 🔐
* Open-source (customizable)
* Strong networking capabilities 🌐
* CLI-based powerful control

---

# 🧩 Flavors (Distributions) of Linux

## 🔹 Debian-based

* Ubuntu
* Kali Linux

## 🔹 RedHat-based

* Red Hat Enterprise Linux (RHEL)
* CentOS
* Fedora

## 🔹 Arch-based

* Manjaro

---

# ⚖️ Difference: Linux vs Windows

| Feature       | Linux 🐧 | Windows 🪟 |
| ------------- | -------- | ---------- |
| Cost          | Free     | Paid       |
| Source Code   | Open     | Closed     |
| Security      | High     | Moderate   |
| Performance   | Fast     | Heavy      |
| Customization | High     | Limited    |
| Usage         | Servers  | Desktop    |

---

# ⚙️ Components of Linux

## 🔹 Kernel

* Core of OS
* Manages:

  * CPU
  * Memory
  * Devices

## 🔹 Shell

* Interface between user & kernel
* Example: Bash (Bourne Again Shell)

---

# ☁️ AWS EC2 Login Demo

## 🔹 Steps

1. Create EC2 Instance in Amazon Web Services
2. Download `.pem` key
3. Connect using SSH

```bash
chmod 400 key.pem
ssh -i "key.pem" ubuntu@<public-ip>
```

---

# 💻 Basic Linux Commands

```bash
pwd       # print working directory
ls        # list files
cd        # change directory
whoami    # current user
uname -a  # system info
```

---

# 📂 File System Hierarchy

## 🔹 Important Directories

| Directory | Purpose         |
| --------- | --------------- |
| /         | Root directory  |
| /home     | User files      |
| /root     | Root user home  |
| /etc      | Config files    |
| /var      | Logs            |
| /bin      | System binaries |

---

# 🏠 Home vs Working Directory

| Concept           | Meaning                                |
| ----------------- | -------------------------------------- |
| Home Directory    | Default user folder (`/home/username`) |
| Working Directory | Current location                       |

---

# 🧭 Directory Navigation Commands

```bash
cd /home       # absolute path
cd ..          # move up
cd ~           # go to home
cd -           # previous directory
```

---

# 📍 Absolute vs Relative Path

| Type     | Example    | Description               |
| -------- | ---------- | ------------------------- |
| Absolute | /home/atul | Full path                 |
| Relative | ../docs    | Based on current location |

---

# 🧪 Hands-on Practice

```bash
mkdir demo
cd demo
touch file1.txt
ls -la
```

---

# ✍️ Text Editors in Linux

## 🔹 Types

* vi / vim (advanced)
* nano (easy)

---

# 🧠 vi / vim Editor

## 🔹 Modes

| Mode    | Description |
| ------- | ----------- |
| Insert  | Editing     |
| Command | Navigation  |
| Visual  | Selection   |

---

## 🔹 Open File

```bash
vi file.txt
```

---

## 🔹 Important Commands

| Action      | Command |
| ----------- | ------- |
| Insert Mode | i       |
| Save        | :w      |
| Exit        | :q      |
| Save & Exit | :wq     |
| Force Exit  | :q!     |

---

## 🔹 Editing & Navigation

```bash
dd       # delete line
yy       # copy line
p        # paste
u        # undo
gg       # top
G        # bottom
```

---

# 📝 nano Editor

## 🔹 Open File

```bash
nano file.txt
```

## 🔹 Basic Commands

| Action | Shortcut |
| ------ | -------- |
| Save   | Ctrl + O |
| Exit   | Ctrl + X |
| Cut    | Ctrl + K |
| Paste  | Ctrl + U |

---

# ⚔️ vi vs nano

| Feature    | vi/vim          | nano      |
| ---------- | --------------- | --------- |
| Difficulty | Hard            | Easy      |
| Power      | Advanced        | Basic     |
| Usage      | DevOps / Admins | Beginners |

---

# ⚡ Important Points to Remember (Exam + Interview)

* Linux = Open Source + Secure
* Kernel = Core of OS
* Shell = User Interface
* `/` is root directory
* `~` means home directory
* `pwd` = current path
* `cd ..` = go back
* Absolute path starts with `/`
* vi has **3 modes**
* nano is beginner-friendly
* SSH uses **port 22**

---

# 🎯 Quick Interview Questions

1. What is Linux Kernel?
2. Difference between absolute and relative path?
3. vi editor modes?
4. Difference between `/home` and `/root`?
5. How to connect EC2 instance?

---
## 🔹 What is Linux Kernel?

The **Linux Kernel** is the **core component of the Linux Operating System**.

👉 It acts as a **bridge between hardware and software**.

### Key Responsibilities:

* 🧠 Process Management (CPU scheduling)
* 💾 Memory Management (RAM allocation)
* 📦 Device Management (drivers)
* 📁 File System Management
* 🔐 Security & Access Control

👉 Without kernel → OS cannot function.

**One-liner (Interview):**
👉 *Kernel is the core of Linux OS that manages hardware resources and enables communication between software and hardware.*

---

## 🔹 Difference: Absolute Path vs Relative Path

| Feature     | Absolute Path                   | Relative Path                |
| ----------- | ------------------------------- | ---------------------------- |
| Definition  | Full path from root (`/`)       | Path from current directory  |
| Starts with | `/`                             | Not `/`                      |
| Dependency  | Independent of current location | Depends on current directory |
| Example     | `/home/atul/file.txt`           | `documents/file.txt`         |

### Quick Example:

```bash
pwd
/home/atul

# Absolute
cd /var/log

# Relative
cd ../documents
```

**One-liner (Interview):**
👉 *Absolute path starts from root, relative path starts from current directory.*

---

## 🔹 vi Editor Modes

The vi editor has **3 main modes**:

### 1️⃣ Command Mode (Default)

* Used for navigation & commands
* Press `Esc` to enter
* Examples:

  * `dd` → delete line
  * `yy` → copy
  * `/word` → search

---

### 2️⃣ Insert Mode

* Used for typing/editing text
* Press:

  * `i` → insert before cursor
  * `a` → insert after cursor
  * `o` → new line

---

### 3️⃣ Visual Mode

* Used for selecting text
* Press:

  * `v` → character selection
  * `V` → line selection

---

### Save & Exit:

```bash
:w   # save
:q   # quit
:wq  # save and quit
:q!  # force quit
```

**One-liner (Interview):**
👉 *vi has Command, Insert, and Visual modes for editing and navigation.*

---

## 🔹 Difference: `/home` vs `/root`

| Feature  | `/home`                          | `/root`                     |
| -------- | -------------------------------- | --------------------------- |
| Purpose  | Home directories of normal users | Home directory of root user |
| Access   | All users                        | Only root user              |
| Example  | `/home/atul`                     | `/root`                     |
| Security | Less privileged                  | Highly privileged           |

### Explanation:

* `/home` → contains directories for users (like `/home/atul`)
* `/root` → default home for **superuser (root)**

**One-liner (Interview):**
👉 */home is for normal users, /root is for admin (root user).*

---

## 🔹 How to Connect EC2 Instance (Linux)

Using Amazon Web Services EC2:

### Step 1: Set Permission for Key

```bash
chmod 400 key.pem
```

---

### Step 2: Connect via SSH

```bash
ssh -i key.pem ubuntu@<public-ip>
```

### Example:

```bash
ssh -i key.pem ubuntu@13.233.xxx.xxx
```

---

### Default Usernames:

| AMI          | Username |
| ------------ | -------- |
| Ubuntu       | ubuntu   |
| Amazon Linux | ec2-user |
| RHEL         | ec2-user |

---

### Ports Required:

* SSH → **22** (must be open in Security Group)

---

**One-liner (Interview):**
👉 *Use SSH with private key and public IP to connect to EC2.*

---

## 🔥 Quick Revision (Exam Ready)

* Kernel → Core of OS
* Absolute Path → Starts from `/`
* Relative Path → From current directory
* vi Modes → Command, Insert, Visual
* `/home` → Users | `/root` → Admin
* EC2 Connect → `ssh -i key.pem user@ip`

---

Here are your **clean, structured Linux + Cloud Basics Notes (Trainer + Exam Ready)** 📘

---

# 🔐 SSH (Secure Shell)

* **Protocol:** Secure remote login
* **Port:** `22`
* Used to connect to remote servers (Linux VM, EC2, Azure VM)

### 🔹 SSH Commands

```bash
ssh -i "key.pem" ec2-user@ec2-18-234-44-85.compute-1.amazonaws.com
ssh atul@20.127.204.131
```

### 🔹 Key Points

* `-i` → identity file (private key)
* Default users:

  * AWS → `ec2-user`, `ubuntu`
  * Azure → custom username (e.g., atul)

---

# 🔐 Linux Permissions

| Permission  | Value |
| ----------- | ----- |
| Read (r)    | 4     |
| Write (w)   | 2     |
| Execute (x) | 1     |

### Example:

* `7 = rwx`
* `6 = rw-`
* `4 = r--`

---

# 📦 Package Management (RHEL / Amazon Linux)

### 🔹 Commands

```bash
sudo yum update -y
sudo yum install python -y
python --version

sudo yum install git -y
git --version

sudo yum install tree -y
tree --version

sudo yum search java
```

### 🔹 Notes

* `yum` → package manager for RPM-based OS
* Used in:

  * RHEL
  * CentOS
  * Fedora
  * Amazon Linux

---

# 📁 File & Directory Commands

```bash
mkdir project      # create folder
cd project         # change directory
touch a.txt        # create file
ls                 # list files
ls -la             # detailed list (hidden + permissions)
```

---

# 💻 PowerShell (Windows Commands)

```powershell
New-Item helloworld.txt
mkdir new
notepad helloworld.txt
code .
code helloworld.txt
```

---

# ☁️ Cloud Platforms

* Amazon Web Services → [https://aws.amazon.com](https://aws.amazon.com)
* Microsoft Azure → [https://portal.azure.com](https://portal.azure.com)
* Google Cloud Platform → [https://cloud.google.com](https://cloud.google.com)

---

# ☁️ Compute Services (Interview Important)

| Cloud | Service                |
| ----- | ---------------------- |
| AWS   | Amazon EC2             |
| Azure | Azure Virtual Machines |
| GCP   | Google Compute Engine  |

---

# 🐧 Linux Basics

### 🔹 What is Linux?

* Open-source operating system
* Based on Unix
* Used in **~90% of servers**

---

# 🧠 Linux Kernel

* Core component of OS
* Manages:

  * CPU
  * Memory
  * Devices
  * Processes

👉 **Definition (Exam):**

> Kernel is the core of Linux that acts as a bridge between hardware and software.

---

# 🐧 Types of Linux (Distros)

### 🔹 Debian-Based (APT / .deb)

* Ubuntu
* Debian
* Kali Linux

### 🔹 RPM-Based (YUM / DNF / .rpm)

* RHEL (Red Hat Enterprise Linux)
* CentOS
* Fedora
* Amazon Linux

👉 **Important:**

* Ubuntu → `.deb`
* RHEL → `.rpm`

---

# 📦 Package Manager

| OS Type | Package Manager |
| ------- | --------------- |
| Debian  | `apt`           |
| RHEL    | `yum` / `dnf`   |

---

# ☁️ Amazon Linux

* Based on **RHEL (RPM)**
* Uses:

  * `yum` (Amazon Linux 2)
  * `dnf` (new versions)

---

# ☁️ Azure VM OS

* Supports:

  * Ubuntu (Debian-based)
  * RHEL (RPM-based)
* Most common: **Ubuntu**

---

# 🧾 Ubuntu Versions

* `24.04` → LTS (Long Term Support) ✅
* `22.04` → LTS (production stable)
* Non-LTS (like `.07`) → short support

---

# 🧾 RHEL Versions

* RHEL 8
* RHEL 9
* RHEL 10 (latest)

---

# 🖥️ Virtualization (Hypervisor)

### 🔹 Type 1 (Bare Metal)

* Runs directly on hardware
* Example:

  * VMware ESXi
  * Hyper-V

### 🔹 Type 2 (Hosted)

* Runs on OS
* Example:

  * VirtualBox
  * VMware Workstation

---

# 🧱 Architecture

```
Application
----------
Guest OS
----------
Hypervisor
----------
Hardware (Bare Metal)
```

---

# ⚡ Quick Interview Questions (Revision)

* What is SSH? → Secure remote login protocol (port 22)
* Difference between `.deb` and `.rpm`?
* What is kernel?
* What is EC2 / Azure VM / Compute Engine?
* Difference between Type 1 and Type 2 hypervisor?
* What is `yum` vs `apt`?

---
