# WINDOWS SERVER ADVANCED
## Advanced Windows Server Administration, Infrastructure, Security & High Availability

**Level:** Advanced  
**Duration:** 16 Weeks  
**Class:** 4 Hours / Week  
**Total:** 64 Hours  
**Prerequisite:** Windows Server Basic + Windows Server Intermediate  
**Lab Platform:** Hyper-V / VMware Workstation / VirtualBox  
**Windows Server:** Windows Server 2022 / Windows Server 2025  
**Windows Client:** Windows 10 / Windows 11  
**Teaching Language:** Khmer + English Technical Keywords  
**Main Focus:** Design + Deploy + Secure + Manage + Troubleshoot + Automate

---

# 1. COURSE PURPOSE

Course នេះបន្តពី **Windows Server Intermediate** ទៅកាន់កម្រិត **Advanced Server Administration**។

នៅ Basic សិស្សរៀន៖

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

នៅ Intermediate សិស្សបន្តទៅ៖

```text
Advanced AD DS
      ↓
Advanced GPO
      ↓
Advanced DNS / DHCP
      ↓
Storage
      ↓
IIS
      ↓
Hyper-V
      ↓
PowerShell
      ↓
Security
      ↓
Backup
      ↓
Troubleshooting
```

នៅ Advanced សិស្សត្រូវអាច៖

```text
Plan
  ↓
Design
  ↓
Deploy
  ↓
Configure
  ↓
Secure
  ↓
Monitor
  ↓
Automate
  ↓
Troubleshoot
  ↓
Recover
  ↓
Document
```

---

# 2. COURSE LEARNING OUTCOMES

នៅចុង Semester សិស្សអាច៖

- Design an advanced **Windows Server Infrastructure**
- Design and manage multi-server **Active Directory**
- Understand **AD DS Replication**
- Design **Active Directory Sites and Services**
- Manage multiple **Domain Controllers**
- Configure advanced **Group Policy**
- Design advanced **DNS Infrastructure**
- Configure secure and resilient **DHCP**
- Manage enterprise **File Server**
- Understand **DFS (Distributed File System)**
- Configure **DFS Namespace**
- Understand **Storage Replica**
- Configure advanced **Storage Spaces**
- Deploy and manage **IIS**
- Configure **Hyper-V Virtualization**
- Understand **Virtual Switches**
- Use advanced **PowerShell Automation**
- Configure **Windows Server Failover Clustering**
- Understand **High Availability**
- Configure **Windows Server Backup**
- Perform **Disaster Recovery**
- Monitor Server Performance
- Analyze Event Logs
- Implement Server Security
- Troubleshoot complex infrastructure problems
- Design a complete enterprise Windows Server environment

---

# 3. SEMESTER STRUCTURE

| Week | Module | Main Topic | Practical Lab |
|---|---|---|---|
| 1 | M1 | Advanced AD DS Architecture | Multi-DC Environment |
| 2 | M2 | AD DS Replication & Sites | Replication Lab |
| 3 | M3 | Advanced AD Management | Delegation & Administration |
| 4 | M4 | Advanced Group Policy | Enterprise GPO |
| 5 | M5 | Advanced DNS Infrastructure | DNS Design |
| 6 | M6 | Advanced DHCP & IP Services | DHCP Resilience |
| 7 | M7 | Advanced File Services | DFS / SMB |
| 8 | M8 | Enterprise Storage | Storage Spaces |
| 9 | M9 | DFS Namespace & File Services | Distributed File System |
| 10 | M10 | IIS Advanced | Web Application Hosting |
| 11 | M11 | Hyper-V Advanced | Virtualization Infrastructure |
| 12 | M12 | PowerShell Automation | Administration Scripts |
| 13 | M13 | Windows Server Security | Server Hardening |
| 14 | M14 | High Availability & Failover | Failover Clustering |
| 15 | M15 | Monitoring, Backup & DR | Recovery + Troubleshooting |
| 16 | M16 | Capstone + Final Exam | Enterprise Infrastructure |

---

# MODULE 1 — ADVANCED ACTIVE DIRECTORY ARCHITECTURE

## Learning Objectives

សិស្សអាច៖

- Understand advanced **AD DS Architecture**
- Understand **Domain Controller (DC)**
- Understand **Global Catalog (GC)**
- Understand **FSMO Roles**
- Understand AD DS database concepts
- Understand Multi-Domain architecture

## Key Terms

`AD DS`  
`Domain Controller`  
`Global Catalog`  
`FSMO`  
`Schema Master`  
`Domain Naming Master`  
`RID Master`  
`PDC Emulator`  
`Infrastructure Master`

## Lecture Notes

### FSMO Roles

```text
Forest-Wide
├── Schema Master
└── Domain Naming Master

Domain-Wide
├── RID Master
├── PDC Emulator
└── Infrastructure Master
```

## PowerShell

Check Domain Controller:

```powershell
Get-ADDomainController
```

Check FSMO:

```powershell
Get-ADForest
Get-ADDomain
```

## Lab

Create:

```text
DC1
DC2
```

Configure both as Domain Controllers.

Test:

- User Login
- DNS
- Authentication
- Replication

## Homework

Explain all 5 FSMO Roles.

## Quiz

20 Questions.

## Module Practical Exam

Deploy and verify a Multi-DC environment.

---

# MODULE 2 — AD DS REPLICATION & SITES

## Learning Objectives

សិស្សអាច៖

- Understand AD Replication
- Understand **Sites**
- Understand **Site Links**
- Understand replication behavior
- Troubleshoot replication problems

## Key Terms

`Replication`  
`Site`  
`Site Link`  
`Replication Partner`  
`Knowledge Consistency Checker (KCC)`

## Commands

Check DC:

```powershell
Get-ADDomainController -Filter *
```

Replication:

```cmd
repadmin /replsummary
repadmin /showrepl
```

Diagnostics:

```cmd
dcdiag
```

## Lab

Topology:

```text
SITE-A                  SITE-B

 DC1 ================= DC2
  |                     |
 PC1                   PC2
```

Configure Sites and test replication.

## Homework

Explain why AD Replication is important.

## Quiz

20 Questions.

## Module Practical Exam

Identify and troubleshoot a replication failure.

---

# MODULE 3 — ADVANCED AD MANAGEMENT & DELEGATION

## Learning Objectives

សិស្សអាច៖

- Design advanced OU structure
- Delegate administration
- Manage Service Accounts
- Manage Computer Accounts
- Understand least-privilege administration

## Key Terms

`Delegation`  
`Service Account`  
`Least Privilege`  
`Administrative Role`  
`Computer Account`

## PowerShell

Search users:

```powershell
Get-ADUser -Filter *
```

Search computers:

```powershell
Get-ADComputer -Filter *
```

Search groups:

```powershell
Get-ADGroup -Filter *
```

## Lab

Create:

```text
IT-Admins
Helpdesk
Teachers
Students
Server-Admins
```

Delegate selected management tasks.

## Homework

Create a Delegation Matrix.

| Team | Permission |
|---|---|
| Helpdesk | Reset User Password |
| IT-Admins | Manage Users |
| Server-Admins | Manage Servers |

## Quiz

15 Questions.

## Module Exam

Design OU + Delegation.

---

# MODULE 4 — ADVANCED GROUP POLICY

## Learning Objectives

សិស្សអាច៖

- Design Enterprise GPO
- Understand GPO Precedence
- Understand Inheritance
- Use Security Filtering
- Understand Loopback Processing
- Troubleshoot GPO

## Key Terms

`GPO`  
`GPMC`  
`Inheritance`  
`Enforced`  
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
GPO-SECURITY
GPO-STUDENT
GPO-ADMIN
GPO-SERVER
GPO-DESKTOP
```

Test policy precedence.

## Homework

Design an Enterprise GPO structure.

## Quiz

20 Questions.

## Module Practical Exam

Troubleshoot conflicting GPOs.

---

# MODULE 5 — ADVANCED DNS INFRASTRUCTURE

## Learning Objectives

សិស្សអាច៖

- Design DNS infrastructure
- Manage DNS Zones
- Understand Conditional Forwarders
- Understand DNS Forwarders
- Manage DNS Records
- Troubleshoot DNS

## Key Terms

`DNS`  
`Zone`  
`Forwarder`  
`Conditional Forwarder`  
`A Record`  
`AAAA Record`  
`CNAME`  
`PTR`  
`Dynamic Update`

## Commands

```powershell
Get-DnsServerZone
Get-DnsServerResourceRecord
```

DNS Cache:

```cmd
ipconfig /flushdns
```

DNS Test:

```cmd
nslookup
```

## Lab

Build:

```text
        DNS1
       /    \
    CLIENT  DNS2
```

Configure DNS redundancy.

## Homework

Design DNS architecture for an enterprise.

## Quiz

20 Questions.

## Module Exam

Advanced DNS Configuration + Troubleshooting.

---

# MODULE 6 — ADVANCED DHCP & IP SERVICES

## Learning Objectives

សិស្សអាច៖

- Design multiple DHCP scopes
- Configure Reservations
- Configure DHCP Options
- Understand DHCP Failover
- Troubleshoot DHCP

## Key Terms

`DHCP`  
`Scope`  
`Reservation`  
`Lease`  
`DHCP Failover`  
`Load Balance`  
`Hot Standby`

## Commands

```powershell
Get-DhcpServerv4Scope
Get-DhcpServerv4Lease
```

## Lab

Deploy:

```text
DHCP1
DHCP2
```

Configure DHCP Failover.

Test:

```text
DHCP1 OFF
    ↓
DHCP2
    ↓
Clients continue receiving service
```

## Homework

Compare:

**Load Balance vs Hot Standby**

## Quiz

15 Questions.

## Module Practical Exam

Configure and test DHCP resilience.

---

# MODULE 7 — ADVANCED FILE SERVICES

## Learning Objectives

សិស្សអាច៖

- Design enterprise File Server
- Manage SMB
- Manage file shares
- Use Security Groups for permissions
- Understand File Server resource management concepts
- Troubleshoot SMB

## Key Terms

`File Server`  
`SMB`  
`Share`  
`File Server Resource Manager (FSRM)`  
`Quota`  
`File Screening`

## Commands

```powershell
Get-SmbShare
Get-SmbSession
Get-SmbOpenFile
```

## Lab

Create:

```text
\\FS1\Company
```

Departments:

```text
ADMIN
HR
FINANCE
IT
PUBLIC
```

## Homework

Design enterprise file structure.

## Quiz

15 Questions.

## Module Exam

File Server administration.

---

# MODULE 8 — ENTERPRISE STORAGE

## Learning Objectives

សិស្សអាច៖

- Understand Storage Spaces
- Understand Storage Pool
- Understand Virtual Disk
- Understand Resiliency
- Plan Server Storage

## Key Terms

`Storage Pool`  
`Virtual Disk`  
`Storage Space`  
`Simple`  
`Mirror`  
`Parity`

## Commands

```powershell
Get-Disk
Get-PhysicalDisk
Get-StoragePool
Get-VirtualDisk
Get-Volume
```

## Lab

Create:

```text
Disk 1
Disk 2
Disk 3
Disk 4
```

Build a Storage Pool and Virtual Disk.

## Homework

Compare:

```text
Simple
Mirror
Parity
```

## Quiz

15 Questions.

## Module Exam

Storage Design + Practical.

---

# MODULE 9 — DFS NAMESPACE & DISTRIBUTED FILE SYSTEM

## Learning Objectives

សិស្សអាច៖

- Understand **DFS**
- Configure **DFS Namespace**
- Understand **DFS Replication (DFSR)**
- Provide centralized file access
- Understand distributed file services

## Key Terms

`DFS`  
`DFS Namespace`  
`DFS Replication`  
`Namespace Server`  
`Replication Group`

## Example

Instead of:

```text
\\FS1\HR
\\FS2\HR
```

Users access:

```text
\\school.local\Company\HR
```

## Lab

Servers:

```text
FS1
FS2
```

Create:

```text
\\school.local\Company
```

Replicate:

```text
HR
IT
ADMIN
```

## Homework

Explain the benefit of DFS Namespace.

## Quiz

15 Questions.

## Module Exam

DFS Configuration + Troubleshooting.

---

# MODULE 10 — IIS ADVANCED

## Learning Objectives

សិស្សអាច៖

- Deploy IIS
- Create Multiple Websites
- Configure Bindings
- Understand Application Pools
- Configure HTTPS concepts
- Monitor Websites

## Key Terms

`IIS`  
`Website`  
`Binding`  
`Application Pool`  
`HTTP`  
`HTTPS`  
`SSL/TLS`

## Commands

```powershell
Install-WindowsFeature Web-Server -IncludeManagementTools
```

IIS site management can be performed through:

```text
IIS Manager
PowerShell
```

## Lab

Deploy:

```text
www.school.local
www.company.local
```

Configure different bindings.

## Homework

Explain:

**Website vs Application Pool**

## Quiz

15 Questions.

## Module Practical Exam

Deploy multiple IIS websites.

---

# MODULE 11 — ADVANCED HYPER-V

## Learning Objectives

សិស្សអាច៖

- Understand Hyper-V Architecture
- Create Virtual Machines
- Configure Virtual Switches
- Configure Virtual Hard Disks
- Manage VM resources
- Use Checkpoints appropriately

## Key Terms

`Hyper-V`  
`VM`  
`Virtual Switch`  
`VHDX`  
`Generation 1`  
`Generation 2`  
`Checkpoint`

## PowerShell

```powershell
Get-VM
Get-VMSwitch
Get-VMNetworkAdapter
```

Start VM:

```powershell
Start-VM -Name "DC1"
```

## Lab

Build:

```text
          Virtual Switch
        /      |      |      \
      DC1     SRV1   SRV2   CLIENT1
```

## Homework

Design a Hyper-V Lab Environment.

## Quiz

15 Questions.

## Module Exam

Deploy and manage multiple VMs.

---

# MODULE 12 — POWERSHELL AUTOMATION

## Learning Objectives

សិស្សអាច៖

- Write PowerShell Scripts
- Use Variables
- Use Conditions
- Use Loops
- Use Functions
- Automate User Creation
- Automate Server Administration

## Key Terms

`PowerShell`  
`Cmdlet`  
`Object`  
`Pipeline`  
`Variable`  
`Loop`  
`Function`  
`Script`

## Commands

```powershell
Get-Command
Get-Help
Get-Service
Get-Process
```

## Example

```powershell
$Users = "Student01","Student02","Student03"

foreach ($User in $Users) {
    New-ADUser -Name $User -SamAccountName $User
}
```

## Lab

Create a script that:

```text
Create Users
Create Groups
Add Users to Groups
Create Folders
Create Shares
Generate Report
```

## Homework

Create a User Provisioning Script.

## Quiz

20 Questions.

## Module Practical Exam

Automation Challenge.

---

# MODULE 13 — WINDOWS SERVER SECURITY & HARDENING

## Learning Objectives

សិស្សអាច៖

- Apply Server Hardening
- Secure Administrator Accounts
- Configure Windows Firewall
- Secure RDP
- Understand Least Privilege
- Understand Security Auditing
- Understand Security Logs

## Key Terms

`Hardening`  
`Least Privilege`  
`Windows Defender`  
`Windows Firewall`  
`Auditing`  
`Security Log`

## Commands

Firewall:

```powershell
Get-NetFirewallProfile
```

Security Events:

```powershell
Get-WinEvent -LogName Security
```

Services:

```powershell
Get-Service
```

## Lab

Apply:

```text
Strong Password
Firewall
Restricted RDP
Limited Admin Access
Auditing
Account Lockout Policy
```

## Homework

Create an Advanced Server Hardening Checklist.

## Quiz

20 Questions.

## Module Practical Exam

Harden a Windows Server.

---

# MODULE 14 — HIGH AVAILABILITY & FAILOVER CLUSTERING

## Learning Objectives

សិស្សអាច៖

- Understand High Availability
- Identify Single Point of Failure
- Understand Failover Clustering
- Understand Cluster Nodes
- Understand Clustered Roles
- Test Failover

## Key Terms

`High Availability`  
`Failover`  
`Failover Cluster`  
`Cluster Node`  
`Clustered Role`  
`Quorum`

## Architecture

```text
             CLIENTS
                |
          Cluster Network
           /           \
        NODE1          NODE2
           \           /
            Shared Storage
```

## Lab

Build a basic Failover Cluster lab.

Test:

```text
NODE1 ONLINE
    ↓
NODE1 FAILURE
    ↓
NODE2 TAKES OVER
```

## Homework

Explain:

**High Availability vs Backup**

## Quiz

20 Questions.

## Module Exam

Failover and High Availability scenario.

---

# MODULE 15 — MONITORING, BACKUP & DISASTER RECOVERY

## Learning Objectives

សិស្សអាច៖

- Monitor Server Performance
- Analyze Event Logs
- Perform Backup
- Perform Restore
- Understand Disaster Recovery
- Create Recovery Plan
- Troubleshoot complex server problems

## Key Terms

`Monitoring`  
`Performance Monitor`  
`Event Viewer`  
`Backup`  
`Restore`  
`Disaster Recovery (DR)`  
`Recovery Plan`  
`Recovery Point Objective (RPO)`  
`Recovery Time Objective (RTO)`

## Useful Tools

```text
Event Viewer
Performance Monitor
Task Manager
Resource Monitor
Server Manager
Windows Server Backup
PowerShell
```

## PowerShell

```powershell
Get-WinEvent
Get-Process
Get-Service
Get-ComputerInfo
```

## Backup Lab

Scenario:

```text
Server Failure
      ↓
Restore
      ↓
Verify Services
      ↓
Verify Users
      ↓
Verify Files
```

## Troubleshooting Lab

Instructor creates:

```text
AD Failure
DNS Failure
DHCP Failure
GPO Failure
SMB Failure
IIS Failure
Storage Failure
RDP Failure
Service Failure
```

Students document:

```text
Problem
Evidence
Root Cause
Solution
Verification
```

## Homework

Create a Disaster Recovery Plan.

## Quiz

25 Scenario Questions.

## Module Practical Exam

Full Infrastructure Recovery Test.

---

# MODULE 16 — ENTERPRISE CAPSTONE PROJECT

# FINAL PROJECT

## Scenario

Company:

**ABC Technology Corporation**

Departments:

```text
ADMIN
HR
FINANCE
IT
SALES
SERVER
```

---

# FINAL INFRASTRUCTURE

```text
                         INTERNET
                             |
                         FIREWALL
                             |
                       Core Network
                             |
          +------------------+------------------+
          |                  |                  |
         DC1                DC2               FILE
       AD DS              AD DS              SERVER
       DNS                DNS                DFS
       DHCP                                   
          |                  |                  |
          +------------------+------------------+
                             |
                           IIS
                             |
                         CLIENTS
```

---

# FINAL PROJECT REQUIREMENTS

## Active Directory

```text
2 Domain Controllers
1 Domain
6 OUs
10+ Groups
50+ Users
```

## DNS

```text
DNS Redundancy
Forward Lookup Zone
Reverse Lookup Zone
DNS Records
```

## DHCP

```text
Multiple Scopes
Reservations
Exclusions
Failover
```

## Group Policy

Minimum:

```text
Security Policy
Password Policy
Desktop Policy
USB Restriction
Audit Policy
RDP Policy
```

## File Services

```text
SMB
DFS Namespace
DFS Replication
NTFS Permissions
Share Permissions
```

## IIS

```text
2 Websites
Multiple Bindings
Application Pools
```

## Hyper-V

Minimum:

```text
DC1
DC2
FILE1
WEB1
CLIENT1
CLIENT2
```

## PowerShell

Minimum:

```text
User Automation Script
Report Script
Health Check Script
```

## Security

```text
Firewall
Hardening
Auditing
Least Privilege
Secure Administration
```

## Backup

```text
AD Backup
File Backup
System Recovery
Restore Test
```

## High Availability

Students must demonstrate at least one:

```text
Failover
Redundant DC
DHCP Failover
DFS Replication
```

---

# FINAL PROJECT DOCUMENTATION

Students must submit:

## 1. Network Diagram

## 2. Server Infrastructure Diagram

## 3. IP Addressing Table

## 4. AD DS Design

## 5. DNS Design

## 6. DHCP Design

## 7. GPO Design

## 8. File Permission Matrix

## 9. Security Policy

## 10. Backup / Recovery Plan

## 11. PowerShell Scripts

## 12. Troubleshooting Report

---

# FINAL EXAM

## PART A — THEORY

**100 Questions**

| Topic | Questions |
|---|---:|
| AD DS | 15 |
| Replication / Sites | 10 |
| GPO | 10 |
| DNS | 10 |
| DHCP | 10 |
| File Services / DFS | 10 |
| Storage | 5 |
| IIS | 5 |
| Hyper-V | 10 |
| PowerShell | 5 |
| Security | 5 |
| High Availability / DR | 5 |
| **Total** | **100** |

---

# PART B — POWERSHELL

Students must perform tasks using PowerShell:

```powershell
Get-ADUser
Get-ADGroup
Get-ADComputer
Get-ADDomainController
Get-DnsServerZone
Get-DhcpServerv4Scope
Get-SmbShare
Get-Disk
Get-Volume
Get-VM
Get-Service
Get-WinEvent
```

---

# PART C — PRACTICAL EXAM

Students receive a partially configured enterprise environment.

They must:

```text
Analyze
   ↓
Configure
   ↓
Secure
   ↓
Verify
   ↓
Troubleshoot
   ↓
Document
```

---

# PART D — TROUBLESHOOTING EXAM

Possible problems:

```text
AD Replication Failure
DNS Resolution Failure
DHCP Failure
GPO Failure
User Authentication Failure
SMB Failure
DFS Failure
IIS Failure
Hyper-V Network Failure
Storage Failure
RDP Failure
```

Students must identify the **Root Cause**, not simply restart services randomly.

---

# PART E — FINAL PRESENTATION

Students explain:

### 1. Infrastructure Design

Why was the architecture designed this way?

### 2. AD DS

How are Domain Controllers and Users organized?

### 3. DNS

How is DNS made reliable?

### 4. DHCP

How is IP Address assignment maintained?

### 5. File Services

How are DFS and NTFS used?

### 6. Security

How is the infrastructure protected?

### 7. High Availability

What happens when a server fails?

### 8. Disaster Recovery

How will the company recover after a major failure?

---

# 4. ASSESSMENT

| Assessment | Weight |
|---|---:|
| Homework | 5% |
| Weekly Quizzes | 10% |
| Practical Labs | 20% |
| Module Exams | 15% |
| Midterm Exam | 10% |
| Capstone Project | 20% |
| Final Exam | 20% |
| **TOTAL** | **100%** |

---

# 5. ADVANCED COMMAND CHECKLIST

## Active Directory

```powershell
Get-ADUser
Get-ADGroup
Get-ADComputer
Get-ADDomainController
Get-ADDomain
Get-ADForest
```

## Replication

```cmd
repadmin /replsummary
repadmin /showrepl
dcdiag
```

## DNS

```powershell
Get-DnsServerZone
Get-DnsServerResourceRecord
```

```cmd
nslookup
ipconfig /flushdns
```

## DHCP

```powershell
Get-DhcpServerv4Scope
Get-DhcpServerv4Lease
```

## File Server

```powershell
Get-SmbShare
Get-SmbSession
Get-SmbOpenFile
Get-Acl
```

## Storage

```powershell
Get-Disk
Get-PhysicalDisk
Get-StoragePool
Get-VirtualDisk
Get-Volume
```

## IIS

```powershell
Get-WindowsFeature Web-Server
```

## Hyper-V

```powershell
Get-VM
Get-VMSwitch
Get-VMNetworkAdapter
Start-VM
Stop-VM
```

## Security

```powershell
Get-NetFirewallProfile
Get-WinEvent -LogName Security
Get-Service
```

## PowerShell

```powershell
Get-Command
Get-Help
Get-Member
Where-Object
ForEach-Object
```

---

# 6. ADVANCED SKILL MATRIX

| Skill | Basic | Intermediate | Advanced |
|---|---|---|---|
| Windows Server | Install | Manage | Design Infrastructure |
| AD DS | Domain | Advanced Management | Multi-DC / FSMO |
| DNS | Basic | Advanced | Enterprise DNS |
| DHCP | Basic | Multiple Scopes | Failover |
| GPO | Basic | Advanced | Enterprise Policy Design |
| File Server | Basic Share | Permissions | DFS |
| Storage | Basic | Storage Management | Enterprise Storage |
| IIS | Basic | Multiple Sites | Advanced Web Hosting |
| Hyper-V | Basic VM | VM Management | Virtualization Infrastructure |
| PowerShell | Commands | Scripts | Automation |
| Security | Basic | Hardening | Advanced Security |
| Backup | Basic | Restore | Disaster Recovery |
| Troubleshooting | Basic | Structured | Complex Infrastructure |
| Availability | — | Concepts | Failover / Redundancy |
| Design | Small Server | Multi-Server | Enterprise Architecture |

---

# 7. GRADUATION STANDARD

សិស្សត្រូវអាចធ្វើបានដោយខ្លួនឯង៖

```text
[✓] Design Windows Server Infrastructure
[✓] Deploy Multiple Domain Controllers
[✓] Understand FSMO Roles
[✓] Troubleshoot AD Replication
[✓] Design AD Sites
[✓] Design Enterprise GPO
[✓] Design Enterprise DNS
[✓] Configure DHCP Failover
[✓] Configure DFS Namespace
[✓] Configure DFS Replication
[✓] Manage Enterprise Storage
[✓] Deploy IIS
[✓] Manage Hyper-V
[✓] Write PowerShell Automation
[✓] Apply Server Hardening
[✓] Configure High Availability
[✓] Perform Backup / Restore
[✓] Design Disaster Recovery
[✓] Monitor Infrastructure
[✓] Troubleshoot Complex Problems
[✓] Document Infrastructure
```

---

# 8. COMPLETE WINDOWS SERVER LEARNING PATH

```text
WINDOWS SERVER BASIC
        ↓
Installation
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
Domain Join
        ↓
GPO
        ↓
File Server
        ↓
NTFS
        ↓
RDP
        ↓
Backup
        ↓

WINDOWS SERVER INTERMEDIATE
        ↓
Advanced AD
        ↓
Advanced GPO
        ↓
Advanced DNS
        ↓
Advanced DHCP
        ↓
File Server Management
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
Troubleshooting
        ↓

WINDOWS SERVER ADVANCED
        ↓
Multi-DC
        ↓
FSMO
        ↓
AD Replication
        ↓
AD Sites
        ↓
Enterprise GPO
        ↓
Enterprise DNS
        ↓
DHCP Failover
        ↓
DFS
        ↓
Storage Spaces
        ↓
Advanced IIS
        ↓
Advanced Hyper-V
        ↓
PowerShell Automation
        ↓
Server Hardening
        ↓
High Availability
        ↓
Failover Clustering
        ↓
Backup / DR
        ↓
Advanced Troubleshooting
        ↓
ENTERPRISE CAPSTONE
```

# 9. FINAL TARGET

នៅចុង **Windows Server Advanced** សិស្សគួរតែអាចទទួលបាន Scenario ដូចជា៖

```text
Business Requirements
        +
Users
        +
Servers
        +
Applications
        +
Security Requirements
        +
Availability Requirements
        +
Recovery Requirements
```

ហើយអាច Design និង Deploy៖

```text
Active Directory
+
DNS
+
DHCP
+
GPO
+
File Services
+
DFS
+
IIS
+
Hyper-V
+
PowerShell
+
Security
+
High Availability
+
Backup / Disaster Recovery
```

គោលដៅគឺឱ្យសិស្សអាចបំពេញការងារកម្រិត **Junior-to-Mid Windows Server Administrator / System Administrator** និងមានមូលដ្ឋានល្អសម្រាប់បន្តទៅ **Enterprise Infrastructure, Windows Server Security, Cloud Administration និង Microsoft Azure**។