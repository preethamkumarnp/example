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
3. Add your AWS ACCESS KEY and AWS SECRET KEY to variables ec2_access_key and ec2_secret_key
   ```bash
   c2_access_key: <your access key>
   ec2_secret_key: <your secret key>

## Task4
1. Run the command 
   ```bash
        ansible-playbook creating-ec2.yml --vault-password-file vault.pass

Setting Up Passwordless Authentication for EC2 Instances

This section outlines how to set up passwordless SSH authentication for your EC2 instances, allowing you to connect securely without needing to enter a password.

### Using Public Key Authentication

1.  Using Public Key
    ```bash
      ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
   * ssh-copy-id: This is the command used to copy your public key to a remote machine.
   * -f: This flag forces the copying of keys, which can be useful if you have keys already set up and want to overwrite them.
   * "-o IdentityFile ": This option specifies the identity file (private key) to use for the connection. The -o flag passes this option to the underlying ssh command.
   * ubuntu@: This is the username (ubuntu) and the IP address of the remote server you want to access.
  
2.  Using Password
    * Go to the file /etc/ssh/sshd_config.d/60-cloudimg-settings.conf
    * Update PasswordAuthentication yes
    * Restart SSH -> sudo systemctl restart ssh


## Task5
   1. Create inventory.ini file and upload all the host created with ip address
   2. Create shutdown.yml file and and update the files with contents present in the repository 

Automate the shutdown of Ubuntu Instancees only using Ansible Conditionals

Hint: Use when condition on ansible gather_facts

## Final 
Run the ansible-playbook command to initiate the shutdown of Ubuntu instances 

```bash 
  ansible-playbook -i inventory shutdown.yml --vault-password-file vault.pass