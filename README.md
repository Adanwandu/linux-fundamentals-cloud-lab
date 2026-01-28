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
- n 

## 1. Linux File System
Commands explored:
```bash
pwd
ls /
ls /var/log
