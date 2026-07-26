# AWS VPC with Public and Private Subnets

## Project Overview

This project demonstrates a highly available and secure AWS infrastructure deployed across two Availability Zones (AZs). The architecture uses both public and private subnets. Public subnets host the Application Load Balancer (ALB) and NAT Gateways, while private subnets host the EC2 application servers. The EC2 instances are managed by an Auto Scaling Group (ASG) to ensure high availability and automatic scaling based on demand.

Traffic from users reaches the Application Load Balancer, which distributes requests to EC2 instances in the private subnets. The EC2 instances securely access the internet through the NAT Gateway. An Amazon S3 Gateway Endpoint enables private connectivity to Amazon S3 without using the public internet.

---

## AWS Services Used

- Amazon VPC
- Public & Private Subnets
- Internet Gateway (IGW)
- NAT Gateway
- Application Load Balancer (ALB)
- Amazon EC2
- Auto Scaling Group (ASG)
- Security Groups
- Route Tables
- Amazon S3
- VPC Gateway Endpoint (S3)
- Elastic IP

---

## Project Architecture

![VPC Architecture](vpc-architecture.png.jpeg)

---

## Implementation Steps

1. Created a VPC with a custom CIDR block.
2. Created two public subnets and two private subnets across two Availability Zones.
3. Attached an Internet Gateway to the VPC.
4. Configured public and private route tables.
5. Associated subnets with their respective route tables.
6. Allocated Elastic IPs and created NAT Gateways in the public subnets.
7. Added default routes from private subnets to the NAT Gateways.
8. Created an Amazon S3 Gateway Endpoint and associated it with the private route tables.
9. Created Security Groups for the Load Balancer and EC2 instances.
10. Launched an EC2 instance and installed the web application.
11. Created an AMI from the configured EC2 instance.
12. Created a Launch Template using the AMI.
13. Created an Auto Scaling Group across both private subnets.
14. Created an Application Load Balancer in the public subnets.
15. Configured a Target Group and attached the Auto Scaling Group.
16. Verified application access using the Load Balancer DNS name.
17. Tested Auto Scaling and High Availability by stopping an EC2 instance and verifying automatic replacement.

---

## Project Screenshots

Project screenshots are available in the **screenshots** folder.

---

## Learning Outcomes

After completing this project, I was able to:

- Design a secure AWS network using Amazon VPC.
- Configure public and private subnets.
- Understand the purpose of Internet Gateway and NAT Gateway.
- Deploy EC2 instances in private subnets.
- Configure an Application Load Balancer for traffic distribution.
- Implement Auto Scaling for high availability.
- Configure Security Groups and Route Tables.
- Enable private access to Amazon S3 using a Gateway Endpoint.
- Build a production-style, highly available AWS architecture.
- Gain practical hands-on experience with AWS networking and services.
