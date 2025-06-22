🛠️ Ansible Automated Deployment on AWS

🔍 Overview

This project showcases how to use Ansible for automating the configuration and deployment of a web application on AWS EC2 instances. The setup is integrated with GitHub Actions to create a CI/CD pipeline and includes a fault-tolerant architecture across multiple Availability Zones.

⚙️ Tech Stack

Tool

Purpose

Ansible

Automates server configuration & deployment

AWS EC2

Hosts the application

GitHub Actions

CI/CD pipeline automation

SSH Key

Secure access to EC2 instances

Amazon Linux 2

Target OS for Ansible playbooks

Route 53

Domain management

🌐 Architecture Highlights

Two EC2 web servers in different AZs (AZ1 & AZ2)

Two NAT Gateways for high availability

Bastion Host for secure SSH access to private instances

Security Groups configured to restrict and allow traffic as needed

Route 53 used to route a pre-owned domain name to the Load Balancer


🚀 What This Playbook Does

Installs system updates and required packages

Installs and configures Nginx (or Apache)

Deploys application files from a local directory or repo

Starts and enables the web service

Ensures idempotency — safe to run multiple times

🧪 How to Run

Update the inventory file with the public/private IP of your EC2 instance.

[web]
ec2-xx-xxx-xxx-xx.compute-1.amazonaws.com ansible_user=ec2-user ansible_ssh_private_key_file=~/.ssh/your-key.pem

Run the playbook:

ansible-playbook -i inventory.ini playbook.yml


🙌 Credits

Built by Tristan Jones🔗 LinkedIn💻 GitHub

🧠 Future Enhancements

Automate teardown with Ansible

Use dynamic inventory from AWS

Extend to include database tier automation

