# AWS-Windows-Server-Deployment
This project demonstrates how to deploy a Windows Server EC2 instance inside a public subnet on AWS, configure networking components such as VPC, subnets, route tables, and an Internet Gateway, and finally connect to the server from a macOS system using Remote Desktop (Windows App).
**#Project Overview**

The goal of this project is to set up a fully functional Windows Server on AWS and ensure it is accessible over the internet using RDP.
We create and configure:

-A custom VPC

-A public subnet

-Internet Gateway & Route Table

-A Windows Server EC2 instance

-Security Group allowing RDP (3389)

-RDP connection from macOS using the Windows App (Remote Desktop)

Steps Performed
1️⃣ Create VPC

CIDR Block: 10.0.0.0/16

This VPC holds all networking resources.

2️⃣ Create Public Subnet

Subnet CIDR: 10.0.1.0/24

Enabled Auto-assign Public IPv4 Address

3️⃣ Create Internet Gateway

Created an IGW named My-IGW

Attached it to the VPC

4️⃣ Add Route for Internet Access

Edited Route Table

Added route:
0.0.0.0/0 → Internet Gateway

This makes the subnet a public subnet

5️⃣ Launch Windows Server EC2 Instance

AMI: Windows Server (2022/2019)

Instance type: t2.micro (Free tier)

Placed inside the Public Subnet

Enabled Public IP

6️⃣ Configure Security Group

Inbound Rule:

Type	Port	Source
RDP	3389	My IP

This allows secure remote connection.

7️⃣ Retrieve Administrator Password

Go to EC2 → Select instance → Connect

Use RDP Client tab

Click Get Password

Upload .pem key to decrypt

8️⃣ Connect from macOS

Install Windows App (previously Microsoft Remote Desktop)

Add PC using EC2’s Public IPv4 address

Enter:

Username: Administrator

Password: decrypted password

You will now successfully access the server.
