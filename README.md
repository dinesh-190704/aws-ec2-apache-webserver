Static Website Hosting on AWS EC2 (Red Hat + Apache)
📌 Project Overview

This project demonstrates how to deploy and host a static website on AWS EC2 using a Red Hat Enterprise Linux (RHEL) instance and the Apache HTTP Server. The implementation follows AWS best practices for compute provisioning, security, and basic cost awareness, using services available under the AWS Free Tier.

🛠️ Technologies & Services Used

AWS EC2 (t3.micro – Free Tier eligible)

Red Hat Enterprise Linux (RHEL)

Apache HTTP Server (httpd)

AWS Security Groups

SSH (Key Pair authentication)

Linux System Administration

🧱 Architecture

User
⬇
Public Internet
⬇
AWS EC2 (RHEL)
⬇
Apache Web Server
⬇
Static Website Content

⚙️ Implementation Steps
1. EC2 Instance Creation

Launched an EC2 instance with:

Instance Type: t3.micro

AMI: Red Hat Enterprise Linux

Network: Default VPC

Configured Security Group to allow:

HTTP (Port 80)

SSH (Port 22 – restricted)

2. Apache Web Server Installation
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

3. Website Deployment

Uploaded static website files to:

/var/www/html/


Set proper permissions:

sudo chown -R apache:apache /var/www/html

4. Accessing the Website

Website accessed via:

http://<EC2-Public-IP>


Verified successful deployment through browser.

🔐 Security Considerations

Used key-pair based SSH authentication

Limited inbound access using Security Groups

Avoided root login for routine operations

💰 Cost Management

Instance type selected under AWS Free Tier

EC2 instance stopped when not in use to avoid unnecessary charges

📈 Learning Outcomes

Practical understanding of AWS EC2 provisioning

Hands-on experience with Linux server administration

Apache web server installation and configuration

Basic AWS networking and security concepts

Real-world deployment of a static website

🚀 Future Enhancements

Attach Elastic IP

Configure IAM Role for EC2

Enable CloudWatch monitoring

Serve content via CloudFront CDN

Secure site using HTTPS (ACM + CloudFront)

📎 Author

Dinesh
Engineer – Cloud / AWS
GitHub: https://github.com/dinesh-190704
