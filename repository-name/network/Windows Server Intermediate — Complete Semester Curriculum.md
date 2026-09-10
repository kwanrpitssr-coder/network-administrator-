# WINDOWS SERVER INTERMEDIATE
## Windows Server Administration & Infrastructure Management

**Level:** Intermediate  
**Duration:** 16 Weeks  
**Class:** 4 Hours / Week  
**Total:** 64 Hours  
**Prerequisite:** Windows Server Basic  
**Lab Platform:** Hyper-V / VMware Workstation / VirtualBox  
**Windows Server:** Windows Server 2022 / Windows Server 2025  
**Windows Client:** Windows 10 / Windows 11  
**Teaching Language:** Khmer + English Technical Keywords

---

# 1. COURSE PURPOSE

Course នេះបន្តពី **Windows Server Basic** ទៅកាន់កម្រិត **Intermediate Administration**។

នៅ Basic សិស្សបានរៀន៖

```text
Windows Server
     ↓
Networking
     ↓
AD DS
     ↓
DNS
     ↓
DHCP
     ↓
Users / Groups / OU
     ↓
GPO
     ↓
File Server
     ↓
NTFS Permissions
```

នៅ Intermediate សិស្សនឹងរៀនពីរបៀប **Administer, Secure, Troubleshoot និង Manage** Windows Server Environment ដែលមាន Servers និង Clients ច្រើនជាងមុន។

គោលដៅ៖

```text
Configure
   ↓
Administer
   ↓
Secure
   ↓
Monitor
   ↓
Troubleshoot
   ↓
Automate
   ↓
Document
```

---

# 2. COURSE LEARNING OUTCOMES

នៅចុង Semester សិស្សអាច៖

- Manage **Active Directory Domain Services (AD DS)**
- Design advanced **Organizational Units (OU)**
- Manage **Users, Groups, and Computer Accounts**
- Apply advanced **Group Policy**
- Configure **DNS Zones and Records**
- Configure **DHCP Advanced Features**
- Manage **File Server / SMB**
- Configure advanced **NTFS Permissions**
- Understand **Storage Management**
- Configure **Disk, Volume, and Storage Spaces**
- Configure **IIS**
- Configure **Hyper-V**
- Manage Windows Server using **PowerShell**
- Configure **Remote Administration**
- Apply Windows Server Security
- Monitor Server Performance
- Analyze Windows Logs
- Perform Server Backup and Restore
- Troubleshoot Domain, DNS, DHCP, GPO, File and Network problems
- Design a small multi-server environment

---

# 3. SEMESTER STRUCTURE

| Week | Module | Main Topic | Practical Lab |
|---|---|---|---|
| 1 | M1 | Advanced AD DS Management | AD Administration |
| 2 | M2 | Users, Groups & Computer Management | Group-Based Management |
| 3 | M3 | Advanced OU & Delegation | AD Delegation |
| 4 | M4 | Advanced Group Policy | GPO Management |
| 5 | M5 | DNS Advanced Administration | DNS Management |
| 6 | M6 | DHCP Advanced Administration | DHCP Management |
| 7 | M7 | File Server & SMB Management | File Services |
| 8 | M8 | NTFS & Share Security | Permission Design |
| 9 | M9 | Storage Management | Disk / Volume |
| 10 | M10 | Storage Spaces | Storage Pool |
| 11 | M11 | IIS Web Server | Web Hosting |
| 12 | M12 | Hyper-V Virtualization | VM Management |
| 13 | M13 | PowerShell Administration | Server Automation |
| 14 | M14 | Remote Management & Security | Secure Administration |
| 15 | M15 | Monitoring, Backup & Troubleshooting | Fault Isolation |
| 16 | M16 | Capstone + Final Exam | Multi-Server Project |

---

# MODULE 1 — ADVANCED ACTIVE DIRECTORY MANAGEMENT

## Learning Objectives

សិស្សអាច៖

- Understand AD DS architecture
- Manage Domain Controllers
- Understand AD database
- Manage AD objects
- Understand Global Catalog
- Understand AD replication concepts

## Key Terms

`AD DS`  
`Domain Controller`  
`Active Directory Database`  
`Global Catalog`  
`Replication`  
`Forest`  
`Domain`  
`Site`

## Lecture Notes

Basic AD structure:

```text
Forest
   ↓
Domain
   ↓
OU
   ↓
Users / Groups / Computers
```

ក្នុង Intermediate សិស្សចាប់ផ្តើមយល់ថា **Active Directory** មិនមែនគ្រាន់តែជាកន្លែងបង្កើត User ទេ ប៉ុន្តែជាប្រព័ន្ធកណ្ដាលសម្រាប់ Identity និង Administration។

## PowerShell

Get AD Module:

```powershell
Get-Module -ListAvailable ActiveDirectory
```

List Users:

```powershell
Get-ADUser -Filter *
```

List Computers:

```powershell
Get-ADComputer -Filter *
```

List Groups:

```powershell
Get-ADGroup -Filter *
```

## Packet / Network Lab

```text
             DC1
              |
          ---------
          |       |
         PC1     PC2
```

Task:

- Manage AD objects
- Search users
- Search groups
- Search computers
- Verify Domain Controller

## Homework

Explain:

**Domain Controller vs Domain**

## Quiz

20 Questions

## Module Practical Exam

Perform basic AD administration using **GUI + PowerShell**.

---

# MODULE 2 — USERS, GROUPS & COMPUTER MANAGEMENT

## Learning Objectives

Students can:

- Create Users in bulk
- Disable Users
- Reset Passwords
- Create Security Groups
- Add Users to Groups
- Manage Computer Accounts

## Key Terms

`User Account`  
`Security Group`  
`Computer Account`  
`Group Membership`  
`Account Status`

## PowerShell

Create User:

```powershell
New-ADUser -Name "Student01" -SamAccountName "student01"
```

Enable:

```powershell
Enable-ADAccount student01
```

Disable:

```powershell
Disable-ADAccount student01
```

Add to Group:

```powershell
Add-ADGroupMember -Identity "Students" -Members "student01"
```

## Lab

Create:

```text
20 Users
5 Security Groups
10 Computer Accounts
```

Assign users into appropriate groups.

## Homework

Create a **Group Membership Matrix**.

| User | Group |
|---|---|
| Student01 | Students |
| Teacher01 | Teachers |
| Admin01 | IT-Admins |

## Quiz

15 Questions

## Module Practical Exam

Manage 20 users and group memberships.

---

# MODULE 3 — ADVANCED OU & DELEGATION

## Learning Objectives

Students can:

- Design OU hierarchy
- Move AD Objects
- Understand Delegation
- Delegate administrative tasks
- Separate user and computer policies

## Example

```text
school.local
│
├── Users
│   ├── Students
│   ├── Teachers
│   └── Staff
│
├── Computers
│   ├── Lab
│   ├── Office
│   └── IT
│
└── Servers
```

## Key Terms

`OU`  
`Delegation`  
`Object`  
`Inheritance`  
`Administrative Control`

## Lab

Create OU structure for:

**School / Company**

Then delegate selected administrative tasks.

## Homework

Design an OU structure for 500 users and 100 computers.

## Quiz

15 Questions

## Module Exam

OU Design + Delegation Practical.

---

# MODULE 4 — ADVANCED GROUP POLICY

## Learning Objectives

Students can:

- Create GPO
- Link GPO
- Understand GPO Scope
- Understand Inheritance
- Understand Security Filtering
- Troubleshoot GPO
- Use loopback concepts

## Key Terms

`GPO`  
`GPMC`  
`Inheritance`  
`Link`  
`Security Filtering`  
`Loopback Processing`

## Commands

```cmd
gpupdate /force
gpresult /r
gpresult /h report.html
```

PowerShell:

```powershell
Get-GPO -All
```

## Lab

Create:

```text
GPO 1 = Password Policy
GPO 2 = Student Restriction
GPO 3 = Software Policy
GPO 4 = Desktop Policy
GPO 5 = IT Admin Policy
```

Apply them to different OUs.

## Homework

Create a **GPO Design Matrix**.

## Quiz

20 Questions

## Module Practical Exam

Troubleshoot GPO not applying correctly.

---

# MODULE 5 — ADVANCED DNS ADMINISTRATION

## Learning Objectives

Students can:

- Manage DNS Zones
- Create DNS Records
- Understand Forward Lookup Zone
- Understand Reverse Lookup Zone
- Understand DNS Forwarders
- Troubleshoot Name Resolution

## Key Terms

`DNS`  
`Zone`  
`Forward Lookup Zone`  
`Reverse Lookup Zone`  
`A Record`  
`AAAA Record`  
`CNAME`  
`PTR`  
`Forwarder`

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
school.local
```

Records:

```text
dc1.school.local
web.school.local
fileserver.school.local
```

Create Reverse Lookup Zone.

## Homework

Design DNS naming structure for a company.

## Quiz

20 Questions

## Module Exam

DNS configuration + troubleshooting.

---

# MODULE 6 — ADVANCED DHCP

## Learning Objectives

Students can:

- Manage DHCP Scopes
- Configure Reservations
- Configure Exclusions
- Configure Options
- Configure DHCP Failover concepts
- Troubleshoot DHCP

## Key Terms

`DHCP`  
`Scope`  
`Lease`  
`Reservation`  
`Exclusion`  
`Option`  
`DHCP Failover`

## Commands

Client:

```cmd
ipconfig /release
ipconfig /renew
ipconfig /all
```

PowerShell:

```powershell
Get-DhcpServerv4Scope
Get-DhcpServerv4Lease
```

## Lab

Create:

```text
Scope 1 = ADMIN
Scope 2 = STUDENT
Scope 3 = LAB
```

Configure:

- Exclusions
- Reservation
- DNS option
- Default Gateway option

## Homework

Design DHCP plan for 300 clients.

## Quiz

15 Questions

## Module Exam

Configure multiple DHCP scopes.

---

# MODULE 7 — FILE SERVER & SMB MANAGEMENT

## Learning Objectives

Students can:

- Manage File Server
- Understand SMB
- Create Shares
- Manage folders
- Understand Access-Based concepts
- Manage File Server permissions

## Key Terms

`File Server`  
`SMB`  
`Share`  
`Shared Folder`  
`Access Control`

## PowerShell

Create Folder:

```powershell
New-Item -Path "D:\Company" -ItemType Directory
```

View SMB Shares:

```powershell
Get-SmbShare
```

Create Share:

```powershell
New-SmbShare -Name "Company" -Path "D:\Company"
```

## Lab

Create:

```text
D:\Company
 ├── ADMIN
 ├── HR
 ├── FINANCE
 └── IT
```

Publish as SMB Share.

## Homework

Design a company File Server structure.

## Quiz

15 Questions

---

# MODULE 8 — NTFS & SHARE SECURITY

## Learning Objectives

Students can:

- Understand NTFS Permissions
- Understand Share Permissions
- Use Security Groups
- Understand Inheritance
- Troubleshoot Permission Problems

## Permission Levels

```text
Read
Write
Modify
Full Control
```

## Security Design

```text
ADMIN → Full Control
HR → Modify
FINANCE → Modify
STUDENT → Read
```

## PowerShell

View ACL:

```powershell
Get-Acl "D:\Company"
```

## Lab

Create groups:

```text
GG-ADMIN
GG-HR
GG-FINANCE
GG-STUDENT
```

Assign correct permissions.

Test using different domain accounts.

## Homework

Create Permission Matrix.

## Quiz

20 Questions

## Module Practical Exam

Permission Troubleshooting Lab.

---

# MODULE 9 — STORAGE MANAGEMENT

## Learning Objectives

Students can:

- Understand Physical Disk
- Understand Partition
- Understand Volume
- Format volumes
- Assign Drive Letters
- Manage Disk Space

## Key Terms

`Disk`  
`Partition`  
`Volume`  
`File System`  
`NTFS`  
`Drive Letter`

## PowerShell

```powershell
Get-Disk
Get-Partition
Get-Volume
```

Create Partition:

```powershell
New-Partition
```

## Lab

Create:

```text
C: = OS
D: = Data
E: = Backup
```

## Homework

Design disk layout for a File Server.

## Quiz

15 Questions

---

# MODULE 10 — STORAGE SPACES

## Learning Objectives

Students can៖

- Understand Storage Pool
- Understand Virtual Disk
- Understand Storage Spaces
- Understand redundancy concepts

## Key Terms

`Storage Pool`  
`Virtual Disk`  
`Storage Space`  
`Resiliency`

## Lab

Use additional virtual disks:

```text
Disk 1
Disk 2
Disk 3
```

Create a Storage Pool and Virtual Disk.

## Homework

Explain:

**Disk vs Partition vs Volume vs Storage Space**

## Quiz

15 Questions.

## Module Exam

Storage Management Practical.

---

# MODULE 11 — IIS WEB SERVER

## Learning Objectives

Students can:

- Install **IIS**
- Create Website
- Configure Website Binding
- Understand HTTP/HTTPS
- Manage Website files
- Troubleshoot basic Web Server issues

## Key Terms

`IIS`  
`Web Server`  
`HTTP`  
`HTTPS`  
`Website`  
`Binding`  
`Port 80`  
`Port 443`

## PowerShell

Install IIS:

```powershell
Install-WindowsFeature Web-Server -IncludeManagementTools
```

Check IIS:

```powershell
Get-WindowsFeature Web-Server
```

## Lab

Create:

```text
Website:
www.school.local
```

Content:

```text
index.html
```

Test:

```text
http://www.school.local
```

## Homework

Create a simple company website structure.

## Quiz

15 Questions.

## Module Practical Exam

Deploy a basic IIS website.

---

# MODULE 12 — HYPER-V VIRTUALIZATION

## Learning Objectives

Students can:

- Explain Virtualization
- Explain Hyper-V
- Create Virtual Machine
- Configure Virtual Switch
- Manage VM Resources
- Create Checkpoints

## Key Terms

`Virtualization`  
`Hyper-V`  
`Virtual Machine (VM)`  
`Virtual Switch`  
`Virtual Hard Disk (VHDX)`  
`Checkpoint`

## PowerShell

Install Hyper-V:

```powershell
Install-WindowsFeature Hyper-V -IncludeManagementTools
```

List VMs:

```powershell
Get-VM
```

Start VM:

```powershell
Start-VM -Name "SRV1"
```

## Lab

Create:

```text
DC1
SRV1
SRV2
CLIENT1
```

Network:

```text
                 Virtual Switch
              /      |      |      \
            DC1     SRV1   SRV2   CLIENT1
```

## Homework

Compare:

**Physical Server vs Virtual Machine**

## Quiz

15 Questions.

## Module Exam

Create and manage VMs.

---

# MODULE 13 — POWERSHELL SERVER ADMINISTRATION

## Learning Objectives

Students can:

- Use PowerShell
- Find commands
- Manage services
- Manage processes
- Manage users
- Manage Windows Features
- Automate repetitive tasks

## Key Terms

`PowerShell`  
`Cmdlet`  
`Object`  
`Pipeline`  
`Variable`  
`Script`

## Commands

Find commands:

```powershell
Get-Command
```

Help:

```powershell
Get-Help Get-Service
```

Services:

```powershell
Get-Service
Start-Service
Stop-Service
Restart-Service
```

Processes:

```powershell
Get-Process
Stop-Process
```

Features:

```powershell
Get-WindowsFeature
```

## Lab

Write a PowerShell script that:

1. Creates 10 users.
2. Creates 3 groups.
3. Adds users to groups.
4. Creates folders.
5. Creates a shared folder.

## Homework

Write a PowerShell script for User Creation.

## Quiz

20 Questions.

## Module Practical Exam

Automation Task.

---

# MODULE 14 — REMOTE MANAGEMENT & SECURITY

## Learning Objectives

Students can:

- Understand Remote Administration
- Use RDP
- Understand Windows Firewall
- Use PowerShell Remoting
- Apply Server Hardening
- Secure Administrator Accounts

## Key Terms

`RDP`  
`PowerShell Remoting`  
`WinRM`  
`Windows Firewall`  
`Server Hardening`

## Commands

```powershell
Enable-PSRemoting
```

Test:

```powershell
Test-WSMan SRV1
```

Firewall:

```powershell
Get-NetFirewallProfile
```

## Lab

```text
ADMIN-PC
   |
   +---- RDP ----> SRV1
   |
   +---- PowerShell Remoting ----> SRV2
```

## Homework

Create a Server Security Checklist.

## Quiz

15 Questions.

## Module Exam

Secure and remotely manage two servers.

---

# MODULE 15 — MONITORING, BACKUP & TROUBLESHOOTING

## Learning Objectives

Students can:

- Monitor Server Performance
- Read Event Logs
- Monitor Services
- Perform Backup
- Restore Data
- Troubleshoot common infrastructure problems

## Key Terms

`Event Viewer`  
`Performance Monitor`  
`Task Manager`  
`Backup`  
`Restore`  
`Recovery`  
`Log`

## Commands

```powershell
Get-Service
Get-Process
Get-WinEvent
Get-ComputerInfo
```

## Troubleshooting Areas

```text
DNS Failure
DHCP Failure
Domain Login Failure
GPO Failure
File Permission Failure
SMB Failure
RDP Failure
Service Failure
```

## Lab

Instructor creates 10 faults.

Students must record:

```text
Problem
Evidence
Root Cause
Solution
Verification
```

## Homework

Write a professional Server Troubleshooting Report.

## Quiz

25 Scenario Questions.

## Module Practical Exam

Troubleshoot a broken Windows Server environment.

---

# MODULE 16 — CAPSTONE PROJECT

# MULTI-SERVER BUSINESS NETWORK

## Scenario

Company:

**ABC Technology School**

Departments:

```text
ADMIN
HR
FINANCE
IT
STUDENT
```

---

# Server Infrastructure

Students must create:

```text
             Network
                 |
              Switch
        _________|_________
       |         |         |
      DC1       SRV1      SRV2
       |         |         |
      AD DS     File      IIS
      DNS       Server    Web
      DHCP
```

## DC1

Services:

```text
AD DS
DNS
DHCP
```

## SRV1

Services:

```text
File Server
SMB
NTFS Permissions
```

## SRV2

Services:

```text
IIS
Web Server
```

## CLIENT1–CLIENT3

Must:

```text
Join Domain
Receive DHCP IP
Resolve DNS
Access File Server
Access Web Server
Apply GPO
```

---

# FINAL PROJECT REQUIREMENTS

## 1. Active Directory

Create:

```text
5 OUs
5 Groups
30 Users
```

## 2. DNS

Create:

```text
Forward Lookup Zone
Reverse Lookup Zone
A Records
CNAME
```

## 3. DHCP

Create:

```text
1–3 Scopes
Reservations
Exclusions
Options
```

## 4. GPO

Minimum:

```text
Password Policy
Desktop Policy
Student Restriction
Security Policy
```

## 5. File Server

Create:

```text
\\SRV1\Company
```

Folders:

```text
ADMIN
HR
FINANCE
IT
STUDENT
```

## 6. Permissions

Implement Group-based permissions.

## 7. IIS

Deploy:

```text
http://www.school.local
```

## 8. PowerShell

Create at least one administrative script.

## 9. Remote Management

Configure:

```text
RDP
PowerShell Remoting
```

## 10. Backup

Backup critical data and perform a restore test.

---

# FINAL EXAM

## PART A — THEORY

**80 Questions**

| Topic | Questions |
|---|---:|
| AD DS | 15 |
| Users/Groups/OU | 10 |
| Group Policy | 10 |
| DNS | 10 |
| DHCP | 10 |
| File Server/NTFS | 10 |
| Storage | 5 |
| IIS | 5 |
| Hyper-V | 5 |
| Security/Troubleshooting | 10 |
| **Total** | **90** |

---

# PART B — POWERSHELL

Students explain and use:

```powershell
Get-Command
Get-Help
Get-Service
Get-Process
Get-WindowsFeature
Get-NetIPConfiguration
Get-ADUser
Get-ADGroup
Get-ADComputer
Get-DnsServerZone
Get-DhcpServerv4Scope
Get-SmbShare
Get-Acl
```

---

# PART C — PRACTICAL EXAM

Starting from a prepared environment, students must:

```text
AD DS
 ↓
Users / Groups / OU
 ↓
DNS
 ↓
DHCP
 ↓
GPO
 ↓
File Server
 ↓
NTFS Permissions
 ↓
IIS
 ↓
Remote Management
 ↓
Backup
 ↓
Verification
```

---

# PART D — TROUBLESHOOTING EXAM

The instructor introduces faults such as:

```text
Client cannot join Domain
DNS resolution fails
DHCP not assigning IP
GPO not applying
User cannot access folder
SMB Share unavailable
IIS website unavailable
RDP unavailable
PowerShell Remoting fails
Service stopped
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

### Active Directory Design

Why were these OUs and Groups created?

### DNS Design

How does Name Resolution work?

### DHCP Design

How do Clients obtain their IP configuration?

### GPO Design

Which policies are applied and why?

### File Server

How are permissions controlled?

### IIS

How is the website published?

### Security

How is the Server protected?

### Troubleshooting

How was the problem diagnosed?

---

# 4. ASSESSMENT

| Assessment | Weight |
|---|---:|
| Homework | 10% |
| Weekly Quizzes | 10% |
| Practical Labs | 20% |
| Module Exams | 15% |
| Midterm | 10% |
| Capstone Project | 20% |
| Final Exam | 15% |
| **TOTAL** | **100%** |

---

# 5. INTERMEDIATE COMMAND CHECKLIST

## Networking

```powershell
ipconfig /all
ping
tracert
nslookup
Test-NetConnection
Get-NetIPConfiguration
```

## Active Directory

```powershell
Get-ADUser
Get-ADGroup
Get-ADComputer
New-ADUser
New-ADGroup
Add-ADGroupMember
Disable-ADAccount
Enable-ADAccount
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

## Storage

```powershell
Get-Disk
Get-Partition
Get-Volume
```

## Services

```powershell
Get-Service
Start-Service
Stop-Service
Restart-Service
```

## Monitoring

```powershell
Get-Process
Get-WinEvent
Get-ComputerInfo
```

## Remote Management

```powershell
Enable-PSRemoting
Test-WSMan
```

## Hyper-V

```powershell
Get-VM
Start-VM
Stop-VM
```

---

# 6. SKILL MATRIX

| Skill | Basic | Intermediate |
|---|---|---|
| Windows Server | Install | Manage |
| AD DS | Basic Domain | Advanced Administration |
| Users | Create | Bulk/Group Management |
| Groups | Basic | Group-based Administration |
| OU | Basic | Design/Delegation |
| GPO | Basic | Advanced Management |
| DNS | Basic | Advanced Troubleshooting |
| DHCP | Basic | Multiple Scopes |
| File Server | Basic Share | Advanced Permissions |
| Storage | Basic Disk | Storage Management |
| IIS | — | Web Server |
| Hyper-V | — | Virtualization |
| PowerShell | Basic Commands | Automation |
| Security | Basic | Server Hardening |
| Backup | Basic | Restore/Recovery |
| Troubleshooting | Basic | Infrastructure Troubleshooting |

---

# 7. GRADUATION STANDARD

សិស្សត្រូវអាចធ្វើបានដោយខ្លួនឯង៖

```text
[✓] Manage Active Directory
[✓] Manage Users
[✓] Manage Groups
[✓] Design OU
[✓] Delegate Administration
[✓] Manage GPO
[✓] Manage DNS
[✓] Manage DHCP
[✓] Manage File Server
[✓] Configure NTFS Permissions
[✓] Manage Storage
[✓] Deploy IIS
[✓] Manage Hyper-V
[✓] Use PowerShell
[✓] Configure Remote Management
[✓] Apply Server Security
[✓] Backup / Restore
[✓] Troubleshoot Server Infrastructure
```

---

# 8. LEARNING PATH

```text
WINDOWS SERVER BASIC
        ↓
Server Installation
        ↓
Networking
        ↓
AD DS
        ↓
DNS
        ↓
DHCP
        ↓
Users / Groups / OU
        ↓
GPO
        ↓
File Server
        ↓
NTFS Permissions
        ↓

WINDOWS SERVER INTERMEDIATE
        ↓
Advanced AD DS
        ↓
Advanced GPO
        ↓
Advanced DNS
        ↓
Advanced DHCP
        ↓
File Server Management
        ↓
NTFS Security
        ↓
Storage
        ↓
IIS
        ↓
Hyper-V
        ↓
PowerShell
        ↓
Remote Management
        ↓
Security
        ↓
Monitoring
        ↓
Backup
        ↓
Troubleshooting
        ↓
Multi-Server Capstone
```

---

# 9. TARGET SKILL

នៅចុង Intermediate Level សិស្សមិនគួរត្រឹមតែអាច **Install Windows Server** ទេ។

ពួកគេគួរអាចទទួលបាន Scenario មួយដូចជា៖

```text
Company Requirements
        +
Users
        +
Departments
        +
Network
        +
Security
        +
Services
```

ហើយបង្កើតជា៖

```text
AD DS Design
+
DNS Design
+
DHCP Design
+
GPO Design
+
File Server
+
IIS
+
Security
+
Backup
+
PowerShell Automation
+
Troubleshooting
```

គោលដៅចុងក្រោយគឺឱ្យសិស្សអាចធ្វើការងារបែប **Junior Windows Server Administrator / Junior System Administrator** បាន។