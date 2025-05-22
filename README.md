# jenkins-aws-deployment
A basic DevOps project deploying Jenkins CI/CD server on AWS EC2 instance.


---

````markdown
# 🚀 Jenkins on AWS EC2 – Full Setup Guide

This is a complete, copy-paste-friendly guide to installing Jenkins on an AWS EC2 Ubuntu server and accessing it from the public internet. Perfect for reference—even a year later!

---

## 🔐 Step 1: Launch EC2 Instance

1. Go to AWS EC2 Console → Launch Instance
2. Choose:
   - AMI: **Ubuntu Server 24.04 LTS**
   - Instance type: **t2.micro**
   - Key pair: `kishan-key.pem` or create your own
   - Security Group: Allow the following **Inbound Rules**
     - SSH (port 22) — for terminal access
     - Custom TCP (port 8080) — for Jenkins web UI

---

## 💻 Step 2: Connect to EC2 via SSH

Open your terminal and run:

```bash
cd ~/Downloads  # or wherever the key is stored
chmod 400 kishan-key.pem
ssh -i "kishan-key.pem" ubuntu@<your-ec2-public-ip>
````

> Replace `<your-ec2-public-ip>` with your real EC2 public IP.

---

## ⚙️ Step 3: Install Jenkins

### Add Jenkins repo & key:

```bash
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

### Update system and install dependencies:

```bash
sudo apt update
sudo apt install -y openjdk-17-jdk
sudo apt install -y jenkins
```

### Start and enable Jenkins:

```bash
sudo systemctl enable jenkins
sudo systemctl start jenkins
```

---

## 🌐 Step 4: Access Jenkins from Browser

Open this in your browser:

```text
http://<your-ec2-public-ip>:8080
```

You’ll see the Jenkins unlock screen.

---

## 🔓 Step 5: Get Initial Jenkins Admin Password

Run this command to unlock:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Copy and paste the password into the Jenkins UI.

---

## 🎯 Step 6: Complete Setup in Web UI

1. Install **Suggested Plugins**
2. Create your admin user
3. Start using Jenkins 🎉

---

## 🛠 Useful Commands

| Task            | Command                               |
| --------------- | ------------------------------------- |
| Restart Jenkins | `sudo systemctl restart jenkins`      |
| Check status    | `systemctl status jenkins`            |
| Jenkins logs    | `journalctl -u jenkins -xe`           |
| Update packages | `sudo apt update && sudo apt upgrade` |

---

## 📝 Summary

You now have a publicly accessible Jenkins server on AWS. Save this `README.md` for future reference or share on GitHub.

---

## 📷 (Optional) Add Screenshots

* Jenkins Login Page
* Jenkins Dashboard
* EC2 Security Group Inbound Rules

---

✅ Done! You just learned how to **set up and deploy Jenkins on AWS EC2** and access it from anywhere in the world.

```

---

Would you like me to also generate this as a `.md` file and script to upload to GitHub for you?
```

