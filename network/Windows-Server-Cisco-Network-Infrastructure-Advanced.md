# WINDOWS SERVER & CISCO NETWORK INFRASTRUCTURE
## Level 3 — Advanced

**Duration:** 16 Weeks  
**Study Time:** 4 Hours/Week  
**Total:** 64 Hours  
**Prerequisite:** Windows Server & Cisco Network Infrastructure — Intermediate  
**Lab:** Cisco Packet Tracer + Hyper-V / VMware / VirtualBox  
**OS:** Windows Server 2022/2025, Windows 10/11

---

## 1. Course Overview

វគ្គសិក្សា **Windows Server & Cisco Network Infrastructure — Advanced** ផ្តោតលើការរចនា និងគ្រប់គ្រង Enterprise Network Infrastructure ដែលបញ្ចូល **Cisco Networking + Windows Server** ជាមួយគ្នា។ សិស្សនឹងអនុវត្តលើ Advanced Routing, Enterprise Switching, Active Directory, GPO, DNS/DHCP Resilience, File Services, IIS, Hyper-V, PowerShell, Security, High Availability, Backup/Disaster Recovery និង Integrated Troubleshooting។

---

## 2. Lab Environment

### Cisco Devices

- R1, R2, R3 — Routers
- SW1, SW2, SW3, SW4 — Switches

### Windows Server VMs

- DC1
- DC2
- FS1
- FS2
- WEB1
- WEB2
- MGMT1
- CLIENT1
- CLIENT2
- CLIENT3

### Domain

`corp.local`

### VLAN / IP Addressing

| VLAN | Name | Network |
|---|---|---|
| 10 | ADMIN | 192.168.10.0/24 |
| 20 | USERS | 192.168.20.0/24 |
| 30 | SERVERS | 192.168.30.0/24 |
| 40 | GUEST | 192.168.40.0/24 |
| 99 | MANAGEMENT | 192.168.99.0/24 |

### Server IPs

| Server | IP Address |
|---|---|
| DC1 | 192.168.30.10 |
| DC2 | 192.168.30.11 |
| FS1 | 192.168.30.20 |
| FS2 | 192.168.30.21 |
| WEB1 | 192.168.30.30 |
| WEB2 | 192.168.30.31 |
| MGMT1 | 192.168.99.10 |

---

# SEMESTER MODULES

## Module 1 — Enterprise Network Design

### Learning Objectives

- Understand Enterprise Network Architecture
- Design hierarchical network topology
- Separate Core, Distribution, and Access layers
- Plan VLANs, IP addressing, routing, and management networks
- Build a scalable network design

### Lecture Notes

- Enterprise Network Architecture
- Core / Distribution / Access
- Network Segmentation
- Server Network Design
- Management Network
- Redundancy and scalability
- IP Address Planning
- Documentation and naming standards

### Key Terms

`Enterprise Network`, `Core Layer`, `Distribution Layer`, `Access Layer`, `Scalability`, `Redundancy`, `Segmentation`, `Network Design`, `Management VLAN`

### Cisco IOS Commands

```cisco
show running-config
show startup-config
show ip interface brief
show interfaces status
show vlan brief
show cdp neighbors detail
```

### Windows / PowerShell Commands

```powershell
Get-NetIPConfiguration
Get-NetAdapter
Get-ComputerInfo
hostname
```

### Cisco Packet Tracer Lab

- Design Enterprise Topology
- Configure VLANs
- Configure Management Network
- Create redundant switch links
- Document IP and VLAN plan

### Windows Server Lab

- Deploy DC1, DC2, FS1, FS2, WEB1, WEB2, MGMT1
- Assign static IP addresses
- Configure hostnames
- Join servers to `corp.local`

### Homework

Create an Enterprise Network topology diagram and IP Address Plan.

### Quiz

10 questions on Enterprise Network Design.

### Module Practical Exam

Design and configure the base enterprise topology.

---

## Module 2 — Advanced IPv4 / VLSM

### Learning Objectives

- Perform advanced VLSM subnetting
- Calculate subnet sizes based on host requirements
- Design efficient IP addressing
- Verify routing and subnet boundaries

### Lecture Notes

- Advanced VLSM
- Variable subnet sizes
- Network planning
- Route summarization concepts
- Address utilization

### Cisco IOS Commands

```cisco
show ip route
show ip interface brief
show running-config | section interface
```

### Windows / PowerShell Commands

```powershell
Get-NetIPAddress
Get-NetRoute
Test-NetConnection
```

### Cisco Packet Tracer Lab

- Create VLSM plan
- Configure router interfaces
- Configure point-to-point links
- Verify connectivity

### Windows Server Lab

- Configure server static addressing
- Verify gateway and DNS settings

### Homework

Create VLSM addressing for a multi-site enterprise network.

### Quiz

10 questions on IPv4/VLSM.

### Module Practical Exam

Build and verify a VLSM-based IPv4 network.

---

## Module 3 — Advanced VLAN & STP

### Learning Objectives

- Configure enterprise VLANs
- Configure Trunking
- Understand STP/RSTP
- Configure STP root bridge
- Prevent Layer 2 loops

### Lecture Notes

- VLAN design
- 802.1Q Trunk
- Native VLAN
- STP fundamentals
- RSTP
- Root Bridge
- Port roles and states
- STP troubleshooting

### Cisco IOS Commands

```cisco
vlan 10
name ADMIN
vlan 20
name USERS
vlan 30
name SERVERS
vlan 40
name GUEST
vlan 99
name MANAGEMENT

interface range g0/1-2
switchport mode trunk

spanning-tree mode rapid-pvst
spanning-tree vlan 10 root primary
spanning-tree vlan 20 root secondary
show spanning-tree
show interfaces trunk
```

### Windows / PowerShell Commands

```powershell
Get-NetAdapter
Get-NetIPConfiguration
```

### Cisco Packet Tracer Lab

- Create VLAN 10/20/30/40/99
- Configure Access Ports
- Configure Trunk Ports
- Configure RSTP
- Select Root Bridge
- Troubleshoot STP loops

### Windows Server Lab

- Connect servers to Server VLAN
- Verify VLAN connectivity using `ping` and `Test-NetConnection`

### Homework

Explain how STP prevents Layer 2 loops.

### Quiz

10 questions.

### Module Practical Exam

Configure multi-VLAN switched network with RSTP.

---

## Module 4 — EtherChannel & Layer 3 Switching

### Learning Objectives

- Configure EtherChannel
- Understand LACP
- Configure Layer 3 switching
- Configure SVI-based routing

### Cisco IOS Commands

```cisco
interface range g0/1-2
channel-group 1 mode active

interface port-channel 1
switchport mode trunk

show etherchannel summary
show interfaces port-channel 1

interface vlan 10
ip address 192.168.10.1 255.255.255.0
no shutdown

ip routing
show ip route
```

### Cisco Packet Tracer Lab

- Configure LACP EtherChannel
- Configure trunk EtherChannel
- Configure SVIs
- Enable inter-VLAN routing

### Windows Server Lab

- Test routing between server and client VLANs

### Homework

Compare STP redundancy and EtherChannel redundancy.

### Quiz

5 questions.

### Module Practical Exam

Configure EtherChannel and Layer 3 Switching.

---

## Module 5 — Advanced OSPF

### Learning Objectives

- Configure multi-router OSPF
- Understand OSPF areas
- Configure router IDs
- Analyze OSPF neighbors and routes
- Troubleshoot OSPF

### Lecture Notes

- OSPF Process
- Router ID
- Neighbor Adjacency
- Area 0
- Multi-area concepts
- Cost
- Passive Interface
- Route Selection

### Cisco IOS Commands

```cisco
router ospf 1
router-id 1.1.1.1
network 192.168.10.0 0.0.0.255 area 0
network 10.0.0.0 0.0.0.3 area 0
passive-interface g0/0

show ip ospf neighbor
show ip ospf interface brief
show ip route ospf
show ip protocols
```

### Cisco Packet Tracer Lab

- Configure OSPF on R1/R2/R3
- Verify neighbor relationships
- Manipulate OSPF cost
- Troubleshoot adjacency

### Windows Server Lab

- Verify server-to-server reachability across routed networks

### Homework

Explain OSPF neighbor formation and route selection.

### Quiz

10 questions.

### Module Practical Exam

Build and troubleshoot an OSPF enterprise network.

---

## Module 6 — IPv6 Dual Stack

### Learning Objectives

- Configure IPv6
- Understand Global Unicast / Link-Local addresses
- Configure IPv6 routing
- Deploy IPv4 + IPv6 Dual Stack

### Cisco IOS Commands

```cisco
ipv6 unicast-routing

interface g0/0
ipv6 address 2001:DB8:30:1::1/64
no shutdown

show ipv6 interface brief
show ipv6 route
ping ipv6 2001:DB8:30:1::10
```

### Cisco Packet Tracer Lab

- Configure IPv6 addressing
- Configure IPv6 routing
- Test Dual Stack

### Windows Server Lab

```powershell
Get-NetIPAddress -AddressFamily IPv6
Test-NetConnection -ComputerName dc1.corp.local -Port 53
```

### Homework

Create an IPv6 addressing plan for the enterprise.

### Quiz

5 questions.

### Module Practical Exam

Configure and verify IPv4/IPv6 Dual Stack.

---

## Module 7 — Advanced Active Directory

### Learning Objectives

- Manage Enterprise Active Directory
- Understand Domain Controllers
- Configure FSMO roles
- Manage Sites and Services
- Perform delegated administration

### Lecture Notes

- AD DS architecture
- Domain Controllers
- FSMO roles
- Global Catalog
- Organizational Units
- Delegation
- Group and computer management

### PowerShell Commands

```powershell
Get-ADDomain
Get-ADForest
Get-ADDomainController -Filter *
netdom query fsmo
Get-ADUser -Filter *
Get-ADComputer -Filter *
```

### Windows Server Lab

- Promote DC2 as additional Domain Controller
- Verify replication
- Query FSMO roles
- Create OUs and administrative groups
- Delegate OU administration

### Homework

Document FSMO roles and their responsibilities.

### Quiz

10 questions.

### Module Practical Exam

Deploy and verify a multi-DC Active Directory environment.

---

## Module 8 — AD Replication, Sites & FSMO

### Learning Objectives

- Understand AD replication
- Configure AD Sites
- Analyze replication health
- Manage FSMO roles
- Troubleshoot replication issues

### Commands

```powershell
repadmin /replsummary
repadmin /showrepl
repadmin /syncall
DCDiag /v
netdom query fsmo
```

### Windows Server Lab

- Create AD Site structure
- Configure Site Links
- Verify replication
- Transfer FSMO roles
- Test replication failure and recovery

### Homework

Write an AD replication troubleshooting procedure.

### Quiz

8 questions.

### Module Practical Exam

Configure AD Sites and troubleshoot replication.

---

## Module 9 — Enterprise GPO & Security

### Learning Objectives

- Design Enterprise Group Policy
- Apply Security Policies
- Use GPO inheritance and filtering
- Harden Windows clients and servers

### Lecture Notes

- GPO Scope
- Link / Inheritance
- Security Filtering
- Loopback Processing
- Password Policy
- Account Lockout
- Windows Firewall
- Security Baseline

### Commands

```powershell
gpupdate /force
gpresult /r
gpresult /h C:\Temp\gpo-report.html
Get-GPO -All
Get-GPResultantSetOfPolicy
```

### Windows Server Lab

- Create Enterprise GPO structure
- Configure Password Policy
- Configure Account Lockout
- Configure Windows Firewall
- Restrict Control Panel / USB / RDP as required

### Homework

Create a GPO security baseline.

### Quiz

7 questions.

### Module Practical Exam

Deploy and verify Enterprise GPO security policies.

---

## Module 10 — DNS & DHCP Resilience

### Learning Objectives

- Configure resilient DNS
- Configure DHCP redundancy concepts
- Manage DNS records
- Verify name resolution
- Troubleshoot DNS/DHCP failures

### Windows Commands

```powershell
Get-DnsServerZone
Get-DnsServerResourceRecord -ZoneName "corp.local"
Get-DhcpServerv4Scope
Get-DhcpServerv4Lease
Resolve-DnsName corp.local
ipconfig /all
nslookup corp.local
```

### Windows Server Lab

- Configure DNS on DC1/DC2
- Create A, CNAME, PTR records
- Configure DHCP scopes
- Create reservations
- Test DNS/DHCP service failure scenarios

### Homework

Design a resilient DNS/DHCP service plan.

### Quiz

7 questions.

### Module Practical Exam

Configure and troubleshoot DNS/DHCP services.

---

## Module 11 — DFS, File Services & Storage

### Learning Objectives

- Deploy SMB File Services
- Configure NTFS and Share Permissions
- Build DFS Namespace
- Understand DFS Replication
- Manage storage and quotas

### Commands

```powershell
Get-SmbShare
New-SmbShare
Get-SmbSession
Get-Acl C:\Shares\IT
Get-Volume
Get-Disk
Get-Partition
```

### Windows Server Lab

- Configure FS1 and FS2
- Create department shares
- Apply NTFS permissions
- Apply Share permissions
- Configure DFS Namespace
- Configure DFS Replication

### Homework

Design a departmental file server permission matrix.

### Quiz

5 questions.

### Module Practical Exam

Deploy and troubleshoot DFS/File Services.

---

## Module 12 — IIS & Hyper-V Infrastructure

### Learning Objectives

- Deploy IIS Web Services
- Configure websites and bindings
- Understand Hyper-V virtualization
- Configure virtual networks
- Manage virtual machines

### Commands

```powershell
Get-WindowsFeature Web-Server
Install-WindowsFeature Web-Server -IncludeManagementTools
Get-VM
Get-VMSwitch
Start-VM
Stop-VM
```

### Windows Server Lab

- Deploy WEB1 and WEB2 using IIS
- Configure test website
- Configure bindings and certificates conceptually
- Deploy Hyper-V VMs
- Configure Virtual Switches

### Homework

Compare IIS deployment and Hyper-V virtualization use cases.

### Quiz

3 questions.

### Module Practical Exam

Deploy an IIS service on a virtualized Windows Server environment.

---

## Module 13 — PowerShell Automation

### Learning Objectives

- Automate Windows Server administration
- Query and filter objects
- Create repeatable administration scripts
- Automate user and server management

### Commands

```powershell
Get-Service
Get-Process
Get-WinEvent -LogName System -MaxEvents 20
Get-ADUser -Filter *
Get-ADComputer -Filter *
Get-WindowsFeature
```

### Windows Server Lab

Create PowerShell scripts to:

- Create users
- Create groups
- Query server health
- Export AD reports
- Check services
- Collect event logs

### Homework

Write one PowerShell administration script.

### Quiz

2 questions.

### Module Practical Exam

Automate a routine server administration task.

---

## Module 14 — High Availability & Redundancy

### Learning Objectives

- Understand High Availability
- Design redundant network paths
- Configure redundant servers
- Reduce Single Point of Failure

### Lecture Notes

- High Availability
- Redundancy
- Failover
- Server redundancy
- Network redundancy
- Load balancing concepts
- Cluster concepts

### Cisco Lab

- Redundant uplinks
- EtherChannel
- STP failover
- Routing redundancy concepts

### Windows Server Lab

- DC1/DC2 redundancy
- FS1/FS2 redundancy
- WEB1/WEB2 redundancy
- Test service failover scenarios

### Homework

Identify Single Points of Failure in the capstone topology.

### Quiz

2 questions.

### Module Practical Exam

Demonstrate a failure and verify service continuity.

---

## Module 15 — Backup, Disaster Recovery & Full Troubleshooting

### Learning Objectives

- Build Backup strategy
- Understand Disaster Recovery
- Perform restore testing
- Use structured troubleshooting methodology

### Troubleshooting Methodology

1. Problem
2. Evidence
3. Root Cause
4. Solution/Fix
5. Verification
6. Documentation

### Cisco Commands

```cisco
show ip route
show interfaces
show vlan brief
show interfaces trunk
show spanning-tree
show etherchannel summary
show ip ospf neighbor
show access-lists
show running-config
```

### Windows Commands

```powershell
Get-WinEvent -LogName System -MaxEvents 50
Get-Service
Test-NetConnection
Resolve-DnsName
repadmin /replsummary
DCDiag
```

### Windows Server Lab

- Configure backup jobs
- Test file restore
- Test system recovery concepts
- Simulate DNS outage
- Simulate AD replication issue
- Simulate File Server failure

### Cisco Packet Tracer Lab

- Troubleshoot VLAN issue
- Troubleshoot routing issue
- Troubleshoot OSPF issue
- Troubleshoot trunk/EtherChannel issue

### Homework

Write a complete Incident Troubleshooting Report.

### Quiz

2 questions.

### Module Practical Exam

Diagnose and resolve an integrated Cisco + Windows Server outage.

---

## Module 16 — Final Enterprise Capstone

### Project Title

**Enterprise Network & Windows Server Infrastructure Deployment**

### Project Requirements

#### Cisco

- Enterprise Network Design
- VLAN 10/20/30/40/99
- Trunk
- RSTP
- EtherChannel / LACP
- Layer 3 Switching
- OSPF
- IPv6 Dual Stack
- ACL
- NAT/PAT
- SSH
- Management Network

#### Windows Server

- DC1 + DC2
- Active Directory Domain Services
- FSMO
- AD Replication
- AD Sites
- Enterprise GPO
- DNS
- DHCP
- FS1 + FS2
- SMB / NTFS Permissions
- DFS Namespace
- DFS Replication
- WEB1 + WEB2 with IIS
- Hyper-V
- PowerShell Automation
- Security Hardening
- Backup / Restore

### Required Documentation

- Network Topology Diagram
- IP Address Table
- VLAN Table
- Server Inventory
- AD OU Structure
- GPO Matrix
- DNS/DHCP Plan
- File Permission Matrix
- Backup Plan
- Troubleshooting Report
- Final Configuration Documentation

### Final Practical Assessment

សិស្សត្រូវ Deploy, Configure, Verify និង Troubleshoot ប្រព័ន្ធទាំងមូល ដោយបង្ហាញថា Cisco Network និង Windows Server Infrastructure អាចដំណើរការរួមគ្នាបាន។

---

# FINAL EXAM — PART A
## 100-Question Theory Exam

| Topic | Questions |
|---|---:|
| Enterprise Network Design | 5 |
| IPv4 / VLSM | 10 |
| VLAN / STP / Trunk | 10 |
| EtherChannel / L3 Switching | 5 |
| OSPF | 10 |
| IPv6 | 5 |
| Cisco Security / NAT / SSH | 5 |
| AD DS / FSMO | 10 |
| AD Replication / Sites | 8 |
| GPO | 7 |
| DNS | 7 |
| DHCP | 5 |
| File Services / DFS | 5 |
| IIS / Hyper-V | 3 |
| PowerShell | 2 |
| Windows Security | 2 |
| High Availability | 2 |
| Backup / Disaster Recovery | 2 |
| Troubleshooting | 2 |
| **TOTAL** | **100** |

---

# ASSESSMENT

| Assessment | Weight |
|---|---:|
| Homework | 5% |
| Weekly Quizzes | 10% |
| Cisco Labs | 10% |
| Windows Server Labs | 10% |
| Module Exams | 15% |
| Midterm | 10% |
| Final Capstone Project | 20% |
| Final Exam | 20% |
| **TOTAL** | **100%** |

---

# GRADUATION CHECKLIST

## Cisco Networking

- [ ] Enterprise Network Design
- [ ] VLSM
- [ ] VLAN
- [ ] Trunk
- [ ] RSTP
- [ ] EtherChannel / LACP
- [ ] Layer 3 Switching
- [ ] OSPF
- [ ] IPv6
- [ ] ACL
- [ ] NAT/PAT
- [ ] SSH
- [ ] Network Troubleshooting

## Windows Server

- [ ] Multi-DC Active Directory
- [ ] FSMO
- [ ] AD Replication
- [ ] AD Sites
- [ ] Enterprise GPO
- [ ] DNS
- [ ] DHCP
- [ ] SMB / NTFS Permissions
- [ ] DFS
- [ ] IIS
- [ ] Hyper-V
- [ ] PowerShell
- [ ] Security Hardening
- [ ] High Availability
- [ ] Backup / Restore
- [ ] Disaster Recovery
- [ ] Integrated Troubleshooting
- [ ] Technical Documentation

---

# Recommended Final Skill Level

បន្ទាប់ពីបញ្ចប់វគ្គនេះ សិស្សគួរអាច៖

1. Design Enterprise Network Infrastructure បាន
2. Configure Advanced Cisco Routing & Switching បាន
3. Deploy និង Manage Multi-Server Windows Infrastructure បាន
4. Implement Active Directory, DNS, DHCP, GPO និង File Services បាន
5. Deploy IIS និង Hyper-V Infrastructure បាន
6. Automate Administration ជាមួយ PowerShell បាន
7. Apply Security, Redundancy, Backup និង Disaster Recovery បាន
8. Troubleshoot Cisco + Windows Server End-to-End បាន
9. Produce Professional Network / Server Documentation បាន

---

**Course:** Windows Server & Cisco Network Infrastructure  
**Level:** Advanced  
**Duration:** 16 Weeks / 64 Hours
