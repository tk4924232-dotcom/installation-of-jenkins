# 🚀 Jenkins CI/CD Setup Project

This project demonstrates how to set up **Jenkins** for Continuous Integration and Continuous Deployment (CI/CD) on an Ubuntu server.

---

## 📌 Features
- Jenkins installation on Ubuntu
- Java 17 support
- Sample Jenkins job/pipeline
- Ready for CI/CD automation

---

## 🛠️ Prerequisites
Make sure you have the following installed:
- Ubuntu 20.04 / 22.04
- Java 17
- Git
- Internet access

---

## 📥 Installation Steps

### 1️⃣ Install Java
```bash
sudo apt update
sudo apt install openjdk-17-jdk -y

### 2️⃣ Add Jenkins Repository Key
Add the official Jenkins GPG key:
``` bash 
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
/usr/share/keyrings/jenkins-keyring.asc > /dev/null

###3️⃣ Add Jenkins Repository

Add Jenkins package repository to your system:
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

###4️⃣ Install Jenkins

Update package list and install Jenkins:
sudo apt update
sudo apt install jenkins -y

###5️⃣ Start and Enable Jenkins

Start Jenkins service and enable it at boot:
sudo systemctl start jenkins
sudo systemctl enable jenkins
Check Jenkins status:
sudo systemctl status jenkins

###6️⃣ Allow Jenkins Port (8080)

Allow Jenkins port through firewall:
sudo ufw allow 8080
sudo ufw reload
⚠️ If UFW is inactive, this step is optional.

###7️⃣ Access Jenkins Web Interface

Open your browser and navigate to:
http://<your-server-ip>:8080

###8️⃣Get Initial Admin Password

Retrieve the Jenkins initial admin password:
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Use this password to unlock Jenkins during first login.

### ✅ Result

🎉 Jenkins is successfully installed and running on Ubuntu.
You can now:
Install recommended plugins
Create Jenkins jobs
Build CI/CD pipelines
Automate deployments

### 📚 Next Steps

Configure Jenkins plugins
Integrate GitHub/GitLab
Create Jenkins pipelines
Add Docker or Kubernetes support



