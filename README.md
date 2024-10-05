# Ansible-shutdown-instances
## Description
This Ansible project allows you to easily shut down AWS EC2 instances from your local machine. With a simple command, you can manage your cloud resources efficiently and ensure that your instances are safely powered down.

## Table of Contents
- [Installation](#installation)
- [Task1](#task1)
- [Task2](#task2)
- [Task3](#task3)
- [License](#license)
- [Contact](#contact)

## Installation
To install this project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/preethamkumarnp/Ansible-shutdown-instance.git



## Task1
Create three(3) EC2 instances on AWS using Ansible loops

2 Instances with Ubuntu Distribution
1 Instance with Centos Distribution
Hint: Use connection: local on Ansible Control node.

## Task2
Use the playbook creating-ec2.yml and change the image by looking selected distribution in AWS EC2
Then change the existing ami id with your distribustion ami id

## Task3
Use asible-vault module to secure your AWS ACCESS KEY and AWS SECRET KEY 
SETUP VAULT
1. Create a password for vault
   ```bash
   openssl rand -base64 2048 > vault.pass
2. Add your AWS credentials using the below vault command
   ```bash
   ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass  

## Task2
Set up passwordless authentication between Ansible control node and newly created instances.


## Task3
Automate the shutdown of Ubuntu Instances only using Ansible Conditionals

Hint: Use when condition on ansible gather_facts
