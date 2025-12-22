# Jenkins Installation on AWS EC2 (Ubuntu)

This repository documents the step-by-step process to install and run **Jenkins** on an **AWS EC2 instance** using **Ubuntu OS**.

---

## Prerequisites

- AWS Account
- Basic knowledge of AWS EC2
- SSH client (PuTTY / Terminal)
- An EC2 key pair

---

## Step 1: Launch an EC2 Instance

1. Log in to the **AWS Management Console**
2. Navigate to **EC2 → Launch Instance**
3. Choose **Ubuntu Server (20.04 or 22.04 LTS)**
4. Select instance type (e.g., `t2.micro` – Free Tier eligible)
5. Configure key pair and network settings
6. Launch the instance

---

## Step 2: Connect to EC2 Instance

```bash
ssh -i <key-file>.pem ubuntu@<public-ipsudo apt update

---

2️⃣ Install Java (Required for Jenkins)
sudo apt install openjdk-17-jdk -y
Verify Java:
java -version

3️⃣ Add Jenkins Repository Key
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

4️⃣ Add Jenkins Repository
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

5️⃣ Install Jenkins
sudo apt update
sudo apt install jenkins -y

6️⃣ Start and Enable Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins

7️⃣ Allow Jenkins Port (8080)
sudo ufw allow 8080
sudo ufw reload

8️⃣ Access Jenkins
http://<your-server-ip>:8080
Get initial admin password:
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

✅ Result
Jenkins is successfully installed and running on Ubuntu.
You can now create jobs, pipelines, and automate deployments.


