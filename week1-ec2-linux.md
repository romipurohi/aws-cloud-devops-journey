# Week 1 – EC2 & Linux Fundamentals

## 1. EC2 Configuration

- Region: ap-south-1 (Mumbai)
- AMI: Amazon Linux 2023
- Instance Type: t2.micro (Free Tier)
- Storage: 8 GB gp2
- Key Pair: cloud-journey-key.pem

## 2. Security Group Configuration

Inbound Rules:
- SSH (22) → My IP only
- HTTP (80) → 0.0.0.0/0

No outbound changes (default allow all).

## 3. SSH Connection

Command used:

ssh -i cloud-journey-key.pem ec2-user@<public-ip>

## 4. Web Server Installation

Commands executed:

sudo yum update -y  
sudo yum install nginx -y  
sudo systemctl start nginx  
sudo systemctl enable nginx  

Verified using:
- systemctl status nginx
- Accessed http://<public-ip> in browser

## 5. Service Testing

Tested service behavior:

Stopped service:
sudo systemctl stop nginx

Started service:
sudo systemctl start nginx

## 6. Key Learnings

- Security Groups act as virtual firewalls
- EC2 public IP allows direct internet access
- systemctl manages background services
- If service stops, website becomes unavailable
- SSH key permission must be 400

## 7. Real-World Relevance

This setup simulates:
- Basic production web server
- Public-facing application server
- Manual service management