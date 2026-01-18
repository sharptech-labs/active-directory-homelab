# Active Directory Home Lab (2026)
*A complete, step-by-step lab environment for learning and practicing real Active Directory administration at home.*

<br>

## Overview

This repository provides a fully documented, reproducible Active Directory home lab designed for anyone who wants hands-on experience with Windows Server, domain services, and real IT administration workflows.

Every module includes:

- Clear step-by-step instructions  
- Screenshots for every major action  
- Realistic configuration tasks  
- A structure that mirrors real helpdesk and sysadmin work  

This lab is also part of my own ongoing skill development as I strengthen my Active Directory, Windows Server, and general IT administration experience.

<br>

## Who This Lab Is For

- Beginners who want a guided, safe environment to learn AD  
- Helpdesk / IT Support candidates preparing for interviews  
- Students building practical experience for their resume  
- Anyone who wants to understand how Windows domains actually work  
- Home lab builders who want a clean, modular project to follow  

No prior AD experience is required — each module builds on the last.

<br>

## Lab Structure

### 01 — Windows Server 2022 VM Setup  
Prepare a Windows Server 2022 virtual machine in VirtualBox, install Guest Additions, and configure the environment for domain controller deployment.

### 02 — Windows 11 VM Setup  
Create a Windows 11 client VM, configure networking, bypass VirtualBox TPM limitations, and prepare it for domain joining.

### 03 — Active Directory Domain Services 
Install AD DS, promote the server to a domain controller, make first user, and create a shared folder.

### 04 — Join Windows 11 to the Domain   
Connect the client machine to the domain and validate authentication.

### 05 — User and Access Management  
Manage users, reset passwords, set logon hours, and account expiration.

### 06 — OUs, Groups, and Group Policy
Deploy and test GPOs, create security groups, and create log-in scripts.

### 07 — Helpdesk Ticket Simulations (Coming Soon)  
Troubleshoot realistic AD issues such as password resets, lockouts, DNS failures, and domain join errors.

### 08 — Patch Management (Coming Soon)  
Implement Action1, and patch deployment strategies to simulate real-world update management.

<br>

## Goals of This Project

- Build a complete, realistic Active Directory environment from scratch  
- Provide a free, open, step-by-step lab that anyone can follow  
- Strengthen my own skills in AD, Windows Server, and IT administration  
- Demonstrate hands-on technical ability through a public GitHub portfolio  
- Help others gain practical experience that translates directly to real IT roles  

<br>

## Technologies Used

- Windows Server 2022  
- Windows 11  
- Active Directory Domain Services  
- DNS, DHCP, NAT, Routing  
- VirtualBox  
- PowerShell  
- Guest Additions  

<br>

## Future Additions

- More ticket simulations  
- More advanced GPO scenarios  
- Security hardening  
- Backup and recovery  
- Multi-site domain replication  
- Optional Linux integration
- Reporting and audits  

<br>

## Contributions

This project is primarily a personal learning environment, but suggestions and improvements are welcome.