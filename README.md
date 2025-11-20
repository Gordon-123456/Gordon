# Standard Operating Procedure (SOP)
## Setup a Virtual Linux Server for Web Application Test
**Version:** 1.0
**Date:** 2025-11-19
**Author:** Enping Zhou

---

## Purpose
The purpose of this SOP is to show simple steps how I create a Linux virtual machine for basic web application testing.
Because I am still learning, this SOP is written in an easy way so beginners can also follow.

---

## Scope
This SOP is for students or anyone who needs to set up a small Linux test server on VMware vSphere.
It includes how to create the VM, install Ubuntu, and install some basic tools for web testing.

---

## Accountability Matrix
| Task          | Person       |
|---------------|--------------|
| Create VM     | Student / Admin |
| Install OS    | Student      |
| Install packages | Student    |
| Documentation | Student      |

---

## Approval Table

| Name | Role | Date | Version |
|------|------|------|--------|
| Enping Zhou | Author | 2025-11-19 | 1.0 |
| Felix Liang | Reviewer | 2025-11-20 | 1.1 |
| Felix Liang | Approver | 2025-11-20 | 1.1 |

---

## Definitions
- VM: virtual machine
- ISO: installation image
- vSphere: VMware management web portal
- SSH: remote login tool for Linux

---

## Procedure Steps
### Step 1: Plan the VM
Before creating the virtual machine, decide some simple settings:
- OS: Ubuntu Server 22.04 LTS
- CPU: 2 vCPUs
- RAM: 4 GB
- Disk: 40 GB
- Network: DHCP is fine
- Hostname: webtest-ubuntu01
These settings are enough for a small testing server.

### Step 2: Create VM in VMware vSphere
1. Log in to the vSphere web page.
2. Right-click the ESXi host → New Virtual Machine.
3. Choose Create a new virtual machine.
4. Name the VM: linux-webtest-01
5. Select:
   - Guest OS: Ubuntu 64-bit
   - CPU: 2
   - RAM: 4 GB
   - Disk: 40 GB
6. Attach the Ubuntu 22.04 ISO to the virtual CD-ROM.
7. Click Finish to create the VM.

### Step 3: Install Ubuntu Server
1. Power on the VM and open console.
2. Select Install Ubuntu Server.
3. Use default language and keyboard.
4. Network: use DHCP or set a simple static IP.
5. Create your username and password.
6. Select OpenSSH Server (important for remote access).
7. Finish installation and reboot.

### Step 4: Basic System Setup
#### Update system
```bash
sudo apt update && sudo apt upgrade -y
```
#### Install VMware tools
```bash
sudo apt install open-vm-tools -y
```
#### Check network
```bash
ping -c 3 google.com
```
If ping works, the server is online.

### Step 5: Install Tools for Web Testing
#### Install Apache
```bash
sudo apt install apache2 -y
```
#### Install Python and Node.js
```bash
sudo apt install python3 python3-pip -y
sudo apt install nodejs npm -y
```
#### Install Git
```bash
sudo apt install git -y
```

### Step 6: Test the Server
#### Test Apache
```bash
curl http://localhost
```
If you see HTML output, Apache is running.

#### Test SSH
From another computer:
```bash
ssh youruser@server-ip
```
#### Check versions
```bash
node -v
python3 --version
```
If versions show, installation is OK.

### Step 7: Record Information
For future testing, write down:
- VM name
- IP address
- Login username
- Installed tools
- Any special settings
This helps if you need to rebuild or troubleshoot later.

---

## Revision History
| Version | Date       | Changes Made By |
|---------|------------|-----------------|
| 1.0     | 2025-11-19 | Enping Zhou |
| 1.1     | 2025-11-20 | Felix Liang |
