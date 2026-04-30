# 🌐 Linux Web Server + Database Setup (Apache + MySQL + PHP)

## 📌 1. Important Ports & Protocols

| Service | Full Form                          | Port | Use Case                 |
| ------- | ---------------------------------- | ---- | ------------------------ |
| SSH     | Secure Shell                       | 22   | Remote server login      |
| HTTP    | HyperText Transfer Protocol        | 80   | Website (non-secure)     |
| HTTPS   | HyperText Transfer Protocol Secure | 443  | Secure website (SSL/TLS) |

---

## 📌 2. Project Use Case

### 🎯 Goal:

Host a **dynamic website** using:

* Web Server → Apache
* Database → MySQL
* Backend → PHP

👉 Example stack: **LAMP (Linux + Apache + MySQL + PHP)**

---

## 📌 3. Local Testing Concept

* Web root directory:

```bash
/var/www/html
```

* Default URL:

```
http://localhost:80
```

---

# 🐧 4. Apache Setup

## 🔹 Ubuntu / Debian (APT)

```bash
sudo apt update -y
sudo apt install apache2 -y
apache2 --version

sudo systemctl start apache2
sudo systemctl enable apache2

cd /var/www/html
```

---

## 🔹 RHEL / CentOS / Amazon Linux (YUM)

```bash
sudo yum update -y
sudo yum install httpd -y
httpd --version

sudo systemctl start httpd
sudo systemctl enable httpd

cd /var/www/html
```

---

## ✅ Verify Apache

```bash
systemctl status apache2   # Ubuntu
systemctl status httpd     # RHEL
```

Open browser:

```
http://<server-ip>
```

---

# 🗄️ 5. MySQL Installation

## 🔹 Ubuntu

```bash
sudo apt install mysql-server -y
mysql --version

sudo systemctl start mysql
sudo systemctl enable mysql
```

---

## 🔹 RHEL / Amazon Linux

```bash
sudo yum search mysql
sudo yum install mysql-server -y

mysql --version

sudo systemctl start mysqld
sudo systemctl enable mysqld
```

---

# 🧩 6. PHP Installation (For Dynamic Websites)

## 🔹 Ubuntu

```bash
sudo apt install php libapache2-mod-php php-mysql -y
```

## 🔹 RHEL

```bash
sudo yum install php php-mysql -y
```

---

# 🔐 7. MySQL Login

```bash
sudo mysql -u root -p
```

---

# 🏗️ 8. Database & User Setup

```sql
CREATE DATABASE testdb;

CREATE USER 'testuser'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON testdb.* TO 'testuser'@'localhost';

FLUSH PRIVILEGES;

EXIT;
```

---

# 📊 9. Sample Application Database

```sql
CREATE DATABASE appdb;

USE appdb;

CREATE TABLE Course (
    CourseID INT,
    CourseName VARCHAR(1000),
    Rating NUMERIC(2,1)
);
```

---

## 📥 Insert Sample Data

```sql
INSERT INTO Course VALUES
(1,'AZ-204 Developing Azure solutions',4.5),
(2,'AZ-303 Architecting Azure solutions',4.6),
(3,'DP-203 Azure Data Engineer',4.7);
```

---

## 🔍 Query Data

```sql
SELECT * FROM Course;
```

---

# 🧪 10. End-to-End Flow

```
User → Browser → Apache (Port 80)
                 ↓
               PHP
                 ↓
              MySQL DB
```

---

# ⚠️ 11. Important Points (Exam + Interview)

* Apache service name:

  * Ubuntu → `apache2`
  * RHEL → `httpd`
* Default web directory → `/var/www/html`
* MySQL service:

  * Ubuntu → `mysql`
  * RHEL → `mysqld`
* Always enable services:

```bash
systemctl enable <service>
```

---

# 🚀 12. Real-World Enhancements

* Enable HTTPS (SSL) using:

  * Let's Encrypt
* Use firewall rules:

```bash
sudo ufw allow 80
sudo ufw allow 443
```

* Secure MySQL:

```bash
sudo mysql_secure_installation
```

---

# 💡 13. Optional (XAMPP Concept)

* XAMPP = Apache + MySQL + PHP (local dev stack)
* Used for:

  * Local testing
  * Learning web development

---
