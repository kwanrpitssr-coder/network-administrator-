# WINDOWS SERVER & CISCO NETWORK INFRASTRUCTURE
## Level 1 — Basic

**Duration:** 16 Weeks  
**Class:** 4 Hours / Week  
**Total:** 64 Hours  
**Level:** Beginner  
**Prerequisite:** Basic Computer Knowledge  
**Lab Platforms:** Cisco Packet Tracer + Hyper-V / VMware / VirtualBox  
**Cisco Devices:** Router + Switch  
**Server:** Windows Server 2022 / Windows Server 2025  
**Client:** Windows 10 / Windows 11  
**Teaching Language:** Khmer + English Technical Keywords

## Course Goal

សិស្សត្រូវអាចបង្កើត Network មូលដ្ឋានមួយដែលមាន៖

```text
                INTERNET
                    |
              Cisco Router
                    |
              Cisco Switch
          _________|_________
         |         |         |
       Server     PC1       PC2
         |
   Windows Server
   ├── DNS
   ├── DHCP
   ├── AD DS
   └── File Server
```

---

# Semester Structure

| Week | Module | Main Topic | Cisco Lab | Windows Server Lab |
|---|---|---|---|---|
| 1 | M1 | Network & Server Fundamentals | Basic LAN | Server Concepts |
| 2 | M2 | Cisco Device & Windows Server Setup | Device Setup | Windows Server Install |
| 3 | M3 | IPv4 & Basic Network Configuration | Router/Switch IP | Static IP |
| 4 | M4 | Cisco IOS & Windows Administration | IOS CLI | Server Manager / PowerShell |
| 5 | M5 | VLAN Fundamentals | VLAN | Server Network Segmentation |
| 6 | M6 | Inter-VLAN Routing | Router-on-a-Stick | Multi-Network Server |
| 7 | M7 | DNS Fundamentals | Cisco-to-Server Connectivity | Windows DNS |
| 8 | M8 | DHCP Fundamentals | DHCP Relay Concepts | Windows DHCP |
| 9 | M9 | Active Directory Fundamentals | Cisco-to-Server Connectivity | AD DS |
| 10 | M10 | Domain Join | Network Verification | Windows Client Domain Join |
| 11 | M11 | Users, Groups & OU | Network Access | AD Management |
| 12 | M12 | Group Policy | Network Policy Concepts | GPO |
| 13 | M13 | File Server & Permissions | Server Connectivity | SMB + NTFS |
| 14 | M14 | Network & Server Security | Basic Cisco Security | Windows Server Security |
| 15 | M15 | Troubleshooting | Cisco Troubleshooting | Server Troubleshooting |
| 16 | M16 | Integrated Project + Final Exam | Full Network | Full Server Infrastructure |

---

# MODULE 1 — NETWORK & SERVER FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain **Computer Network**
- Explain **Client-Server Model**
- Identify **Router, Switch, Server, Client**
- Understand **LAN / WAN**
- Understand the relationship between Network and Server

## Key Terms

`Network`  
`LAN`  
`WAN`  
`Router`  
`Switch`  
`Server`  
`Client`  
`Protocol`  
`Packet`  
`Service`

## Lecture Notes

### Network

Network គឺជាការភ្ជាប់ Devices ដើម្បីអាច **Communicate** និងចែករំលែក Resources។

### Router

**Router** ប្រើសម្រាប់ភ្ជាប់ **Different Networks**។

### Switch

**Switch** ប្រើសម្រាប់ភ្ជាប់ Devices ក្នុង **LAN**។

### Server

**Server** ផ្តល់ Services ទៅឱ្យ Clients។

ឧទាហរណ៍៖

```text
DNS Server
DHCP Server
File Server
Web Server
Domain Controller
```

## Cisco Packet Tracer Lab

```text
PC1 ---- SW1 ---- Router1
PC2 ----/
```

Task:

1. Place devices.
2. Connect cables.
3. Identify interfaces.
4. Verify link status.

## Windows Server Lab

បង្កើត Virtual Machine:

```text
VM Name: SRV1
OS: Windows Server
```

មិនទាន់ Install Role ទេ។

## Homework

ពន្យល់៖

1. Router
2. Switch
3. Server
4. Client
5. Network

## Quiz

**10 Questions**

## Module Practical Exam

Identify network devices និង server roles.

---

# MODULE 2 — CISCO & WINDOWS SERVER SETUP

## Learning Objectives

សិស្សអាច៖

- Understand Cisco device startup
- Open Cisco CLI
- Create Windows Server VM
- Install Windows Server
- Identify Cisco and Windows interfaces

## Cisco Keywords

`CLI`  
`IOS`  
`Console`  
`Ethernet Interface`

## Windows Keywords

`Virtual Machine`  
`ISO`  
`Server Core`  
`Desktop Experience`

## Cisco Commands

```text
enable
show version
show interfaces
```

## Windows Server Lab

Create:

```text
VM Name: SRV1
4 GB RAM
2 vCPU
60 GB Disk
1 Network Adapter
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

Create VM + access Cisco CLI.

---

# MODULE 3 — IPv4 & BASIC NETWORK CONFIGURATION

## Learning Objectives

សិស្សអាច៖

- Configure IPv4
- Understand Subnet Mask
- Understand Default Gateway
- Configure Cisco Interface
- Configure Windows Server Static IP
- Test connectivity

## Example IP Plan

```text
Network: 192.168.10.0/24

Router:
192.168.10.1

Server:
192.168.10.10

PC1:
192.168.10.20

PC2:
192.168.10.21
```

## Cisco Commands

```text
enable
configure terminal

interface gigabitEthernet 0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
```

Verify:

```text
show ip interface brief
```

## Windows Commands

```cmd
ipconfig /all
ping
tracert
```

PowerShell:

```powershell
Get-NetIPConfiguration
```

## Cisco Packet Tracer Lab

```text
PC1 ---- SW1 ---- R1
PC2 ----/
```

Configure IPs and test Ping.

## Windows Server Lab

Configure:

```text
SRV1:
192.168.10.10/24
Gateway:
192.168.10.1
```

Test:

```cmd
ping 192.168.10.1
```

## Homework

Create an IP Addressing Table.

## Quiz

15 Questions

## Module Practical Exam

Cisco + Windows Server connectivity.

---

# MODULE 4 — CISCO IOS & WINDOWS ADMINISTRATION

## Learning Objectives

សិស្សអាច៖

- Understand Cisco IOS Modes
- Configure basic Cisco settings
- Use Server Manager
- Use PowerShell basics

## Cisco IOS Modes

```text
User EXEC Mode
Privileged EXEC Mode
Global Configuration Mode
Interface Configuration Mode
```

## Cisco Commands

```text
enable
configure terminal
hostname
show running-config
show startup-config
copy running-config startup-config
```

## Windows Tools

```text
Server Manager
Computer Management
Task Manager
PowerShell
```

## PowerShell

```powershell
Get-ComputerInfo
Get-Service
Get-Process
```

## Lab

Configure:

```text
Cisco:
Hostname = R1
Hostname = SW1

Windows:
Hostname = SRV1
```

## Homework

Explain:

**running-config vs startup-config**

## Quiz

15 Questions

## Module Practical Exam

Basic Cisco + Windows administration.

---

# MODULE 5 — VLAN FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain **VLAN**
- Create VLAN
- Assign Access Port
- Understand VLAN segmentation
- Connect Windows Server to a VLAN

## Key Terms

`VLAN`  
`Access Port`  
`Trunk`  
`VLAN ID`

## Cisco Commands

```text
vlan 10
name SERVER

vlan 20
name USERS
```

Assign port:

```text
interface fastEthernet 0/1
switchport mode access
switchport access vlan 10
```

Verify:

```text
show vlan brief
```

## Cisco Packet Tracer Lab

```text
VLAN 10 = SERVER
VLAN 20 = USERS
```

Create two separate networks.

## Windows Server Lab

Connect SRV1 to:

```text
VLAN 10
```

## Homework

Explain why VLAN is used.

## Quiz

15 Questions

## Module Practical Exam

Create VLANs and assign ports correctly.

---

# MODULE 6 — INTER-VLAN ROUTING

## Learning Objectives

សិស្សអាច៖

- Explain Inter-VLAN Routing
- Configure Trunk
- Configure Router-on-a-Stick
- Configure Windows Server Gateway
- Test communication between VLANs

## Cisco Commands

```text
interface gigabitEthernet 0/1
switchport mode trunk
```

Router:

```text
interface gigabitEthernet 0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

interface gigabitEthernet 0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
```

## Packet Tracer Lab

```text
PC1 -- SW1 ---- R1
PC2 --/
```

```text
VLAN 10 = SERVER
VLAN 20 = USERS
```

## Windows Server Lab

Configure Server in VLAN 10 and Client in VLAN 20.

Test communication.

## Homework

Draw packet flow:

```text
PC → Switch → Trunk → Router → VLAN
```

## Quiz

15 Questions

## Module Practical Exam

Inter-VLAN connectivity.

---

# MODULE 7 — DNS FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain DNS
- Understand Name Resolution
- Install DNS Server
- Create DNS Zone
- Create A Record
- Test DNS

## Key Terms

`DNS`  
`Name Resolution`  
`Forward Lookup Zone`  
`A Record`  
`CNAME`  
`PTR`

## Windows Server

Install:

```powershell
Install-WindowsFeature DNS -IncludeManagementTools
```

## Commands

```cmd
nslookup
ipconfig /flushdns
```

PowerShell:

```powershell
Get-DnsServerZone
```

## Lab

Create:

```text
Zone:
corp.local
```

Create:

```text
server.corp.local
192.168.10.10
```

## Cisco Packet Tracer Lab

Demonstrate client-to-server DNS concept and verify network connectivity.

## Homework

Explain DNS Name Resolution.

## Quiz

20 Questions.

## Module Practical Exam

DNS Zone + Record + Client Test.

---

# MODULE 8 — DHCP FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain DHCP
- Understand DORA
- Install DHCP Server
- Create Scope
- Configure Exclusion
- Configure Options

## Key Terms

`DHCP`  
`Scope`  
`Lease`  
`Reservation`  
`Exclusion`  
`DORA`

## Windows Server

Install:

```powershell
Install-WindowsFeature DHCP -IncludeManagementTools
```

Example:

```text
Scope:
192.168.10.100 - 192.168.10.200

Gateway:
192.168.10.1

DNS:
192.168.10.10
```

## Client Test

```cmd
ipconfig /release
ipconfig /renew
ipconfig /all
```

## Cisco Integration

If DHCP Server is in another subnet:

```text
ip helper-address 192.168.10.10
```

## Lab

```text
VLAN 20
   |
Cisco Router
   |
DHCP Server
```

Students configure DHCP for Clients.

## Homework

Explain:

```text
Discover
Offer
Request
ACK
```

## Quiz

15 Questions.

## Module Practical Exam

DHCP + Cisco integration.

---

# MODULE 9 — ACTIVE DIRECTORY FUNDAMENTALS

## Learning Objectives

សិស្សអាច៖

- Explain Active Directory
- Install AD DS
- Create Domain
- Promote Domain Controller
- Understand DC and Domain

## Key Terms

`Active Directory`  
`AD DS`  
`Domain`  
`Domain Controller`  
`Forest`  
`OU`

## PowerShell

```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

Create Domain:

```powershell
Install-ADDSForest -DomainName "corp.local"
```

## Lab

```text
Cisco Network
      |
     SW1
      |
     DC1
```

Create:

```text
corp.local
```

## Homework

Explain:

**Domain vs Domain Controller**

## Quiz

20 Questions.

## Module Practical Exam

Create a functioning Domain Controller.

---

# MODULE 10 — WINDOWS CLIENT DOMAIN JOIN

## Learning Objectives

សិស្សអាច៖

- Configure Client DNS
- Join Windows Client to Domain
- Login with Domain Account
- Verify Domain Membership

## Lab

```text
              DC1
               |
             SW1
            /   \
          PC1   PC2
```

Domain:

```text
corp.local
```

Join:

```text
PC1
PC2
```

Login:

```text
corp\\student01
```

## Troubleshooting Commands

```cmd
ipconfig /all
ping dc1
nslookup corp.local
```

## Cisco Verification

```text
show vlan brief
show interfaces trunk
```

## Homework

Compare:

**Local Account vs Domain Account**

## Quiz

15 Questions.

## Module Practical Exam

Join two Clients to Domain.

---

# MODULE 11 — USERS, GROUPS & OU

## Learning Objectives

សិស្សអាច៖

- Create Users
- Create Groups
- Create OUs
- Add Users to Groups
- Understand Security Groups

## OU Structure

```text
corp.local
│
├── ADMIN
├── HR
├── IT
└── STUDENT
```

## PowerShell

```powershell
New-ADOrganizationalUnit -Name "STUDENT"
```

```powershell
New-ADUser -Name "Student01" -SamAccountName "student01"
```

```powershell
New-ADGroup -Name "Students" -GroupScope Global
```

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

Design OU Structure for a school.

## Quiz

15 Questions.

## Module Practical Exam

Users + Groups + OUs.

---

# MODULE 12 — GROUP POLICY

## Learning Objectives

សិស្សអាច៖

- Explain GPO
- Create GPO
- Link GPO to OU
- Apply basic security settings
- Verify GPO

## Key Terms

`GPO`  
`GPMC`  
`OU`  
`Policy`  
`Inheritance`

## Commands

```cmd
gpupdate /force
gpresult /r
gpresult /h report.html
```

## Lab

Create:

```text
GPO-STUDENT
GPO-SECURITY
GPO-ADMIN
```

Apply them to appropriate OUs.

## Cisco Integration

Explain how Cisco Network Access and Windows Policies work together:

```text
Cisco Network
     ↓
VLAN
     ↓
Windows Client
     ↓
Domain
     ↓
GPO
```

## Homework

Create 5 policies for Student PCs.

## Quiz

15 Questions.

## Module Practical Exam

Create and verify GPO.

---

# MODULE 13 — FILE SERVER & PERMISSIONS

## Learning Objectives

សិស្សអាច៖

- Create File Server
- Create SMB Share
- Understand NTFS Permissions
- Understand Share Permissions
- Use Groups for Access Control

## Key Terms

`File Server`  
`SMB`  
`NTFS`  
`Share Permission`  
`Security Group`  
`Inheritance`

## Folder Structure

```text
D:\Company
├── ADMIN
├── HR
├── IT
└── STUDENT
```

## PowerShell

```powershell
New-Item -Path "D:\Company" -ItemType Directory
```

```powershell
Get-SmbShare
```

View permissions:

```powershell
Get-Acl "D:\Company"
```

## Lab

Configure:

```text
ADMIN → Full Control
HR → Modify
IT → Modify
STUDENT → Read
```

Access from Client:

```text
\\FS1\Company
```

## Cisco Integration

Server connectivity must work through the Cisco VLAN and Routing configuration.

## Homework

Create Permission Matrix.

## Quiz

20 Questions.

## Module Practical Exam

File Server + NTFS + SMB.

---

# MODULE 14 — NETWORK & SERVER SECURITY

## Learning Objectives

សិស្សអាច៖

- Understand basic network security
- Secure Cisco devices
- Configure Windows Firewall
- Secure Windows Accounts
- Use SSH
- Understand least privilege

## Cisco Security

```text
enable secret
username
ip domain-name
crypto key generate rsa
line vty 0 4
login local
transport input ssh
```

## Windows Security

```powershell
Get-NetFirewallProfile
```

```powershell
Get-Service
```

## Key Terms

`SSH`  
`Firewall`  
`Hardening`  
`Least Privilege`  
`Authentication`  
`Authorization`

## Lab

Secure:

```text
Cisco Router
Cisco Switch
Windows Server
Windows Client
```

## Homework

Create a Security Checklist.

## Quiz

20 Questions.

## Module Practical Exam

Secure the complete infrastructure.

---

# MODULE 15 — INTEGRATED TROUBLESHOOTING

## Learning Objectives

សិស្សអាច៖

- Troubleshoot Cisco Network Problems
- Troubleshoot Windows Server Problems
- Identify Root Cause
- Use verification commands
- Document Troubleshooting

## Troubleshooting Model

```text
Identify
   ↓
Gather Evidence
   ↓
Create Theory
   ↓
Test
   ↓
Fix
   ↓
Verify
   ↓
Document
```

## Cisco Commands

```text
show ip interface brief
show vlan brief
show interfaces trunk
show spanning-tree
show ip route
ping
traceroute
```

## Windows Commands

```cmd
ipconfig /all
ping
tracert
nslookup
```

PowerShell:

```powershell
Test-NetConnection
Get-Service
Get-WinEvent
```

## Fault Scenarios

```text
Wrong VLAN
Wrong IP
Wrong Gateway
DNS Failure
DHCP Failure
Domain Join Failure
GPO Failure
File Permission Failure
SSH Failure
Firewall Failure
```

## Lab

Instructor creates **15 hidden faults**.

Students submit:

```text
Problem
Evidence
Root Cause
Solution
Verification
```

## Homework

Troubleshooting Report.

## Quiz

25 Scenario Questions.

## Module Practical Exam

**Integrated Cisco + Windows Server Troubleshooting**

---

# MODULE 16 — FINAL CAPSTONE PROJECT

# PROJECT TITLE

## ABC School — Cisco + Windows Server Infrastructure

## BUSINESS REQUIREMENTS

School has:

```text
ADMIN
HR
IT
TEACHER
STUDENT
SERVER
```

The network requires:

```text
VLAN
Routing
DNS
DHCP
Active Directory
File Server
Group Policy
Security
```

# FINAL NETWORK TOPOLOGY

```text
                         INTERNET
                            |
                       Cisco Router
                            |
                       Cisco Switch
                   _________|_________
                  |         |         |
                VLAN 10   VLAN 20   VLAN 30
                 ADMIN     USERS     SERVER
                   |         |         |
                  PC1       PC2       DC1
                                      |
                         +------------+------------+
                         |            |            |
                        AD DS        DNS          DHCP
                         |
                       FILE
                       SERVER
```

# FINAL VLAN PLAN

| VLAN | Name | Network |
|---:|---|---|
| 10 | ADMIN | 192.168.10.0/24 |
| 20 | USERS | 192.168.20.0/24 |
| 30 | SERVER | 192.168.30.0/24 |
| 99 | MANAGEMENT | 192.168.99.0/24 |

# FINAL SERVER PLAN

| Server | Role | IP |
|---|---|---|
| DC1 | AD DS + DNS + DHCP | 192.168.30.10 |
| FS1 | File Server | 192.168.30.20 |
| WEB1 | IIS | 192.168.30.30 |

# FINAL PROJECT TASKS

## Cisco

Students must configure:

```text
Hostname
VLAN
Access Port
Trunk
Inter-VLAN Routing
SSH
Basic Security
```

## Windows Server

Students must configure:

```text
Static IP
AD DS
Domain
DNS
DHCP
Users
Groups
OU
GPO
File Server
NTFS Permissions
RDP
Windows Firewall
```

## Client

Students must:

```text
Receive DHCP IP
Resolve DNS
Join Domain
Login Domain Account
Apply GPO
Access File Server
```

# FINAL PROJECT TESTING

Students must demonstrate:

```text
[✓] PC → Default Gateway
[✓] VLAN → VLAN
[✓] Client → DNS
[✓] Client → Domain Controller
[✓] Client → File Server
[✓] Domain Login
[✓] GPO Application
[✓] DHCP
[✓] SSH to Cisco
[✓] RDP to Server
```

# FINAL EXAM

## PART A — THEORY

**100 Questions**

| Topic | Questions |
|---|---:|
| Networking Fundamentals | 10 |
| Cisco IOS | 10 |
| IPv4 | 10 |
| VLAN / Routing | 10 |
| DNS | 10 |
| DHCP | 10 |
| AD DS | 15 |
| Users / Groups / OU | 5 |
| GPO | 5 |
| File Server / NTFS | 5 |
| Security | 5 |
| Troubleshooting | 5 |
| **TOTAL** | **100** |

## PART B — CISCO PRACTICAL

**100 Points**

Students configure:

```text
Router
Switch
VLAN
Trunk
Inter-VLAN Routing
SSH
```

## PART C — WINDOWS SERVER PRACTICAL

**100 Points**

Students configure:

```text
Static IP
DNS
DHCP
AD DS
Users
Groups
OU
GPO
File Server
NTFS
RDP
Firewall
```

## PART D — TROUBLESHOOTING

Students receive a broken environment containing problems in:

```text
Cisco Network
DNS
DHCP
Active Directory
GPO
File Server
Permissions
Security
```

Students must:

```text
Identify
   ↓
Analyze
   ↓
Fix
   ↓
Verify
   ↓
Document
```

# ASSESSMENT

| Assessment | Weight |
|---|---:|
| Homework | 5% |
| Weekly Quizzes | 10% |
| Cisco Labs | 15% |
| Windows Server Labs | 15% |
| Module Exams | 15% |
| Midterm Exam | 10% |
| Final Project | 15% |
| Final Exam | 15% |
| **TOTAL** | **100%** |

# COURSE COMPETENCY CHECKLIST

```text
[✓] Explain Network
[✓] Explain Client-Server
[✓] Configure Cisco Router
[✓] Configure Cisco Switch
[✓] Configure IPv4
[✓] Configure VLAN
[✓] Configure Trunk
[✓] Configure Inter-VLAN Routing
[✓] Configure Cisco SSH
[✓] Install Windows Server
[✓] Configure Static IP
[✓] Install DNS
[✓] Install DHCP
[✓] Install AD DS
[✓] Create Domain
[✓] Create Users
[✓] Create Groups
[✓] Create OUs
[✓] Join Client to Domain
[✓] Configure GPO
[✓] Configure File Server
[✓] Configure NTFS Permissions
[✓] Configure RDP
[✓] Configure Basic Security
[✓] Troubleshoot Cisco Network
[✓] Troubleshoot Windows Server
```

# COMPLETE LEARNING PATH

```text
IT FUNDAMENTALS
       ↓
NETWORKING BASICS
       ↓
CISCO ROUTER / SWITCH
       ↓
IPv4
       ↓
VLAN
       ↓
INTER-VLAN ROUTING
       ↓
WINDOWS SERVER
       ↓
DNS
       ↓
DHCP
       ↓
ACTIVE DIRECTORY
       ↓
DOMAIN JOIN
       ↓
USERS / GROUPS / OU
       ↓
GPO
       ↓
FILE SERVER
       ↓
NTFS
       ↓
SECURITY
       ↓
TROUBLESHOOTING
       ↓
CISCO + WINDOWS SERVER
       ↓
FINAL ENTERPRISE LAB
```
