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

---

# 1. COURSE PURPOSE

Course នេះបន្តពី **Windows Server Intermediate** ហើយផ្តោតលើការគ្រប់គ្រង និងរចនា **Enterprise Windows Server Infrastructure**។

សិស្សនឹងអភិវឌ្ឍពី៖

```text
Manage a Server
      ↓
Manage Multiple Servers
      ↓
Design Infrastructure
      ↓
Secure Infrastructure
      ↓
Provide Redundancy
      ↓
Automate Administration
      ↓
Monitor
      ↓
Recover
      ↓
Troubleshoot
```

---

# 2. DESIGN PRINCIPLES OF THIS COURSE

លំដាប់ Module ត្រូវបានរៀបតាម Dependency:

```text
AD DS
  ↓
Replication / Sites
  ↓
GPO
  ↓
DNS
  ↓
DHCP
  ↓
File Services
  ↓
DFS
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
High Availability
  ↓
Backup / DR
  ↓
Troubleshooting
  ↓
Capstone
```

នេះមានន័យថា Final Project ប្រើតែ Technology ដែលសិស្សបានរៀនរួចហើយ។

---

# 3. COURSE LEARNING OUTCOMES

នៅចុង Semester សិស្សអាច៖

- Design a multi-server Windows Server environment
- Manage multiple **Domain Controllers**
- Understand **FSMO Roles**
- Troubleshoot **AD DS Replication**
- Design **Active Directory Sites**
- Design and troubleshoot enterprise **GPO**
- Design resilient **DNS**
- Configure advanced **DHCP**
- Manage enterprise **File Services**
- Configure **DFS Namespace**
- Understand **DFS Replication**
- Manage Server Storage
- Deploy and manage **IIS**
- Build a **Hyper-V** lab infrastructure
- Automate administration using **PowerShell**
- Apply Windows Server hardening
- Understand **High Availability**
- Configure basic **Failover Clustering**
- Perform Backup and Restore
- Build a basic Disaster Recovery plan
- Monitor and troubleshoot enterprise infrastructure
- Document infrastructure professionally

---

# 4. STANDARD LAB ENVIRONMENT

គ្រប់ Lab ត្រូវប្រើ Environment ដែលអាចបន្តគ្នាពី Module មួយទៅ Module មួយ។

## Core Virtual Machines

```text
DC1
DC2
FS1
FS2
WEB1
WEB2
MGMT1
CLIENT1
CLIENT2
CLIENT3
```

## Basic Network

```text
                Router
                   |
             Virtual Switch
                   |
      +------------+-------------+
      |            |             |
     DC1          DC2           FS1
      |            |             |
      +------------+-------------+
                   |
                 FS2
                   |
                 WEB1
                   |
                 WEB2
```

---

# 5. IP ADDRESSING STANDARD

ប្រើ Addressing Plan មួយជាប់គ្នាទូទាំង Semester។

```text
Network:
192.168.10.0/24
```

## Infrastructure

```text
Gateway:
192.168.10.1

DC1:
192.168.10.10

DC2:
192.168.10.11

FS1:
192.168.10.20

FS2:
192.168.10.21

WEB1:
192.168.10.30

WEB2:
192.168.10.31

MGMT1:
192.168.10.40
```

## DHCP Client Range

```text
192.168.10.100 - 192.168.10.200
```

## Domain

```text
corp.local
```

> ឈ្មោះ `corp.local` ត្រូវប្រើជាប់គ្នាទូទាំង Lab និង Capstone ដើម្បីកុំឱ្យសិស្សច្រឡំ។

---

# 6. SEMESTER STRUCTURE

| Week | Module | Main Topic | Main Lab |
|---|---|---|---|
| 1 | M1 | Advanced AD DS Architecture | Multi-DC |
| 2 | M2 | AD Replication & Sites | DC1/DC2 Replication |
| 3 | M3 | Advanced AD Management & Delegation | OU + Delegation |
| 4 | M4 | Advanced Group Policy | Enterprise GPO |
| 5 | M5 | Advanced DNS | DNS Redundancy |
| 6 | M6 | Advanced DHCP | DHCP Resilience |
| 7 | M7 | File Services & SMB | File Server |
| 8 | M8 | DFS Namespace & Replication | DFS |
| 9 | M9 | Advanced Storage | Storage Management |
| 10 | M10 | IIS Web Server | Web Farm Basics |
| 11 | M11 | Hyper-V Virtualization | VM Infrastructure |
| 12 | M12 | PowerShell Automation | Administration Scripts |
| 13 | M13 | Windows Server Security | Server Hardening |
| 14 | M14 | High Availability | Failover Concepts |
| 15 | M15 | Backup, DR & Troubleshooting | Recovery Lab |
| 16 | M16 | Capstone + Final Exam | Enterprise Project |

---

# MODULE 1 — ADVANCED AD DS ARCHITECTURE

## Learning Objectives

សិស្សអាច៖

- Explain advanced **AD DS Architecture**
- Understand **Domain Controller**
- Understand **Global Catalog**
- Understand **FSMO Roles**
- Manage multiple Domain Controllers

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

```powershell
Get-ADDomainController
Get-ADDomain
Get-ADForest
```

## Lab

Deploy:

```text
DC1
DC2
```

Both belong to:

```text
corp.local
```

Test:

- Domain Login
- DNS
- Authentication
- DC Discovery

## Homework

Explain the 5 FSMO Roles.

## Quiz

20 Questions

## Module Practical Exam

Deploy and verify a 2-DC environment.

---

# MODULE 2 — AD DS REPLICATION & SITES

## Learning Objectives

សិស្សអាច៖

- Explain AD Replication
- Understand **Sites**
- Understand **Site Links**
- Identify replication partners
- Troubleshoot replication

## Key Terms

`Replication`  
`AD Site`  
`Site Link`  
`Replication Partner`  
`KCC`

## Commands

```cmd
repadmin /replsummary
repadmin /showrepl
dcdiag
```

## Lab

```text
SITE-A                    SITE-B

DC1 ==================== DC2
```

Configure Sites and verify replication.

## Troubleshooting

Instructor introduces:

- DNS problem
- Replication problem
- Wrong Site
- Connectivity problem

## Homework

Explain why AD Replication is important.

## Quiz

20 Questions

## Module Practical Exam

Identify and repair an AD Replication problem.

---

# MODULE 3 — ADVANCED AD MANAGEMENT & DELEGATION

## Learning Objectives

សិស្សអាច៖

- Design OU hierarchy
- Delegate administrative tasks
- Manage Computer Accounts
- Manage Service Accounts
- Apply Least Privilege

## Key Terms

`OU`  
`Delegation`  
`Service Account`  
`Least Privilege`  
`Computer Account`

## Lab

Create:

```text
corp.local
│
├── Users
│   ├── Admin
│   ├── Staff
│   └── Students
│
├── Computers
│   ├── Office
│   └── Lab
│
└── Servers
```

Create groups:

```text
IT-Admins
Helpdesk
Staff
Students
Server-Admins
```

## PowerShell

```powershell
Get-ADUser -Filter *
Get-ADGroup -Filter *
Get-ADComputer -Filter *
```

## Homework

Create an OU and Delegation Matrix.

## Quiz

15 Questions

## Module Practical Exam

OU Design + Delegation.

---

# MODULE 4 — ADVANCED GROUP POLICY

## Learning Objectives

សិស្សអាច៖

- Design Enterprise GPO
- Understand GPO Scope
- Understand GPO Precedence
- Understand Inheritance
- Use Security Filtering
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
GPO-Domain-Security
GPO-Students
GPO-Workstations
GPO-Servers
```

Apply according to OU structure.

## Troubleshooting Lab

Create conflicting policies and ask students to identify:

```text
Which GPO wins?
Why?
How can we verify?
```

## Homework

Create an Enterprise GPO Design.

## Quiz

20 Questions

## Module Practical Exam

Troubleshoot a GPO application problem.

---

# MODULE 5 — ADVANCED DNS INFRASTRUCTURE

## Learning Objectives

សិស្សអាច៖

- Manage DNS Zones
- Configure Forward Lookup Zone
- Configure Reverse Lookup Zone
- Manage DNS Records
- Understand DNS Forwarders
- Configure DNS redundancy
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

```powershell
Get-DnsServerZone
Get-DnsServerResourceRecord
```

```cmd
nslookup
ipconfig /flushdns
```

## Lab

Configure DNS on:

```text
DC1
DC2
```

Create:

```text
corp.local
```

Records:

```text
dc1.corp.local
dc2.corp.local
fs1.corp.local
web1.corp.local
```

## Homework

Design DNS Infrastructure for a company.

## Quiz

20 Questions

## Module Practical Exam

DNS redundancy + troubleshooting.

---

# MODULE 6 — ADVANCED DHCP

## Learning Objectives

សិស្សអាច៖

- Create multiple DHCP Scopes
- Configure Reservations
- Configure Exclusions
- Configure DHCP Options
- Understand DHCP Failover
- Troubleshoot DHCP

## Key Terms

`DHCP`  
`Scope`  
`Reservation`  
`Lease`  
`Exclusion`  
`DHCP Failover`  
`Load Balance`  
`Hot Standby`

## Commands

```powershell
Get-DhcpServerv4Scope
Get-DhcpServerv4Lease
```

Client:

```cmd
ipconfig /release
ipconfig /renew
ipconfig /all
```

## Lab

Deploy:

```text
DHCP1 = DC1
DHCP2 = DC2
```

Configure DHCP Failover.

Test:

```text
DC1 / DHCP1
      ↓ Failure
DC2 / DHCP2
      ↓
Client continues receiving service
```

## Homework

Compare:

**Load Balance vs Hot Standby**

## Quiz

15 Questions

## Module Practical Exam

Configure and test DHCP resilience.

---

# MODULE 7 — FILE SERVICES & SMB

## Learning Objectives

សិស្សអាច៖

- Design File Server
- Configure SMB Shares
- Manage Share Permissions
- Use Security Groups
- Understand File Server Administration

## Key Terms

`File Server`  
`SMB`  
`Share`  
`Shared Folder`  
`Security Group`

## Lab

Use:

```text
FS1
```

Create:

```text
D:\Company
├── ADMIN
├── HR
├── FINANCE
├── IT
└── PUBLIC
```

Share:

```text
\\FS1\Company
```

## PowerShell

```powershell
Get-SmbShare
Get-SmbSession
Get-SmbOpenFile
```

## Homework

Design a File Server structure.

## Quiz

15 Questions

## Module Practical Exam

Create and manage SMB File Shares.

---

# MODULE 8 — DFS NAMESPACE & DFS REPLICATION

## Learning Objectives

សិស្សអាច៖

- Explain **DFS**
- Configure **DFS Namespace**
- Configure **DFS Replication (DFSR)**
- Understand Namespace vs Replication
- Troubleshoot DFS

## Key Terms

`DFS`  
`DFS Namespace`  
`DFSR`  
`Namespace Server`  
`Replication Group`

## Lab

Use:

```text
FS1
FS2
```

Create namespace:

```text
\\corp.local\Company
```

Folders:

```text
ADMIN
HR
FINANCE
IT
```

Replicate selected folders between FS1 and FS2.

## Homework

Explain:

**DFS Namespace vs DFS Replication**

## Quiz

15 Questions

## Module Practical Exam

Configure DFS Namespace + Replication.

---

# MODULE 9 — ADVANCED STORAGE

## Learning Objectives

សិស្សអាច៖

- Manage Disks
- Manage Partitions
- Manage Volumes
- Configure Storage Spaces
- Understand Storage Pool
- Understand resiliency types

## Key Terms

`Disk`  
`Partition`  
`Volume`  
`Storage Pool`  
`Virtual Disk`  
`Storage Space`  
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

Create virtual disks:

```text
Disk 1
Disk 2
Disk 3
Disk 4
```

Create:

```text
Storage Pool
Virtual Disk
Volume
```

## Homework

Compare:

```text
Simple
Mirror
Parity
```

## Quiz

15 Questions

## Module Practical Exam

Storage Management.

---

# MODULE 10 — IIS WEB SERVER

## Learning Objectives

សិស្សអាច៖

- Install IIS
- Create Websites
- Configure Bindings
- Understand Application Pools
- Understand HTTP / HTTPS
- Deploy multiple websites

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

## Lab

Use:

```text
WEB1
WEB2
```

Deploy:

```text
www.corp.local
portal.corp.local
```

Configure different bindings.

## Homework

Explain:

**Website vs Application Pool**

## Quiz

15 Questions

## Module Practical Exam

Deploy and test multiple IIS websites.

---

# MODULE 11 — HYPER-V VIRTUALIZATION

## Learning Objectives

សិស្សអាច៖

- Understand Hyper-V Architecture
- Create VMs
- Configure Virtual Switches
- Manage VHDX
- Manage Checkpoints
- Allocate VM resources

## Key Terms

`Hyper-V`  
`Virtual Machine`  
`Virtual Switch`  
`VHDX`  
`Checkpoint`

## Commands

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

Create:

```text
DC1
DC2
FS1
FS2
WEB1
WEB2
CLIENT1
CLIENT2
```

Connect them through Virtual Switch.

## Homework

Design a Virtualization Lab Architecture.

## Quiz

15 Questions

## Module Practical Exam

Build and manage a multi-VM infrastructure.

---

# MODULE 12 — POWERSHELL AUTOMATION

## Learning Objectives

សិស្សអាច៖

- Use PowerShell effectively
- Work with Objects
- Use Pipeline
- Write Scripts
- Use Loops
- Use Functions
- Automate Administration

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
Get-Member
Where-Object
ForEach-Object
```

## Lab

Create an automation script that:

```text
Create 30 Users
Create 5 Groups
Create OUs
Add Users to Groups
Create Folders
Create Report
```

## Homework

Create a User Provisioning Script.

## Quiz

20 Questions

## Module Practical Exam

PowerShell Automation Challenge.

---

# MODULE 13 — WINDOWS SERVER SECURITY & HARDENING

## Learning Objectives

សិស្សអាច៖

- Apply Server Hardening
- Secure Administrator Accounts
- Configure Windows Firewall
- Configure Auditing
- Secure RDP
- Apply Least Privilege
- Monitor Security Events

## Key Terms

`Hardening`  
`Least Privilege`  
`Windows Defender`  
`Windows Firewall`  
`Auditing`  
`Security Log`

## Commands

```powershell
Get-NetFirewallProfile
Get-Service
Get-WinEvent -LogName Security
```

## Lab

Apply:

```text
Strong Password Policy
Account Lockout
Windows Firewall
Restricted RDP
Auditing
Least Privilege
```

## Homework

Create an Enterprise Server Hardening Checklist.

## Quiz

20 Questions

## Module Practical Exam

Harden a Windows Server according to a security checklist.

---

# MODULE 14 — HIGH AVAILABILITY & FAILOVER

## Learning Objectives

សិស្សអាច៖

- Explain High Availability
- Identify Single Point of Failure
- Understand Failover
- Understand Failover Cluster
- Understand Cluster Nodes
- Understand Quorum
- Test service continuity

## Key Terms

`High Availability`  
`Failover`  
`Failover Cluster`  
`Cluster Node`  
`Quorum`  
`Clustered Role`

## Lecture Notes

Single Server:

```text
CLIENTS
   |
SERVER
```

Server failure = Service unavailable.

Redundant design:

```text
          CLIENTS
             |
       +-----+-----+
       |           |
     NODE1       NODE2
       \           /
        \         /
        Cluster
```

## Lab

Use:

```text
NODE1
NODE2
```

Create a basic clustering demonstration where supported by the lab environment.

Test:

```text
NODE1 ONLINE
      ↓
NODE1 FAILURE
      ↓
NODE2
      ↓
SERVICE CONTINUES
```

## Homework

Explain:

**High Availability vs Backup**

## Quiz

20 Questions

## Module Practical Exam

Failover Scenario Test.

---

# MODULE 15 — BACKUP, DISASTER RECOVERY & TROUBLESHOOTING

## Learning Objectives

សិស្សអាច៖

- Plan Backup
- Perform Restore
- Understand Disaster Recovery
- Understand RPO
- Understand RTO
- Monitor Server
- Analyze Event Logs
- Troubleshoot multi-service problems

## Key Terms

`Backup`  
`Restore`  
`Disaster Recovery (DR)`  
`RPO`  
`RTO`  
`Monitoring`  
`Event Viewer`

## Tools

```text
Windows Server Backup
Event Viewer
Performance Monitor
Resource Monitor
Task Manager
PowerShell
```

## PowerShell

```powershell
Get-Service
Get-Process
Get-WinEvent
Get-ComputerInfo
```

## Backup Lab

Backup:

```text
AD DS
File Server Data
IIS Content
Configuration
```

Then:

```text
Delete Data
    ↓
Restore
    ↓
Verify
```

## Troubleshooting Lab

Instructor creates:

```text
AD Replication Failure
DNS Failure
DHCP Failure
GPO Failure
SMB Failure
DFS Failure
IIS Failure
RDP Failure
Service Failure
Storage Problem
```

Students submit:

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

25 Scenario Questions

## Module Practical Exam

Full Infrastructure Troubleshooting + Recovery.

---

# MODULE 16 — ENTERPRISE CAPSTONE PROJECT

# PROJECT TITLE

## ABC Corporation — Windows Server Enterprise Infrastructure

---

# BUSINESS SCENARIO

ABC Corporation has:

```text
ADMIN
HR
FINANCE
IT
SALES
```

The company needs:

```text
Central Authentication
DNS
DHCP
File Services
Web Services
Group Policy
Security
Redundancy
Backup
Monitoring
```

---

# FINAL INFRASTRUCTURE

```text
                         CLIENTS
                            |
                     Virtual Network
                            |
         +------------------+------------------+
         |                  |                  |
        DC1                DC2                MGMT1
         |                  |                  |
       AD DS              AD DS            Admin Tools
       DNS                DNS
       DHCP               DHCP
         |                  |
         +---------+--------+
                   |
            +------+------+
            |             |
           FS1           FS2
            |             |
          SMB           DFSR
            \             /
             \           /
              DFS Namespace
                   |
              +----+----+
              |         |
             WEB1      WEB2
              |         |
             IIS       IIS
```

---

# FINAL PROJECT TECHNOLOGIES

Every technology below has already been taught in Modules 1–15.

```text
AD DS
FSMO
AD Replication
AD Sites
OU
Delegation
GPO
DNS
DHCP
SMB
NTFS Permissions
DFS Namespace
DFS Replication
Storage
IIS
Hyper-V
PowerShell
Security Hardening
High Availability
Backup
Disaster Recovery
Troubleshooting
```

---

# FINAL PROJECT REQUIREMENTS

## 1. Active Directory

```text
2 Domain Controllers
1 Domain
6 OUs
5+ Security Groups
50+ Users
```

Domain:

```text
corp.local
```

## 2. AD Replication

Students must demonstrate:

```text
DC1 ↔ DC2
```

Verify:

```cmd
repadmin /replsummary
```

## 3. DNS

Both Domain Controllers provide DNS.

Required:

```text
Forward Lookup Zone
Reverse Lookup Zone
A Records
CNAME
PTR
```

## 4. DHCP

Deploy DHCP on the Domain Controllers according to the lab design.

Configure:

```text
Scope
Exclusion
Reservation
Options
Failover
```

## 5. GPO

Minimum:

```text
Security Policy
Password Policy
Workstation Policy
Student/Staff Policy
Server Policy
```

## 6. File Services

FS1 + FS2:

```text
SMB
NTFS Permissions
DFS Namespace
DFS Replication
```

Namespace:

```text
\\corp.local\Company
```

## 7. IIS

Deploy:

```text
www.corp.local
portal.corp.local
```

on the Web Server environment.

## 8. Hyper-V

Virtual infrastructure must contain:

```text
DC1
DC2
FS1
FS2
WEB1
WEB2
CLIENT1
CLIENT2
```

## 9. PowerShell

Students submit:

```text
User Creation Script
Group Creation Script
Health Check Script
Report Script
```

## 10. Security

Must include:

```text
Firewall
GPO Security
Least Privilege
Auditing
Secure RDP
Administrative Separation
```

## 11. Backup

Students must demonstrate:

```text
Backup
Delete Test Data
Restore
Verify
```

## 12. High Availability

Students must demonstrate at least two redundancy mechanisms:

```text
DC1/DC2
DNS Redundancy
DHCP Failover
DFS Replication
Failover Cluster
```

---

# FINAL PROJECT DOCUMENTATION

Students must submit:

## 1. Infrastructure Diagram

## 2. IP Addressing Table

## 3. Server Inventory

| Server | Role | IP |
|---|---|---|
| DC1 | AD DS/DNS/DHCP | 192.168.10.10 |
| DC2 | AD DS/DNS/DHCP | 192.168.10.11 |
| FS1 | File/DFS | 192.168.10.20 |
| FS2 | File/DFS | 192.168.10.21 |
| WEB1 | IIS | 192.168.10.30 |
| WEB2 | IIS | 192.168.10.31 |

## 4. AD DS Design

## 5. GPO Design

## 6. DNS Design

## 7. DHCP Design

## 8. File Permission Matrix

## 9. Security Policy

## 10. Backup / DR Plan

## 11. PowerShell Scripts

## 12. Testing Results

## 13. Troubleshooting Report

---

# FINAL EXAM

## PART A — THEORY

**100 Questions**

| Topic | Questions |
|---|---:|
| AD DS / FSMO | 15 |
| Replication / Sites | 10 |
| GPO | 10 |
| DNS | 10 |
| DHCP | 10 |
| File Services / DFS | 10 |
| Storage | 5 |
| IIS | 5 |
| Hyper-V | 5 |
| PowerShell | 5 |
| Security | 5 |
| High Availability | 5 |
| Backup / DR | 5 |
| Troubleshooting | 5 |
| **Total** | **120** |

> សម្រាប់ Final Exam ពិតប្រាកដ អាចកំណត់ជា **100 Questions** ដោយ instructor សម្របសម្រួលចំនួនសំណួរតាមពេលវេលា។

---

# PART B — DESIGN EXAM

Students receive:

```text
Business Requirements
User Requirements
Security Requirements
Availability Requirements
```

They must produce:

```text
AD Design
DNS Design
DHCP Design
File Design
GPO Design
Security Design
Backup Plan
```

---

# PART C — PRACTICAL EXAM

Student receives a partially configured environment.

Must:

```text
Analyze
   ↓
Configure
   ↓
Verify
   ↓
Secure
   ↓
Troubleshoot
   ↓
Document
```

---

# PART D — TROUBLESHOOTING EXAM

Instructor creates faults in:

```text
AD DS
DNS
DHCP
GPO
SMB
DFS
IIS
PowerShell
Security
Storage
```

Students must identify:

```text
Symptom
Evidence
Root Cause
Fix
Verification
```

---

# PART E — FINAL PRESENTATION

Students explain:

### Infrastructure Architecture

ហេតុអ្វីបានជាជ្រើសរើស Design នេះ?

### Active Directory

តើ DC1 និង DC2 មានតួនាទីអ្វី?

### DNS / DHCP

តើ Services ទាំងនេះផ្តល់ Reliability យ៉ាងដូចម្តេច?

### File Services

ហេតុអ្វីប្រើ SMB + DFS?

### Security

តើអ្នកការពារម៉ាស៊ីនមេ និង Users ដោយរបៀបណា?

### High Availability

តើមានអ្វីកើតឡើងនៅពេល Server ឬ Service មួយ Fail?

### Disaster Recovery

តើយើង Restore Service ដោយរបៀបណា?

---

# 7. ASSESSMENT

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

# 8. STANDARD COMMAND CHECKLIST

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

## GPO

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

```cmd
nslookup
ipconfig /flushdns
```

## DHCP

```powershell
Get-DhcpServerv4Scope
Get-DhcpServerv4Lease
```

## File Services

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

## Security / Monitoring

```powershell
Get-NetFirewallProfile
Get-Service
Get-WinEvent
Get-Process
```

## Testing

```cmd
ping
tracert
nslookup
```

---

# 9. RESOLVED COURSE DEPENDENCY

```text
M1  AD DS Architecture
 ↓
M2  Replication & Sites
 ↓
M3  AD Management
 ↓
M4  GPO
 ↓
M5  DNS
 ↓
M6  DHCP
 ↓
M7  File Services
 ↓
M8  DFS
 ↓
M9  Storage
 ↓
M10 IIS
 ↓
M11 Hyper-V
 ↓
M12 PowerShell
 ↓
M13 Security
 ↓
M14 High Availability
 ↓
M15 Backup / DR / Troubleshooting
 ↓
M16 Capstone
```

---

# 10. RESOLVED CAPSTONE DEPENDENCY

Final Project uses only technologies explicitly taught earlier:

```text
AD DS              → M1
Replication        → M2
Sites              → M2
Delegation         → M3
GPO                → M4
DNS                → M5
DHCP               → M6
SMB                → M7
NTFS               → M7
DFS                → M8
Storage            → M9
IIS                → M10
Hyper-V            → M11
PowerShell         → M12
Security            → M13
High Availability  → M14
Backup / DR        → M15
Troubleshooting    → M15
```

---

# 11. GRADUATION STANDARD

Students must be able to:

```text
[✓] Design Multi-Server Infrastructure
[✓] Manage Multiple Domain Controllers
[✓] Explain FSMO Roles
[✓] Troubleshoot AD Replication
[✓] Design AD Sites
[✓] Design Enterprise GPO
[✓] Manage DNS
[✓] Manage DHCP
[✓] Manage SMB File Services
[✓] Configure NTFS Permissions
[✓] Configure DFS
[✓] Manage Storage
[✓] Deploy IIS
[✓] Manage Hyper-V
[✓] Automate with PowerShell
[✓] Harden Windows Server
[✓] Implement Redundancy
[✓] Perform Backup / Restore
[✓] Plan Disaster Recovery
[✓] Monitor Infrastructure
[✓] Troubleshoot Complex Problems
[✓] Document Enterprise Infrastructure
```

---

# 12. COMPLETE WINDOWS SERVER PATH

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
Advanced AD Management
        ↓
Advanced GPO
        ↓
Advanced DNS
        ↓
Advanced DHCP
        ↓
File Services
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
Advanced Storage
        ↓
Advanced IIS
        ↓
Hyper-V Infrastructure
        ↓
PowerShell Automation
        ↓
Server Hardening
        ↓
High Availability
        ↓
Failover
        ↓
Backup / DR
        ↓
Advanced Troubleshooting
        ↓
ENTERPRISE CAPSTONE
```

# 13. FINAL TARGET

ក្រោយចប់ **Windows Server Advanced** សិស្សគួរតែអាចផ្លាស់ពី៖

```text
Server Technician
```

ទៅជា៖

```text
Junior Windows Server Administrator
        ↓
System Administrator
        ↓
Infrastructure Administrator
```

ដោយអាចធ្វើការ៖

```text
DESIGN
   ↓
DEPLOY
   ↓
ADMINISTER
   ↓
SECURE
   ↓
MONITOR
   ↓
TROUBLESHOOT
   ↓
BACKUP
   ↓
RECOVER
   ↓
DOCUMENT
```