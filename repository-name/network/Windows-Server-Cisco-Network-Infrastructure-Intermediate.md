# WINDOWS SERVER & CISCO NETWORK INFRASTRUCTURE — INTERMEDIATE
## Integrated Cisco Networking + Windows Server Administration

**Level:** Intermediate  
**Duration:** 16 Weeks  
**Class:** 4 Hours / Week  
**Total:** 64 Hours  
**Prerequisite:** Windows Server + Cisco Network Infrastructure Basic  
**Lab Platforms:** Cisco Packet Tracer + Hyper-V / VMware Workstation / VirtualBox  
**Cisco Devices:** Router + Switch + Layer 3 Switch (where supported)  
**Windows Server:** Windows Server 2022 / Windows Server 2025  
**Windows Client:** Windows 10 / Windows 11  
**Teaching Language:** Khmer + English Technical Keywords  
**Main Focus:** Configure + Integrate + Verify + Troubleshoot

---

# 1. COURSE PURPOSE

Course នេះបន្តពី **Basic Level** ដោយឱ្យសិស្សភ្ជាប់ **Cisco Network Infrastructure** ជាមួយ **Windows Server Infrastructure** ជា Environment តែមួយ។

នៅ Basic សិស្សបានរៀន៖

```text
Cisco Router / Switch
        ↓
IPv4
        ↓
VLAN
        ↓
Inter-VLAN Routing
        ↓
Windows Server
        ↓
DNS
        ↓
DHCP
        ↓
AD DS
        ↓
Domain Join
        ↓
GPO
        ↓
File Server
```

នៅ Intermediate សិស្សនឹងរៀន៖

```text
Advanced VLAN
      ↓
Trunking
      ↓
STP / RSTP
      ↓
EtherChannel
      ↓
Layer 3 Switching
      ↓
OSPF
      ↓
Advanced DHCP
      ↓
Advanced DNS
      ↓
Advanced AD DS
      ↓
Advanced GPO
      ↓
File Services
      ↓
IIS
      ↓
PowerShell
      ↓
Security
      ↓
Integrated Troubleshooting
```

---

# 2. COURSE LEARNING OUTCOMES

នៅចុង Semester សិស្សអាច៖

- Configure advanced **VLANs, Trunks, STP/RSTP, and EtherChannel**
- Configure basic **Layer 3 Switching**
- Configure **OSPF** សម្រាប់ Multi-Router Network
- Design IPv4 **VLSM** addressing
- Integrate Cisco routing with Windows Server networks
- Configure centralized **DNS and DHCP**
- Configure **DHCP Relay** រវាង VLANs
- Manage **Active Directory Domain Services (AD DS)**
- Manage Users, Groups, OUs និង Computer Accounts
- Configure advanced **Group Policy (GPO)**
- Manage **SMB / File Server / NTFS Permissions**
- Deploy a basic **IIS Web Server**
- Use **PowerShell** សម្រាប់ Windows Server Administration
- Configure basic **SSH** លើ Cisco Devices និង **RDP** សម្រាប់ Windows Server
- Apply network and server security controls
- Troubleshoot Cisco + Windows integrated infrastructure
- Design and deploy a small business network and server environment

---

# 3. STANDARD LAB ENVIRONMENT

គ្រប់ Module ប្រើ Lab Environment ដែលអាចបន្តគ្នាបាន។

## Cisco

```text
R1      = Edge Router
R2      = Internal Router
SW1     = Access Switch
SW2     = Access Switch
SW3     = Core / Layer 3 Switch
```

## Windows Server

```text
DC1     = AD DS + DNS
SRV1    = DHCP + File Server
WEB1    = IIS
MGMT1   = Management Server / Admin PC
```

## Windows Clients

```text
PC1
PC2
PC3
PC4
```

## Logical Topology

```text
                         INTERNET
                            |
                           R1
                            |
                         R2 / Core
                            |
                         SW3 (L3)
                       /           \
                     SW1           SW2
                  /   |   \      /   |   \
                PC1  PC2  DC1   PC3  PC4  SRV1
                              |
                             WEB1
```

---

# 4. STANDARD IP ADDRESSING PLAN

| Network | Purpose | Addressing |
|---|---|---|
| VLAN 10 | ADMIN | 192.168.10.0/24 |
| VLAN 20 | USERS | 192.168.20.0/24 |
| VLAN 30 | SERVERS | 192.168.30.0/24 |
| VLAN 40 | GUEST | 192.168.40.0/24 |
| VLAN 99 | MANAGEMENT | 192.168.99.0/24 |
| WAN-1 | R1-R2 | 10.0.0.0/30 |
| WAN-2 | R2-SW3 | 10.0.0.4/30 |

## Server IPs

```text
DC1   = 192.168.30.10
SRV1  = 192.168.30.20
WEB1  = 192.168.30.30
```

## Domain

```text
corp.local
```

---

# 5. SEMESTER STRUCTURE

| Week | Module | Main Topic | Cisco Lab | Windows Server Lab |
|---|---|---|---|---|
| 1 | M1 | Advanced IPv4 & VLSM | IP Design | Server IP Plan |
| 2 | M2 | VLAN & Trunking | Multi-VLAN | Server VLAN Integration |
| 3 | M3 | STP / RSTP | Loop Prevention | Service Availability |
| 4 | M4 | EtherChannel | LACP | Redundant Server Links |
| 5 | M5 | Layer 3 Switching | SVI / Routing | Multi-VLAN Server Access |
| 6 | M6 | OSPF | Dynamic Routing | Server Network Reachability |
| 7 | M7 | Advanced DHCP | DHCP Relay | Central DHCP |
| 8 | M8 | Advanced DNS | DNS Integration | DNS Infrastructure |
| 9 | M9 | Active Directory | Network Integration | Advanced AD DS |
| 10 | M10 | Users / Groups / OU | Access Design | AD Administration |
| 11 | M11 | Group Policy | Network Policy | Advanced GPO |
| 12 | M12 | File Server & NTFS | VLAN Access | SMB + Permissions |
| 13 | M13 | IIS Web Server | Server VLAN | IIS Deployment |
| 14 | M14 | Cisco + Windows Security | SSH / ACL | Firewall / RDP |
| 15 | M15 | Integrated Troubleshooting | Fault Isolation | Server Troubleshooting |
| 16 | M16 | Capstone + Final Exam | Enterprise Network | Enterprise Server |

---

# MODULE 1 — ADVANCED IPv4 & VLSM

## Learning Objectives

សិស្សអាច៖

- Perform IPv4 Subnetting
- Perform **VLSM**
- Design IP Addressing for multiple departments
- Assign subnets to VLANs
- Assign IP networks to Windows Servers
- Verify routing and connectivity

## Key Terms

`IPv4`  
`Subnet Mask`  
`CIDR`  
`VLSM`  
`Network Address`  
`Broadcast Address`  
`Default Gateway`

## Lecture Notes

Example requirement:

```text
ADMIN   = 100 Hosts
USERS   = 200 Hosts
SERVER  = 50 Hosts
GUEST   = 50 Hosts
WAN     = 2 Hosts
```

សិស្សត្រូវរៀបចំ Subnets ឱ្យមានប្រសិទ្ធភាព ហើយភ្ជាប់ Subnet នីមួយៗទៅ VLAN និង Server/Client Role ត្រឹមត្រូវ។

## Cisco Commands

```text
show ip interface brief
show ip route
```

## Windows Commands

```cmd
ipconfig /all
ping
tracert
```

```powershell
Get-NetIPConfiguration
Test-NetConnection
```

## Cisco Packet Tracer Lab

Design:

```text
R1 ---- R2 ---- SW3
            /        \
          SW1        SW2
```

Assign VLSM networks to departments.

## Windows Server Lab

Create an IP Addressing Table for:

```text
DC1
SRV1
WEB1
CLIENTS
```

## Homework

20 VLSM problems.

## Quiz

20 Questions.

## Module Practical Exam

Create a complete VLSM plan from business requirements.

---

# MODULE 2 — VLAN & TRUNKING

## Learning Objectives

សិស្សអាច៖

- Create VLANs
- Assign Access Ports
- Configure Trunk Ports
- Understand VLAN segmentation
- Connect Windows Servers to Server VLAN
- Troubleshoot VLAN connectivity

## Key Terms

`VLAN`  
`Access Port`  
`Trunk`  
`802.1Q`  
`Native VLAN`  
`Management VLAN`

## Cisco Commands

```text
vlan 10
name ADMIN

vlan 20
name USERS

vlan 30
name SERVERS

vlan 99
name MANAGEMENT
```

Access Port:

```text
interface fastEthernet 0/1
switchport mode access
switchport access vlan 10
```

Trunk:

```text
interface gigabitEthernet 0/1
switchport mode trunk
```

Verify:

```text
show vlan brief
show interfaces trunk
```

## Packet Tracer Lab

Build a multi-VLAN campus:

```text
VLAN 10 = ADMIN
VLAN 20 = USERS
VLAN 30 = SERVERS
VLAN 40 = GUEST
VLAN 99 = MANAGEMENT
```

## Windows Server Lab

Connect:

```text
DC1  → VLAN 30
SRV1 → VLAN 30
WEB1 → VLAN 30
```

Test access from user VLANs.

## Homework

Explain **Access Port vs Trunk Port**.

## Quiz

15 Questions.

## Module Practical Exam

Configure and troubleshoot five VLANs.

---

# MODULE 3 — STP / RSTP

## Learning Objectives

សិស្សអាច៖

- Explain Layer 2 Loop
- Explain **STP**
- Understand **Root Bridge**
- Understand **Root Port** and **Designated Port**
- Configure **RSTP**
- Troubleshoot Layer 2 redundancy

## Key Terms

`STP`  
`RSTP`  
`BPDU`  
`Root Bridge`  
`Root Port`  
`Designated Port`  
`Path Cost`

## Cisco Commands

```text
show spanning-tree
show spanning-tree vlan 10
```

RSTP:

```text
spanning-tree mode rapid-pvst
```

Root:

```text
spanning-tree vlan 10 root primary
```

## Packet Tracer Lab

```text
             SW1
            /   \
           /     \
         SW2-----SW3
```

Create redundancy and observe STP.

## Windows Server Integration Lab

Discuss why Network Redundancy is important for:

```text
DNS
DHCP
AD DS
File Server
```

## Homework

Draw STP topology and identify Port Roles.

## Quiz

20 Questions.

## Module Practical Exam

STP Analysis + Root Bridge Design + Troubleshooting.

---

# MODULE 4 — ETHERCHANNEL / LACP

## Learning Objectives

សិស្សអាច៖

- Explain EtherChannel
- Understand **LACP**
- Configure Port-Channel
- Configure EtherChannel Trunk
- Troubleshoot link mismatch

## Key Terms

`EtherChannel`  
`LACP`  
`PAgP`  
`Port-Channel`

## Cisco Commands

```text
interface range gigabitEthernet 0/1-2
channel-group 1 mode active
```

```text
interface port-channel 1
switchport mode trunk
```

Verify:

```text
show etherchannel summary
```

## Packet Tracer Lab

Connect SW1 and SW2 using multiple links.

Create:

```text
Port-Channel 1
LACP
Trunk
```

## Windows Server Integration Lab

Use Server VLAN traffic across redundant switch links.

Test file and DNS access when one physical link is disconnected.

## Homework

Explain **STP vs EtherChannel**.

## Quiz

15 Questions.

## Module Practical Exam

Configure LACP and test link failure.

---

# MODULE 5 — LAYER 3 SWITCHING

## Learning Objectives

សិស្សអាច៖

- Understand Layer 2 vs Layer 3 Switch
- Configure **SVI**
- Enable IP Routing
- Perform Inter-VLAN Routing on a Layer 3 Switch
- Connect Server VLANs to routed networks

## Key Terms

`Layer 3 Switch`  
`SVI`  
`IP Routing`  
`Routed Port`

## Cisco Commands

```text
ip routing
```

SVI:

```text
interface vlan 10
ip address 192.168.10.1 255.255.255.0
no shutdown
```

Routed interface:

```text
interface gigabitEthernet 0/1
no switchport
ip address 10.0.0.5 255.255.255.252
no shutdown
```

Verify:

```text
show ip interface brief
show ip route
```

## Packet Tracer Lab

```text
VLAN 10 ─┐
VLAN 20 ─┼─ SW3 (L3)
VLAN 30 ─┘
          |
          R2
```

## Windows Server Lab

Place DC1, SRV1 and WEB1 in VLAN 30.

Test reachability from VLAN 10 and VLAN 20.

## Homework

Compare:

**Router-on-a-Stick vs Layer 3 Switch**

## Quiz

15 Questions.

## Module Practical Exam

Configure Layer 3 Switching for three VLANs.

---

# MODULE 6 — OSPF DYNAMIC ROUTING

## Learning Objectives

សិស្សអាច៖

- Explain Dynamic Routing
- Configure **OSPF**
- Configure Router ID
- Establish OSPF Neighbor Adjacency
- Verify OSPF Routes
- Integrate routed networks with Windows Server VLANs

## Key Terms

`OSPF`  
`Router ID`  
`Neighbor`  
`Adjacency`  
`Area 0`  
`LSA`  
`Cost`

## Cisco Commands

```text
router ospf 1
router-id 1.1.1.1
network 10.0.0.0 0.0.0.255 area 0
network 192.168.30.0 0.0.0.255 area 0
```

Verify:

```text
show ip ospf neighbor
show ip route ospf
show ip protocols
```

## Packet Tracer Lab

```text
LAN-A -- R1 ---- R2 ---- R3 -- LAN-C
```

Configure OSPF Area 0.

## Windows Server Lab

Verify that:

```text
VLAN 10 Client
      ↓
OSPF Network
      ↓
Server VLAN 30
```

can reach the required services.

## Homework

Explain how OSPF learns a remote Server Network.

## Quiz

20 Questions.

## Module Practical Exam

Three-router OSPF + Server VLAN reachability.

---

# MODULE 7 — ADVANCED DHCP & DHCP RELAY

## Learning Objectives

សិស្សអាច៖

- Configure centralized DHCP
- Create multiple DHCP Scopes
- Configure Reservations
- Configure Exclusions
- Understand **DHCP Relay**
- Integrate DHCP with VLANs
- Troubleshoot DHCP failures

## Key Terms

`DHCP`  
`Scope`  
`Lease`  
`Reservation`  
`Exclusion`  
`DHCP Relay`  
`ip helper-address`

## Cisco Command

```text
interface vlan 10
ip helper-address 192.168.30.20
```

## Windows Server

Create DHCP Scopes for:

```text
VLAN 10
VLAN 20
VLAN 40
```

Example:

```text
VLAN 10:
192.168.10.100 - 192.168.10.200

VLAN 20:
192.168.20.100 - 192.168.20.200

VLAN 40:
192.168.40.100 - 192.168.40.200
```

## Client Commands

```cmd
ipconfig /release
ipconfig /renew
ipconfig /all
```

## Packet Tracer Lab

Test DHCP Relay between VLANs.

## Windows Server Lab

SRV1 acts as centralized DHCP Server.

## Homework

Explain DHCP DORA and DHCP Relay.

## Quiz

20 Questions.

## Module Practical Exam

Multi-VLAN DHCP with Relay.

---

# MODULE 8 — ADVANCED DNS INFRASTRUCTURE

## Learning Objectives

សិស្សអាច៖

- Manage DNS Zones
- Create A / CNAME / PTR Records
- Understand Forward Lookup Zone
- Understand Reverse Lookup Zone
- Configure DNS Forwarders
- Troubleshoot DNS
- Understand DNS in Active Directory

## Key Terms

`DNS`  
`Forward Lookup Zone`  
`Reverse Lookup Zone`  
`A Record`  
`AAAA Record`  
`CNAME`  
`PTR`  
`Forwarder`

## PowerShell

```powershell
Get-DnsServerZone
Get-DnsServerResourceRecord
```

## Client Commands

```cmd
nslookup
ipconfig /flushdns
ipconfig /registerdns
```

## Lab

Create:

```text
corp.local
```

Records:

```text
dc1.corp.local       → 192.168.30.10
files.corp.local     → 192.168.30.20
web.corp.local       → 192.168.30.30
```

## Cisco Integration Lab

Test DNS access across VLANs and routed networks.

## Homework

Draw the DNS resolution process from Client → DNS → Server.

## Quiz

20 Questions.

## Module Practical Exam

DNS configuration + cross-VLAN Name Resolution.

---

# MODULE 9 — ADVANCED ACTIVE DIRECTORY

## Learning Objectives

សិស្សអាច៖

- Manage **AD DS**
- Understand Domain Controller Roles
- Manage Computer Accounts
- Understand **Global Catalog**
- Understand basic **FSMO Roles**
- Use PowerShell for AD management

## Key Terms

`AD DS`  
`Domain Controller`  
`Global Catalog`  
`FSMO`  
`Domain`  
`Forest`  
`Computer Account`

## PowerShell

```powershell
Get-ADDomain
Get-ADForest
Get-ADDomainController
```

Users:

```powershell
Get-ADUser -Filter *
```

Computers:

```powershell
Get-ADComputer -Filter *
```

## Lab

Deploy:

```text
DC1
```

Domain:

```text
corp.local
```

Create multiple organizational departments.

## Cisco Integration Lab

Verify:

```text
Client VLAN
   ↓
Cisco Routing
   ↓
Server VLAN
   ↓
DC1
```

## Homework

Explain **Domain vs Domain Controller vs Forest**.

## Quiz

20 Questions.

## Module Practical Exam

AD DS Administration + Network Integration.

---

# MODULE 10 — USERS, GROUPS, OU & DELEGATION

## Learning Objectives

សិស្សអាច៖

- Design OU structure
- Create Users
- Create Groups
- Manage Group Membership
- Manage Computer Accounts
- Understand basic Delegation

## OU Structure

```text
corp.local
│
├── ADMIN
├── HR
├── FINANCE
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
5 OUs
5 Groups
30 Users
```

## Cisco Integration Lab

Map departments to VLANs:

```text
ADMIN   → VLAN 10
USERS   → VLAN 20
SERVER  → VLAN 30
GUEST   → VLAN 40
```

## Homework

Create an **OU + VLAN + Group Matrix**.

## Quiz

15 Questions.

## Module Practical Exam

Manage Users, Groups, OUs and department mapping.

---

# MODULE 11 — ADVANCED GROUP POLICY

## Learning Objectives

សិស្សអាច៖

- Create GPO
- Link GPO to OU
- Understand GPO Inheritance
- Understand GPO Scope
- Use Security Filtering
- Troubleshoot GPO

## Key Terms

`GPO`  
`GPMC`  
`Inheritance`  
`Link`  
`Security Filtering`

## Commands

```cmd
gpupdate /force
gpresult /r
gpresult /h report.html
```

## Lab

Create:

```text
GPO-SECURITY
GPO-STUDENT
GPO-ADMIN
GPO-WORKSTATION
```

Apply to correct OUs.

## Cisco Integration Lab

Explain:

```text
Cisco VLAN
     ↓
Network Access
     ↓
Windows Domain
     ↓
GPO
     ↓
User / Computer Policy
```

## Homework

Design 5 GPOs for a school/company.

## Quiz

20 Questions.

## Module Practical Exam

Troubleshoot a GPO that is not applying.

---

# MODULE 12 — FILE SERVER, SMB & NTFS

## Learning Objectives

សិស្សអាច៖

- Configure File Server
- Configure SMB Share
- Configure NTFS Permissions
- Use Security Groups for access
- Understand Share vs NTFS Permissions
- Access Files across VLANs

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
├── FINANCE
├── IT
└── PUBLIC
```

## PowerShell

```powershell
New-Item -Path "D:\Company" -ItemType Directory
```

```powershell
Get-SmbShare
```

```powershell
Get-Acl "D:\Company"
```

## Lab

Permissions:

```text
ADMIN    → Full Control
HR       → Modify
FINANCE  → Modify
IT       → Modify
PUBLIC   → Read
```

## Cisco Integration Lab

Verify Clients from multiple VLANs can access:

```text
\\SRV1\Company
```

according to security policy.

## Homework

Create a Permission Matrix.

## Quiz

20 Questions.

## Module Practical Exam

SMB + NTFS + VLAN access troubleshooting.

---

# MODULE 13 — IIS WEB SERVER

## Learning Objectives

សិស្សអាច៖

- Install IIS
- Create a Website
- Configure Bindings
- Understand HTTP / HTTPS
- Configure DNS for websites
- Test web access across VLANs

## Key Terms

`IIS`  
`Website`  
`Binding`  
`Application Pool`  
`HTTP`  
`HTTPS`

## PowerShell

```powershell
Install-WindowsFeature Web-Server -IncludeManagementTools
```

## Lab

WEB1:

```text
IP:
192.168.30.30
```

DNS:

```text
www.corp.local → 192.168.30.30
```

Website:

```text
http://www.corp.local
```

## Cisco Integration Lab

Verify:

```text
VLAN 10 Client
      ↓
Cisco Network
      ↓
WEB1
```

## Homework

Explain:

**DNS + HTTP + IIS** interaction.

## Quiz

15 Questions.

## Module Practical Exam

Deploy and test an IIS website from another VLAN.

---

# MODULE 14 — CISCO + WINDOWS SECURITY

## Learning Objectives

សិស្សអាច៖

- Configure Cisco SSH
- Configure basic Cisco ACL
- Configure Windows Firewall
- Secure RDP
- Apply Least Privilege
- Understand network segmentation

## Cisco SSH Commands

```text
hostname R1
ip domain-name corp.local
username admin privilege 15 secret StrongPassword
crypto key generate rsa
```

```text
line vty 0 4
login local
transport input ssh
```

## Cisco ACL Example

```text
access-list 100 deny ip 192.168.40.0 0.0.0.255 192.168.30.0 0.0.0.255
access-list 100 permit ip any any
```

Apply:

```text
interface vlan 40
ip access-group 100 in
```

## Windows Firewall

```powershell
Get-NetFirewallProfile
```

## Lab Security Policy

```text
GUEST → Internet Only
GUEST → Internal Servers = Denied
ADMIN → Servers = Allowed
IT → Servers = Allowed
```

## Homework

Create a Cisco + Windows Security Checklist.

## Quiz

20 Questions.

## Module Practical Exam

Implement and test a basic integrated security policy.

---

# MODULE 15 — INTEGRATED TROUBLESHOOTING

## Learning Objectives

សិស្សអាច៖

- Troubleshoot Layer 1–3
- Troubleshoot VLAN / Trunk
- Troubleshoot DHCP
- Troubleshoot DNS
- Troubleshoot AD DS
- Troubleshoot GPO
- Troubleshoot File Server
- Troubleshoot IIS
- Identify Root Cause

## Troubleshooting Framework

```text
1. Identify Problem
2. Gather Evidence
3. Establish Theory
4. Test Theory
5. Implement Fix
6. Verify
7. Document
```

## Cisco Commands

```text
show ip interface brief
show vlan brief
show interfaces trunk
show spanning-tree
show etherchannel summary
show ip route
show ip ospf neighbor
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

Instructor creates **20 faults**:

```text
Wrong VLAN
Wrong Trunk
STP Problem
EtherChannel Problem
Wrong IP
Wrong Gateway
OSPF Failure
DHCP Failure
DNS Failure
AD Failure
Domain Join Failure
GPO Failure
SMB Failure
NTFS Permission Failure
IIS Failure
RDP Failure
SSH Failure
Firewall Failure
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

Professional Troubleshooting Report.

## Quiz

25 Scenario Questions.

## Module Practical Exam

**Integrated Cisco + Windows Server Troubleshooting Challenge**

---

# MODULE 16 — CAPSTONE PROJECT + FINAL EXAM

# PROJECT TITLE

## ABC Technology School — Integrated Cisco & Windows Server Infrastructure

---

# BUSINESS REQUIREMENTS

ABC Technology School has:

```text
ADMIN
HR
FINANCE
IT
TEACHER
STUDENT
SERVER
```

The school requires:

```text
Network Connectivity
VLAN Segmentation
Routing
Central Authentication
DNS
DHCP
File Sharing
Web Server
Security
Remote Management
```

---

# FINAL NETWORK TOPOLOGY

```text
                            INTERNET
                               |
                              R1
                               |
                              R2
                               |
                         SW3 (L3 Core)
                         /           \
                      SW1             SW2
                    /  |  \         /  |  \
                  PC1 PC2  DC1    PC3 PC4  SRV1
                         |            |
                        WEB1        Clients
```

---

# FINAL VLAN PLAN

| VLAN | Name | Network |
|---:|---|---|
| 10 | ADMIN | 192.168.10.0/24 |
| 20 | USERS | 192.168.20.0/24 |
| 30 | SERVERS | 192.168.30.0/24 |
| 40 | GUEST | 192.168.40.0/24 |
| 99 | MANAGEMENT | 192.168.99.0/24 |

---

# FINAL SERVER PLAN

| Server | Role | IP |
|---|---|---|
| DC1 | AD DS + DNS | 192.168.30.10 |
| SRV1 | DHCP + File Server | 192.168.30.20 |
| WEB1 | IIS | 192.168.30.30 |

---

# FINAL PROJECT TECHNOLOGIES

Students must use technologies already taught in Modules 1–15:

```text
IPv4 / VLSM
VLAN
Trunk
STP / RSTP
EtherChannel
Layer 3 Switching
OSPF
DHCP / DHCP Relay
DNS
AD DS
Users / Groups / OU
GPO
SMB
NTFS
IIS
SSH
ACL
Windows Firewall
RDP
PowerShell
Troubleshooting
```

---

# FINAL PROJECT REQUIREMENTS

## Cisco

Configure:

```text
Hostname
IPv4
VLANs
Access Ports
Trunks
STP / RSTP
EtherChannel
Layer 3 Switching
OSPF
SSH
ACL
```

## Windows Server

Configure:

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
SMB
NTFS Permissions
IIS
RDP
Windows Firewall
```

## Windows Clients

Clients must:

```text
Receive DHCP Address
Resolve DNS
Join Domain
Login with Domain Account
Receive GPO
Access File Server
Access IIS Website
```

---

# FINAL PROJECT TESTING

Students must demonstrate:

```text
[✓] PC → Default Gateway
[✓] VLAN → VLAN
[✓] Client → DHCP
[✓] Client → DNS
[✓] Client → Domain Controller
[✓] Domain Login
[✓] Client → File Server
[✓] Client → IIS Website
[✓] SSH → Cisco Device
[✓] RDP → Windows Server
[✓] Guest Restrictions
[✓] Troubleshooting
```

---

# FINAL PROJECT DOCUMENTATION

Students submit:

1. Network Diagram
2. IP Addressing Table
3. VLAN Table
4. Cisco Configuration
5. Server Inventory
6. AD DS Structure
7. DNS Design
8. DHCP Design
9. GPO Design
10. File Permission Matrix
11. Security Policy
12. Testing Results
13. Troubleshooting Report
14. PowerShell Scripts

---

# FINAL EXAM

## PART A — THEORY

**100 Questions**

| Topic | Questions |
|---|---:|
| Network Fundamentals & IPv4/VLSM | 10 |
| VLAN / Trunk | 8 |
| STP / RSTP | 7 |
| EtherChannel | 6 |
| Layer 3 Switching | 7 |
| OSPF | 10 |
| DHCP / DHCP Relay | 8 |
| DNS | 8 |
| AD DS | 10 |
| Users / Groups / OU | 5 |
| GPO | 7 |
| File Server / SMB / NTFS | 6 |
| IIS | 4 |
| Security / SSH / ACL / Firewall | 7 |
| Troubleshooting | 7 |
| **TOTAL** | **100** |

---

# PART B — SUBNETTING

Students solve:

```text
Network Address
Broadcast Address
First Host
Last Host
Prefix
Subnet Mask
Host Capacity
VLSM
```

---

# PART C — CISCO PRACTICAL

**100 Points**

Students configure:

```text
IPv4
VLAN
Trunk
STP
EtherChannel
SVI
OSPF
SSH
ACL
```

---

# PART D — WINDOWS SERVER PRACTICAL

**100 Points**

Students configure:

```text
IP Address
DNS
DHCP
AD DS
Users
Groups
OU
GPO
SMB
NTFS
IIS
RDP
Firewall
```

---

# PART E — TROUBLESHOOTING

Students receive a broken integrated environment.

Possible problems:

```text
Cisco VLAN Failure
Cisco Trunk Failure
OSPF Failure
DHCP Failure
DNS Failure
AD Failure
GPO Failure
File Permission Failure
IIS Failure
Security Policy Failure
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

---

# INTERMEDIATE SKILL CHECKLIST

```text
[✓] Advanced IPv4 / VLSM
[✓] VLAN
[✓] Trunk
[✓] STP / RSTP
[✓] EtherChannel / LACP
[✓] Layer 3 Switching
[✓] OSPF
[✓] DHCP Relay
[✓] Advanced DNS
[✓] Active Directory
[✓] Users / Groups / OU
[✓] Group Policy
[✓] SMB / File Server
[✓] NTFS Permissions
[✓] IIS
[✓] SSH
[✓] ACL
[✓] Windows Firewall
[✓] RDP
[✓] PowerShell
[✓] Integrated Troubleshooting
```

---

# COMPLETE LEARNING PATH

```text
LEVEL 1 — BASIC
        ↓
Cisco Router / Switch
        ↓
IPv4
        ↓
VLAN
        ↓
Inter-VLAN Routing
        ↓
Windows Server
        ↓
DNS
        ↓
DHCP
        ↓
AD DS
        ↓
Domain Join
        ↓
GPO
        ↓
File Server
        ↓

LEVEL 2 — INTERMEDIATE
        ↓
VLSM
        ↓
Advanced VLAN / Trunk
        ↓
STP / RSTP
        ↓
EtherChannel
        ↓
Layer 3 Switching
        ↓
OSPF
        ↓
DHCP Relay
        ↓
Advanced DNS
        ↓
Advanced AD DS
        ↓
GPO Management
        ↓
SMB / NTFS
        ↓
IIS
        ↓
SSH / ACL / Firewall
        ↓
PowerShell
        ↓
Integrated Troubleshooting
        ↓
ENTERPRISE CAPSTONE
```

# FINAL TARGET

នៅចុង **Windows Server & Cisco Network Infrastructure — Intermediate** សិស្សគួរតែអាចផ្លាស់ពី៖

```text
Basic IT Technician
```

ទៅជា៖

```text
Junior Network / System Administrator
```

ដែលអាច **Design → Configure → Integrate → Verify → Secure → Troubleshoot** ទាំង **Cisco Network Infrastructure** និង **Windows Server Infrastructure** ក្នុង Environment តែមួយ។
