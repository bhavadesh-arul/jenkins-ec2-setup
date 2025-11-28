---

# ✅ **README.md (Jenkins Task – DevOps)**

````markdown
# Jenkins Task

## 📌 Task Description
Launch Jenkins on an AWS EC2 instance and explore:
- Creating Jenkins projects (Freestyle job)
- Creating Jenkins users

## 🖥️ Tech Stack Used
- AWS EC2 (Ubuntu)
- Jenkins
- Java (OpenJDK 17)

---

## 🚀 Steps I Followed

### 1. Launched EC2 Instance
- AMI: Ubuntu 22.04
- Instance type: t2.micro
- Security Group Inbound Rules:
  - SSH → 22
  - Custom TCP → **8080** (for Jenkins)
  - HTTP → 80 (optional)
- Connected to EC2 using SSH.

---

### 2. Installed Java (Required for Jenkins)
```bash
sudo apt update
sudo apt install -y fontconfig openjdk-17-jre
java -version
````

---

### 3. Installed Jenkins

```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install -y jenkins
```

---

### 4. Started Jenkins Service

```bash
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
```

---

### 5. Accessed Jenkins from Browser

Opened:

```
http://<EC2_PUBLIC_IP>:8080
```

Unlocked Jenkins using:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Installed **Suggested Plugins** and created the first admin user.

---

## 🛠️ Created a Freestyle Project

### Project Name:

```
hello-world-job
```

### Build Step (Execute Shell):

```bash
echo "Hello from Jenkins on EC2!"
```

Successfully ran Build #1 and verified output.

---

## 👥 Created a Jenkins User

Navigated to:

```
Manage Jenkins → Manage Users → Create User
```

Created:

* Username: `dev-user`
* Email: `dev@example.com`

Both users visible:

* `bhava-admin`
* `dev-user`

---

## 📸 Screenshots Uploaded

	Jenkins Dashboard / Unlock page
	Freestyle Job Page
	Console Output (SUCCESS)
	Manage Users page (admin + dev-user)

---

## ✔️ Task Completed

Jenkins successfully installed and configured on AWS EC2.
