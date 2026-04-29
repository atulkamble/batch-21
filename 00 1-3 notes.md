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
