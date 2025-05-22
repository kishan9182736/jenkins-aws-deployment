# jenkins-aws-deployment
A basic DevOps project deploying Jenkins CI/CD server on AWS EC2 instance.

# Jenkins Deployment on AWS EC2

This project demonstrates how to deploy a Jenkins CI/CD server on an AWS EC2 Ubuntu instance and access it publicly over the internet.

## 🚀 Steps Performed

1. Launched Ubuntu EC2 instance on AWS
2. Installed OpenJDK 17
3. Added Jenkins official GPG key & repo
4. Installed Jenkins
5. Opened port 8080 in AWS security group
6. Accessed Jenkins at `http://<your-ec2-ip>:8080`

## 🛠️ Tech Stack

- AWS EC2
- Ubuntu 24.04 LTS
- Jenkins 2.511
- OpenJDK 17
- SSH, systemctl, apt

## 🖼️ Screenshots

![Jenkins Installed](./screenshots/jenkins-installed.png)
![Jenkins Running](./screenshots/jenkins-browser-access.png)

## 💡 Next Steps

- Configure a sample CI/CD pipeline
- Connect GitHub repo to Jenkins
- Install Docker & build containerized apps
