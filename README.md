# linux-fundamentals-cloud-lab
A beginner-friendly lab to practice Linux fundamentals: file system, permissions, services, SSH, package management, and logs.
This project is a beginner-friendly lab to practice Linux fundamentals. 
It covers 
- the Linux file system, 
- Users & permissions,
- Services,
- SSH access,
- Package management, and
- Log inspection.

The lab is done on a Linux VM using Multipass & SSH from MacOS simulating a real cloud server environment.

# Tools Used
- MacOS Terminal  
- Multipass (Ubuntu VM)  
- Linux commands: `ls` to list files and directories in the current location , `chmod` to change file or directory permissions, `chown` to change the owner and/or group of a file or directory, `systemctl` to manage system services and the systemd init system, `ssh` to securely connect to a remote machine over the network, `tail` to show the last part of a file, often used for logs, `journalctl` to view and query systemd logs.


## 1. Linux File System
Commands explored:
bash
pwd ![SSH Login Success](screenshots/ssh-login.png)
ls /
ls /var/log

## 2. Users & Permissions
User Creation
commands used
- sudo - super user do to take commands as roots
created a user called clouduser
- sudo adduser clouduser
- sudo usermod -aG sudo clouduser

# File Permissions
File permissions are used to control who can access a file or directory and what they’re allowed to do with it. In Linux (and Unix-like systems), they are a core security and access-control mechanism.

commands used
-  touch testfile.txt
- ls -l
- chmod 700 testfile.txt
- chown clouduser:clouduser testfile.txt

r = read, w = write, x = execute

## 3. Package Management
Package Management is how a Linux system installs, updates, configures, and removes software in a controlled, reliable way.

Think of it as the operating system’s official app store + installer + updater, all in one.

Update system packages:
commands used
- sudo apt update
- sudo apt install nginx -y - install package
nginx -v
apt update refreshes available package versions
apt install installs software

## 4. 4. Services
Manage system services
commands used:  
- sudo systemctl start nginx
- sudo systemctl enable nginx
- sudo systemctl status nginx

## 5. SSH Access
Step 1 — Generate SSH Key on Mac 
ssh-keygen -t ed2***
* Private key stays on Mac (~/.ssh/id_ed2***)
* Public key goes to the server (~/.ssh/id_ed2***.pub)

Step 2 — Set Up the User on VM
sudo mkdir -p /home/clouduser/.ssh
sudo chown clouduser:clouduser /home/clouduser/.ssh
sudo chmod 600 /home/clouduser/.ssh

Step 3 — Add Public Key
Paste Mac public key into: /home/clouduser/.ssh/authorized_keys
commands  used:
sudo chown clouduser:clouduser /home/clouduser/.ssh/authorized_keys
sudo chmod 600 /home/clouduser/.ssh/authorized_keys

Step 4 — Test SSH Login
command used:
- ssh -i ~/.ssh/"filename" clouduserr@192.168.64.7

## 6. Logs & Troubleshooting
View logs for the system, authentication, and services:
commands used
- sudo tail /var/log/syslog
- sudo tail /var/log/auth.log
- journalctl -u nginx
- sudo grep "error" /var/log/syslog

syslog → general system messages
auth.log → login attempts and security events
journalctl -u <service> → service-specific logs
grep → filter for errors

7. Challenges & Learnings
SSH public/private key confusion → solved by using private key with correct permissions
Understanding Linux file permissions and ownership
Using Multipass to simulate cloud VM access
Key-based authentication allows secure, passwordless login
