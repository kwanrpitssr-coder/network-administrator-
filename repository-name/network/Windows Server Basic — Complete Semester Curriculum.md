# WINDOWS SERVER BASIC
## Windows Server Fundamentals & Basic Administration

**Level:** Basic / Beginner  
**Duration:** 16 Weeks  
**Class:** 4 Hours / Week  
**Total:** 64 Hours  
**Prerequisite:** Basic Computer + Basic Networking  
**Lab Platform:** Hyper-V / VMware Workstation / VirtualBox  
**Windows Server:** Windows Server 2022 / Windows Server 2025  
**Windows Client:** Windows 10 / Windows 11  
**Teaching Language:** Khmer + English Technical Keywords

---

# 1. COURSE PURPOSE

Course នេះរៀបចំសម្រាប់សិស្ស IT ដែលចាប់ផ្តើមសិក្សា **Windows Server** ពីកម្រិតមូលដ្ឋាន។

សិស្សនឹងរៀនពី៖

```text
Computer Fundamentals
        ↓
Networking Basics
        ↓
Windows Server
        ↓
Server Installation
        ↓
TCP/IP
        ↓
DNS
        ↓
DHCP
        ↓
Active Directory
        ↓
Users / Groups / OU
        ↓
Domain Join
        ↓
Group Policy
        ↓
File Server
        ↓
NTFS Permissions
        ↓
Remote Administration
        ↓
Security
        ↓
Backup
        ↓
Troubleshooting
        ↓
Final Project
```

---

# 2. COURSE LEARNING OUTCOMES

នៅចុង Semester សិស្សអាច៖

- Explain **Server** និង **Client-Server Model**
- Explain **Workgroup vs Domain**
- Install Windows Server in a **Virtual Machine (VM)**
- Configure **Hostname**
- Configure **Static IPv4**
- Configure **Default Gateway**
- Configure **DNS**
- Install **Server Roles and Features**
- Install **Active Directory Domain Services (AD DS)**
- Configure a **Domain Controller (DC)**
- Create **Users, Groups, and Organizational Units (OU)**
- Join Windows Client to a **Domain**
- Configure basic **DNS**
- Configure basic **DHCP**
- Create and apply basic **Group Policy Objects (GPO)**
- Create **File Server / SMB Share**
- Configure basic **NTFS Permissions**
- Use **Remote Desktop (RDP)**
- Perform Basic **Backup and Restore**
- Troubleshoot common Windows Server problems

---

# 3. SEMESTER STRUCTURE

| Week | Module | Main Topic | Practical Lab |
|---|---|---|---|
| 1 | M1 | Server & Networking Fundamentals | Client-Server Lab |
| 2 | M2 | Windows Server Installation | VM Installation |
| 3 | M3 | Initial Server Configuration | Hostname + IP |
| 4 | M4 | Windows Server Networking | TCP/IP Testing |
| 5 | M5 | Server Roles & Features | Role Installation |
| 6 | M6 | Active Directory Fundamentals | AD DS Installation |
| 7 | M7 | Users, Groups & OU | AD Object Management |
| 8 | M8 | Domain Join | Client → Domain |
| 9 | M9 | DNS Server Fundamentals | DNS Zone + Records |
| 10 | M10 | DHCP Server Fundamentals | DHCP Scope |
| 11 | M11 | Group Policy Fundamentals | Basic GPO |
| 12 | M12 | File Server & SMB | Shared Folder |
| 13 | M13 | NTFS & Share Permissions | Permission Lab |
| 14 | M14 | Remote Administration & Security | RDP + Firewall |
| 15 | M15 | Backup & Troubleshooting | Recovery Lab |
| 16 | M16 | Capstone + Final Exam | Complete Server Project |

---

# MODULE 1 — SERVER & NETWORKING FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain **Server**
- Explain **Client**
- Explain **Client-Server Model**
- Understand **LAN**
- Understand **IP Address**
- Understand **Subnet Mask**
- Understand **Default Gateway**
- Understand **DNS**
- Understand **DHCP**
- Understand **Workgroup vs Domain**

## Lecture Notes

### What is a Server?

**Server** គឺជា Computer ដែលផ្តល់ **Services** ឬ **Resources** ទៅកាន់ Client។

Examples:

```text
File Server
DNS Server
DHCP Server
Web Server
Database Server
Domain Controller
```

### Client-Server Model

```text
                 SERVER
        ┌────────────────────┐
        │ AD DS              │
        │ DNS                │
        │ DHCP               │
        │ File Server        │
        └─────────┬──────────┘
                  │
         ┌────────┼────────┐
         │        │        │
        PC1      PC2      PC3
```

## Key Terms

`Server`  
`Client`  
`Service`  
`Resource`  
`Workgroup`  
`Domain`  
`IP Address`  
`DNS`  
`DHCP`

## Commands

```cmd
ipconfig
ping
tracert
nslookup
```

## Packet Tracer / Network Lab

> **Note:** Packet Tracer មិនមែនជា Windows Server Lab ទេ។ ប្រើវាតែសម្រាប់បង្ហាញ Basic Network Concept។ Windows Server Practical ត្រូវប្រើ VM។

Topology:

```text
PC1 ---- Switch ---- Server
```

Task:

1. Configure IP.
2. Test connectivity.
3. Explain Client vs Server.

## Homework

សរសេរ Function របស់៖

- DNS Server
- DHCP Server
- File Server
- Web Server
- Domain Controller

## Quiz

**10 Questions**

## Module Practical Exam

Build a basic Client-Server network and verify connectivity.

---

# MODULE 2 — WINDOWS SERVER INSTALLATION

## Learning Objectives

សិស្សអាច៖

- Explain Windows Server
- Create a **Virtual Machine**
- Select VM Resources
- Install Windows Server
- Understand **Server Core**
- Understand **Desktop Experience**

## Key Terms

`Windows Server`  
`Virtual Machine (VM)`  
`ISO`  
`Server Core`  
`Desktop Experience`  
`Virtual Disk`  
`Virtual Network Adapter`

## Recommended VM

```text
CPU: 2 vCPU
RAM: 4–8 GB
Disk: 60 GB+
Network Adapter: 1
```

## Lab

Create:

```text
VM Name: SRV1
Hostname: SRV1
OS: Windows Server
```

Install Windows Server.

## Homework

Compare:

```text
Server Core
vs
Desktop Experience
```

## Quiz

15 Questions

## Module Practical Exam

Install Windows Server successfully.

---

# MODULE 3 — INITIAL SERVER CONFIGURATION

## Learning Objectives

សិស្សអាច៖

- Change **Computer Name**
- Configure **Static IPv4**
- Configure **Subnet Mask**
- Configure **Default Gateway**
- Configure **DNS Server**
- Check server configuration

## PowerShell Commands

Check configuration:

```powershell
Get-NetIPConfiguration
```

Check hostname:

```powershell
hostname
```

Rename:

```powershell
Rename-Computer -NewName "SRV1"
```

IP information:

```powershell
ipconfig /all
```

## Lab

Configure:

```text
Hostname: SRV1

IP Address:
192.168.10.10

Subnet Mask:
255.255.255.0

Default Gateway:
192.168.10.1

DNS:
192.168.10.10
```

Test:

```cmd
ping 192.168.10.1
```

## Homework

Create an **IP Addressing Table**.

## Quiz

15 Questions

## Module Practical Exam

Configure a Server from a blank installation.

---

# MODULE 4 — WINDOWS SERVER NETWORKING BASICS

## Learning Objectives

សិស្សអាច៖

- Understand **TCP/IP**
- Understand IPv4
- Understand Subnet Mask
- Understand DNS Resolution
- Test network connectivity
- Troubleshoot basic network problems

## Key Terms

`TCP/IP`  
`IPv4`  
`Subnet Mask`  
`Default Gateway`  
`DNS Resolution`

## Commands

```cmd
ipconfig
ipconfig /all
ping
tracert
nslookup
```

PowerShell:

```powershell
Test-NetConnection
Get-NetIPConfiguration
```

## Lab

Topology:

```text
SRV1 ---- Switch ---- PC1
```

Tasks:

1. Configure IP.
2. Test Ping.
3. Test DNS.
4. Identify incorrect IP configuration.

## Troubleshooting

Check:

```text
IP Address
Subnet Mask
Default Gateway
DNS Server
Cable / Adapter
```

## Homework

10 Networking questions.

## Quiz

15 Questions

## Module Exam

Basic Windows Networking Configuration.

---

# MODULE 5 — SERVER ROLES & FEATURES

## Learning Objectives

សិស្សអាច៖

- Explain **Server Role**
- Explain **Feature**
- Install Roles
- Remove Roles
- Use **Server Manager**
- Use PowerShell to manage Features

## Common Roles

```text
AD DS
DNS Server
DHCP Server
File and Storage Services
Web Server (IIS)
```

## PowerShell

List Features:

```powershell
Get-WindowsFeature
```

Install DNS:

```powershell
Install-WindowsFeature DNS -IncludeManagementTools
```

Install DHCP:

```powershell
Install-WindowsFeature DHCP -IncludeManagementTools
```

## Lab

Install:

- DNS
- DHCP
- File Server

## Homework

Explain:

**Role vs Feature**

## Quiz

10 Questions

## Module Practical Exam

Install and verify Server Roles.

---

# MODULE 6 — ACTIVE DIRECTORY FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain **Active Directory**
- Explain **AD DS**
- Explain **Domain**
- Explain **Domain Controller**
- Understand **Forest**
- Understand **Organizational Unit (OU)**

## Key Terms

`Active Directory`  
`AD DS`  
`Domain`  
`Domain Controller (DC)`  
`Forest`  
`Tree`  
`Organizational Unit (OU)`

## PowerShell

Install AD DS:

```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

Create Domain:

```powershell
Install-ADDSForest -DomainName "school.local"
```

## Lab

Create:

```text
Domain:
school.local

Domain Controller:
DC1
```

Verify:

```text
DC1
 |
school.local
```

## Homework

Draw:

```text
Forest
└── Domain
    ├── Users
    ├── Computers
    └── OUs
```

## Quiz

20 Questions

## Module Practical Exam

Install AD DS and promote the Server to Domain Controller.

---

# MODULE 7 — USERS, GROUPS & ORGANIZATIONAL UNITS

## Learning Objectives

សិស្សអាច៖

- Create **User Account**
- Create **Security Group**
- Create **OU**
- Move AD Objects
- Manage Group Membership

## Example OU Structure

```text
school.local
│
├── ADMIN
├── TEACHER
├── STUDENT
└── IT
```

## PowerShell

Create OU:

```powershell
New-ADOrganizationalUnit -Name "STUDENT"
```

Create User:

```powershell
New-ADUser -Name "Student01" -SamAccountName "student01"
```

Create Group:

```powershell
New-ADGroup -Name "Students" -GroupScope Global
```

Add User to Group:

```powershell
Add-ADGroupMember -Identity "Students" -Members "student01"
```

## Lab

Create:

```text
4 OUs
5 Groups
20 Users
```

## Homework

Design an OU structure for a school or company.

## Quiz

15 Questions

## Module Practical Exam

Create Users, Groups and OUs independently.

---

# MODULE 8 — WINDOWS CLIENT DOMAIN JOIN

## Learning Objectives

សិស្សអាច៖

- Configure Windows Client
- Configure Client DNS
- Join Client to a Domain
- Login using Domain Account
- Understand Computer Account

## Lab

Topology:

```text
               DC1
                |
              Switch
             /     \
           PC1     PC2
```

Domain:

```text
school.local
```

Join:

```text
PC1 → school.local
PC2 → school.local
```

Login:

```text
school\student01
```

## Troubleshooting Commands

```cmd
ipconfig /all
nslookup school.local
ping DC1
```

## Homework

Compare:

**Local Account vs Domain Account**

## Quiz

15 Questions

## Module Practical Exam

Join two Windows Clients to the Domain.

---

# MODULE 9 — DNS SERVER FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain **DNS**
- Create **Forward Lookup Zone**
- Understand **A Record**
- Understand **CNAME**
- Understand **PTR**
- Test DNS Resolution

## Key Terms

`DNS`  
`Forward Lookup Zone`  
`Reverse Lookup Zone`  
`A Record`  
`CNAME`  
`PTR`  
`Name Resolution`

## Commands

```cmd
nslookup
ipconfig /flushdns
ipconfig /registerdns
```

PowerShell:

```powershell
Get-DnsServerZone
Get-DnsServerResourceRecord
```

## Lab

Create:

```text
Zone:
school.local
```

Create A Record:

```text
server.school.local
192.168.10.10
```

Test:

```cmd
nslookup server.school.local
```

## Homework

Explain DNS Name Resolution.

## Quiz

20 Questions

## Module Exam

DNS Zone + Record + Troubleshooting.

---

# MODULE 10 — DHCP SERVER FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain **DHCP**
- Create **DHCP Scope**
- Configure IP Address Range
- Configure **Exclusion**
- Configure **Reservation**
- Configure basic DHCP Options

## Key Terms

`DHCP`  
`Scope`  
`Lease`  
`Reservation`  
`Exclusion`  
`Default Gateway`  
`DNS Server`

## Example

```text
Scope:
192.168.10.100 – 192.168.10.200

Gateway:
192.168.10.1

DNS:
192.168.10.10
```

## Client Commands

```cmd
ipconfig /release
ipconfig /renew
ipconfig /all
```

## Lab

Configure DHCP Scope.

Client should receive an IP automatically.

## Homework

Design DHCP Scope for 100 computers.

## Quiz

15 Questions

## Module Practical Exam

Configure DHCP and verify client lease.

---

# MODULE 11 — GROUP POLICY FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain **Group Policy**
- Create a **GPO**
- Link GPO to an OU
- Configure basic Password Policy
- Configure basic User/Computer Policies

## Key Terms

`GPO`  
`Group Policy`  
`GPMC`  
`OU`  
`Policy`

## Commands

Update Policy:

```cmd
gpupdate /force
```

Check Policy:

```cmd
gpresult /r
```

Create Report:

```cmd
gpresult /h report.html
```

## Lab

Create:

```text
GPO:
Student-Policy
```

Link to:

```text
OU:
STUDENT
```

Configure:

- Password Policy
- Desktop Restriction
- Control Panel Restriction

## Homework

Design 5 GPO Policies for Students.

## Quiz

15 Questions

## Module Practical Exam

Create and apply a basic GPO.

---

# MODULE 12 — FILE SERVER & SMB

## Learning Objectives

សិស្សអាច៖

- Explain **File Server**
- Explain **SMB**
- Create Shared Folder
- Create SMB Share
- Access Shared Folder from Client

## Key Terms

`File Server`  
`SMB`  
`Share`  
`Shared Folder`

## Folder Structure

```text
D:\Company
│
├── ADMIN
├── HR
├── FINANCE
└── IT
```

## PowerShell

Create Folder:

```powershell
New-Item -Path "D:\Company" -ItemType Directory
```

View Shares:

```powershell
Get-SmbShare
```

Create Share:

```powershell
New-SmbShare -Name "Company" -Path "D:\Company"
```

## Client Test

```text
\\SRV1\Company
```

## Homework

Design File Server folder structure for a company.

## Quiz

15 Questions

## Module Practical Exam

Create and access an SMB Share.

---

# MODULE 13 — NTFS & SHARE PERMISSIONS

## Learning Objectives

សិស្សអាច៖

- Explain **NTFS Permissions**
- Explain **Share Permissions**
- Understand **Read**
- Understand **Write**
- Understand **Modify**
- Understand **Full Control**
- Understand Permission Inheritance

## Key Terms

`NTFS`  
`Read`  
`Write`  
`Modify`  
`Full Control`  
`Inheritance`  
`Security Group`

## Example

| Group | Folder | Permission |
|---|---|---|
| ADMIN | ADMIN | Full Control |
| HR | HR | Modify |
| STUDENT | Public | Read |

## PowerShell

View ACL:

```powershell
Get-Acl "D:\Company"
```

## Lab

Create:

```text
GG-ADMIN
GG-HR
GG-STUDENT
```

Assign permissions and test using different users.

## Homework

Create a Permission Matrix.

## Quiz

20 Questions

## Module Practical Exam

Configure and troubleshoot NTFS + Share Permissions.

---

# MODULE 14 — REMOTE ADMINISTRATION & SECURITY

## Learning Objectives

សិស្សអាច៖

- Explain **Remote Desktop (RDP)**
- Enable RDP
- Understand Windows Firewall
- Manage Server remotely
- Understand Administrator Account
- Apply Basic Server Security

## Key Terms

`RDP`  
`Windows Firewall`  
`Remote Administration`  
`Administrator`  
`Security`

## PowerShell

Check Firewall:

```powershell
Get-NetFirewallProfile
```

Check Services:

```powershell
Get-Service
```

## Lab

```text
ADMIN-PC
    |
    └──── RDP ────> SRV1
```

Configure and test RDP.

## Homework

Create a Windows Server Security Checklist.

## Quiz

15 Questions

## Module Practical Exam

Connect to Server using RDP and verify Firewall configuration.

---

# MODULE 15 — BACKUP & TROUBLESHOOTING

## Learning Objectives

សិស្សអាច៖

- Explain **Backup**
- Explain **Restore**
- Understand **Recovery**
- Use **Event Viewer**
- Check Services
- Troubleshoot DNS
- Troubleshoot DHCP
- Troubleshoot Domain Login
- Troubleshoot File Permissions

## Key Terms

`Backup`  
`Restore`  
`Recovery`  
`Event Viewer`  
`Service`  
`Log`

## Useful Tools

```text
Event Viewer
Services
Task Manager
Disk Management
Server Manager
PowerShell
```

## Commands

```cmd
ipconfig /all
ping
nslookup
```

PowerShell:

```powershell
Get-Service
Get-WinEvent
Test-NetConnection
```

## Backup Lab

Create:

```text
D:\Important\Data.txt
```

Then:

```text
Backup
   ↓
Delete Data
   ↓
Restore
   ↓
Verify
```

## Troubleshooting Lab

Instructor creates:

```text
Problem 1 → Wrong IP
Problem 2 → DNS Failure
Problem 3 → DHCP Failure
Problem 4 → Domain Login Failure
Problem 5 → File Permission Failure
Problem 6 → Stopped Service
```

Students record:

```text
Problem
Evidence
Root Cause
Solution
Verification
```

## Homework

Write a Server Troubleshooting Report.

## Quiz

20 Scenario Questions.

## Module Practical Exam

Troubleshoot a broken Windows Server environment.

---

# MODULE 16 — FINAL PROJECT

# SMALL BUSINESS WINDOWS SERVER

## Scenario

Company:

**ABC Computer School**

Departments:

```text
ADMIN
HR
FINANCE
IT
STUDENT
```

---

# FINAL LAB TOPOLOGY

```text
                      Internet
                          |
                       Router
                          |
                       Switch
                    /     |     \
                  DC1    PC1    PC2
                          |
                         PC3
```

---

# SERVER REQUIREMENTS

DC1 provides:

```text
AD DS
DNS
DHCP
File Server
Group Policy
```

## IP Plan

```text
Network:
192.168.10.0/24

DC1:
192.168.10.10

Gateway:
192.168.10.1

DHCP:
192.168.10.100 - 192.168.10.200

DNS:
192.168.10.10

Domain:
abcschool.local
```

---

# FINAL PROJECT TASKS

## 1. Install Windows Server

## 2. Configure Hostname

```text
DC1
```

## 3. Configure Static IP

## 4. Install AD DS

## 5. Create Domain

```text
abcschool.local
```

## 6. Configure DNS

## 7. Configure DHCP

## 8. Create OUs

```text
ADMIN
HR
FINANCE
IT
STUDENT
```

## 9. Create Users and Groups

Minimum:

```text
20 Users
5 Groups
```

## 10. Join Windows Clients

Minimum:

```text
3 Windows Clients
```

## 11. Create GPO

Minimum:

```text
Password Policy
Student Policy
Desktop Policy
```

## 12. Create File Server

```text
\\DC1\Company
```

## 13. Configure NTFS Permissions

## 14. Configure RDP

## 15. Perform Backup

## 16. Test Everything

Students must demonstrate:

```text
Domain Login
DNS Resolution
DHCP Address
File Access
Group Policy
RDP
Backup / Restore
```

---

# FINAL EXAM

## PART A — THEORY

**50 Questions**

| Topic | Questions |
|---|---:|
| Server Fundamentals | 5 |
| Networking | 5 |
| Windows Server | 5 |
| AD DS | 10 |
| DNS | 5 |
| DHCP | 5 |
| Users / Groups / OU | 5 |
| Group Policy | 5 |
| File Server / NTFS | 5 |
| Security / Backup | 5 |
| **Total** | **55** |

---

# PART B — COMMANDS

Students explain:

```cmd
ipconfig
ipconfig /all
ipconfig /release
ipconfig /renew
ping
tracert
nslookup
```

PowerShell:

```powershell
Get-NetIPConfiguration
Test-NetConnection
Get-WindowsFeature
Get-Service
Get-WinEvent
Get-ADUser
Get-ADGroup
Get-ADComputer
Get-DnsServerZone
Get-SmbShare
Get-Acl
```

---

# PART C — PRACTICAL EXAM

Starting from a prepared environment, students must complete:

```text
Windows Server
      ↓
Hostname
      ↓
Static IP
      ↓
AD DS
      ↓
Domain
      ↓
DNS
      ↓
DHCP
      ↓
OU
      ↓
Users / Groups
      ↓
Domain Join
      ↓
GPO
      ↓
File Server
      ↓
NTFS Permissions
      ↓
RDP
      ↓
Backup
      ↓
Verification
```

---

# PART D — TROUBLESHOOTING EXAM

Instructor provides a broken environment.

Example:

```text
Client cannot join Domain
Client cannot resolve DNS
Client does not receive DHCP IP
User cannot login
User cannot access folder
GPO does not apply
RDP does not work
```

Students must:

```text
Identify
   ↓
Gather Evidence
   ↓
Find Root Cause
   ↓
Fix
   ↓
Verify
   ↓
Document
```

---

# PART E — FINAL PRESENTATION

Students explain:

### 1. Server Design

តើ Server មានតួនាទីអ្វី?

### 2. AD DS Design

ហេតុអ្វីត្រូវប្រើ Domain Controller?

### 3. DNS Design

DNS មានតួនាទីអ្វីនៅក្នុង Domain?

### 4. DHCP Design

តើ Client ទទួល IP ដោយរបៀបណា?

### 5. GPO Design

តើ Policy ត្រូវ Apply ទៅ User/Computer ណា?

### 6. File Server

តើ User ម្នាក់ៗមាន Permission អ្វី?

### 7. Security

តើ Server ត្រូវបានការពារដោយរបៀបណា?

### 8. Troubleshooting

តើបញ្ហាត្រូវបានរកឃើញ និងដោះស្រាយដោយរបៀបណា?

---

# 4. ASSESSMENT

| Assessment | Weight |
|---|---:|
| Homework | 10% |
| Weekly Quizzes | 10% |
| Practical Labs | 25% |
| Module Exams | 15% |
| Midterm | 10% |
| Final Project | 15% |
| Final Exam | 15% |
| **TOTAL** | **100%** |

---

# 5. BASIC COMMAND CHECKLIST

## Networking

```cmd
ipconfig
ipconfig /all
ipconfig /release
ipconfig /renew
ping
tracert
nslookup
```

## PowerShell

```powershell
Get-NetIPConfiguration
Test-NetConnection
Get-WindowsFeature
Get-Service
Get-WinEvent
```

## Active Directory

```powershell
Get-ADUser
Get-ADGroup
Get-ADComputer
New-ADUser
New-ADGroup
Add-ADGroupMember
```

## Group Policy

```cmd
gpupdate /force
gpresult /r
gpresult /h report.html
```

## DNS

```powershell
Get-DnsServerZone
Get-DnsServerResourceRecord
```

## DHCP

```powershell
Get-DhcpServerv4Scope
Get-DhcpServerv4Lease
```

## File Server

```powershell
Get-SmbShare
New-SmbShare
Get-Acl
```

## Services

```powershell
Get-Service
Start-Service
Stop-Service
Restart-Service
```

---

# 6. GRADUATION CHECKLIST

សិស្សត្រូវអាច៖

```text
[✓] Explain Server
[✓] Explain Client-Server Model
[✓] Install Windows Server
[✓] Create Virtual Machine
[✓] Configure Static IPv4
[✓] Configure DNS
[✓] Install Server Roles
[✓] Install AD DS
[✓] Create Domain
[✓] Manage Domain Controller
[✓] Create Users
[✓] Create Groups
[✓] Create OUs
[✓] Join Windows Client to Domain
[✓] Configure DHCP
[✓] Configure GPO
[✓] Create SMB Share
[✓] Configure NTFS Permissions
[✓] Use RDP
[✓] Perform Backup / Restore
[✓] Troubleshoot Basic Server Problems
```

---

# 7. COMPLETE WINDOWS SERVER LEARNING PATH

```text
WINDOWS SERVER BASIC
        ↓
Server Fundamentals
        ↓
Virtual Machine
        ↓
Windows Server Installation
        ↓
IPv4 / TCP-IP
        ↓
Server Roles
        ↓
AD DS
        ↓
Domain Controller
        ↓
Users / Groups / OU
        ↓
Domain Join
        ↓
DNS
        ↓
DHCP
        ↓
Group Policy
        ↓
File Server / SMB
        ↓
NTFS Permissions
        ↓
RDP / Security
        ↓
Backup
        ↓
Troubleshooting
        ↓
FINAL PROJECT
```

# 8. TARGET SKILL

នៅចុង Basic Level សិស្សគួរតែអាចទទួលបាន Scenario មួយ៖

```text
Company Requirements
       +
Users
       +
Computers
       +
Network
       +
Services
```

ហើយអាចបង្កើតបានជា៖

```text
Windows Server
+
Active Directory
+
DNS
+
DHCP
+
Group Policy
+
File Server
+
Permissions
+
Security
+
Backup
```

គោលដៅចុងក្រោយគឺឱ្យសិស្សអាចអនុវត្តការងារមូលដ្ឋានរបស់ **Junior Windows Server Administrator / Junior System Administrator**។