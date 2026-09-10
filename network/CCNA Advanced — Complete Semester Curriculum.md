# CCNA ADVANCED
## Advanced Cisco Networking & Enterprise Network Engineering

**Duration:** 16 Weeks  
**Class:** 4 Hours / Week  
**Total:** 64 Hours  
**Prerequisite:** CCNA Beginner + CCNA Intermediate  
**Lab:** Cisco Packet Tracer  
**Focus:** Design + Configure + Verify + Troubleshoot

---

# 1. COURSE PURPOSE

Course នេះមានគោលបំណងឱ្យសិស្សផ្លាស់ពី **Intermediate Network Configuration** ទៅ **Advanced Network Engineering**។

សិស្សនឹងមិនរៀនតែ Command ទេ ប៉ុន្តែត្រូវអាច៖

```text
Analyze
   ↓
Design
   ↓
Configure
   ↓
Verify
   ↓
Troubleshoot
   ↓
Optimize
   ↓
Document
```

---

# 2. COURSE LEARNING OUTCOMES

នៅចុង Course សិស្សអាច៖

- Design Enterprise Network Architecture
- Perform Advanced IPv4/VLSM
- Configure Layer 2 Redundancy
- Configure Advanced STP
- Configure EtherChannel
- Configure Layer 3 Switching
- Configure OSPF Multi-Area Fundamentals
- Configure OSPF Optimization
- Configure IPv6 Routing
- Configure DHCP Relay and Services
- Configure NAT/PAT
- Design Advanced ACL Policies
- Configure Network Device Security
- Perform Network Redundancy
- Troubleshoot complex Cisco networks
- Design a complete enterprise topology
- Explain design decisions professionally

---

# 3. SEMESTER STRUCTURE

| Week | Module | Main Topic | Practical |
|---|---|---|---|
| 1 | M1 | Enterprise Network Design | Network Architecture |
| 2 | M2 | Advanced IPv4 & VLSM | Address Planning |
| 3 | M3 | Advanced VLAN Architecture | VLAN Design |
| 4 | M4 | Advanced STP | STP Optimization |
| 5 | M5 | Advanced EtherChannel | LACP Design |
| 6 | M6 | Layer 3 Switching | Campus Routing |
| 7 | M7 | Advanced OSPF | Multi-Router OSPF |
| 8 | M8 | OSPF Optimization | Routing Troubleshooting |
| 9 | M9 | IPv6 Routing | IPv6 Enterprise |
| 10 | M10 | DHCP / DNS / Services | Central Services |
| 11 | M11 | NAT / PAT / Edge Routing | Internet Edge |
| 12 | M12 | Advanced ACL | Security Policy |
| 13 | M13 | Advanced Device Security | Secure Infrastructure |
| 14 | M14 | Network Redundancy | High Availability |
| 15 | M15 | Advanced Troubleshooting | Fault Injection |
| 16 | M16 | Capstone + Final Exam | Enterprise Project |

---

# MODULE 1 — ENTERPRISE NETWORK DESIGN

## Learning Objectives

សិស្សអាច៖

- Design a small Enterprise Network
- Understand **Core / Distribution / Access**
- Separate Layer 2 and Layer 3 functions
- Select correct Cisco devices
- Create network documentation
- Design scalable topology

## Lecture Notes

### Hierarchical Network Model

```text
             CORE
          /         \
   DISTRIBUTION   DISTRIBUTION
      /   \          /   \
   ACCESS ACCESS   ACCESS ACCESS
```

### Important Keywords

`Access Layer`  
`Distribution Layer`  
`Core Layer`  
`Campus Network`  
`Scalability`  
`Redundancy`  
`Availability`

## Cisco Focus

Students review:

```text
show running-config
show ip interface brief
show vlan brief
show interfaces trunk
show spanning-tree
show ip route
```

## Packet Tracer Lab

Design a school/company network with:

- 2 Core/Distribution devices
- 4 Access Switches
- 5 VLANs
- Multiple departments

## Homework

Create a network diagram and explain why each device is placed where it is.

## Quiz

15 architecture questions.

## Module Practical Exam

Design an Enterprise Network from requirements only.

---

# MODULE 2 — ADVANCED IPv4 & VLSM

## Learning Objectives

Students can:

- Perform complex VLSM
- Design hierarchical IP addressing
- Allocate addresses efficiently
- Perform route summarization
- Build an IP Addressing Plan

## Lecture Notes

Example:

```text
10.10.0.0/16
```

Departments:

```text
ADMIN     = 500 hosts
STUDENT   = 300 hosts
SERVER    = 100 hosts
MANAGEMENT = 50 hosts
WAN       = 2 hosts
```

Students must allocate addresses from largest to smallest.

### Keywords

`VLSM`  
`CIDR`  
`Prefix`  
`Subnetting`  
`Route Summarization`

## Cisco Commands

```text
show ip interface brief
show ip route
```

## Packet Tracer Lab

Create a multi-department IP addressing plan and configure all router interfaces.

## Homework

20 advanced subnetting problems.

## Quiz

20 questions.

## Module Exam

**40% subnetting + 60% practical addressing design**

---

# MODULE 3 — ADVANCED VLAN ARCHITECTURE

## Learning Objectives

Students can:

- Build large VLAN structures
- Understand VLAN segmentation
- Configure Access/Trunk
- Configure Native VLAN
- Understand VLAN management practices

## Keywords

`VLAN`  
`Access VLAN`  
`Trunk VLAN`  
`Native VLAN`  
`Voice VLAN`  
`Management VLAN`

## Cisco Commands

```text
vlan 10
name ADMIN

interface range fastEthernet 0/1-12
switchport mode access
switchport access vlan 10
```

Voice VLAN:

```text
switchport voice vlan 20
```

Trunk:

```text
interface gigabitEthernet 0/1
switchport mode trunk
```

## Verification

```text
show vlan brief
show interfaces trunk
```

## Packet Tracer Lab

Design:

```text
VLAN 10 = ADMIN
VLAN 20 = STUDENT
VLAN 30 = SERVER
VLAN 40 = VOICE
VLAN 99 = MANAGEMENT
```

## Homework

Design VLAN structure for a school with 500 students.

## Quiz

15 questions.

## Practical Exam

Configure and troubleshoot a multi-VLAN campus.

---

# MODULE 4 — ADVANCED STP

## Learning Objectives

Students can:

- Understand STP election process
- Manipulate Root Bridge
- Understand STP priority
- Understand Port Cost
- Use RSTP effectively
- Troubleshoot STP loops

## Keywords

`STP`  
`RSTP`  
`Root Bridge`  
`Root Port`  
`Designated Port`  
`BPDU`  
`Path Cost`

## Cisco Commands

```text
show spanning-tree
show spanning-tree vlan 10
```

Root:

```text
spanning-tree vlan 10 root primary
```

Priority:

```text
spanning-tree vlan 10 priority 24576
```

## Packet Tracer Lab

Three-switch redundant topology:

```text
             SW1
            /   \
           /     \
         SW2-----SW3
```

Configure different Root Bridges for VLANs.

## Homework

Explain why Root Bridge placement matters.

## Quiz

20 questions.

## Module Exam

STP Design + Troubleshooting.

---

# MODULE 5 — ADVANCED ETHERCHANNEL

## Learning Objectives

Students can:

- Design EtherChannel
- Configure LACP
- Troubleshoot bundle mismatch
- Configure Port-Channel trunk
- Verify member interfaces

## Keywords

`EtherChannel`  
`LACP`  
`PAgP`  
`Port-Channel`

## Cisco Commands

```text
interface range gigabitEthernet 0/1-4
channel-group 1 mode active
```

```text
interface port-channel 1
switchport mode trunk
```

Verify:

```text
show etherchannel summary
show interfaces port-channel 1
```

## Packet Tracer Lab

Create redundant links between switches using 4 physical links.

## Homework

Troubleshoot five EtherChannel mismatch scenarios.

## Quiz

15 questions.

## Practical Exam

Build LACP EtherChannel and recover from failure.

---

# MODULE 6 — ADVANCED LAYER 3 SWITCHING

## Learning Objectives

Students can:

- Configure SVI
- Enable IP Routing
- Use Layer 3 interfaces
- Route between VLANs
- Connect campus switches to routers

## Cisco Commands

```text
ip routing
```

SVI:

```text
interface vlan 10
ip address 10.10.10.1 255.255.255.0
no shutdown
```

Layer 3 interface:

```text
interface gigabitEthernet 0/1
no switchport
ip address 10.0.0.1 255.255.255.252
no shutdown
```

Verify:

```text
show ip route
show ip interface brief
```

## Packet Tracer Lab

Create:

```text
Access Switch
      |
Layer 3 Switch
      |
   Router
      |
    WAN
```

## Homework

Compare:

**Layer 2 Switch vs Layer 3 Switch vs Router**

## Quiz

15 questions.

## Module Exam

Design a Layer 3 campus network.

---

# MODULE 7 — ADVANCED OSPF

## Learning Objectives

Students can:

- Configure OSPF
- Understand Router ID
- Understand Areas
- Understand Neighbor Adjacency
- Understand OSPF Route Types
- Understand DR/BDR concept
- Perform basic multi-area design

## Keywords

`OSPF`  
`Area 0`  
`Area`  
`Router ID`  
`Neighbor`  
`Adjacency`  
`DR`  
`BDR`  
`LSA`  
`Cost`

## Cisco Commands

```text
router ospf 1
router-id 1.1.1.1
network 10.10.0.0 0.0.255.255 area 0
```

Passive:

```text
passive-interface gigabitEthernet 0/0
```

## Verification

```text
show ip ospf neighbor
show ip ospf interface
show ip route ospf
show ip protocols
```

## Packet Tracer Lab

```text
      R1
     /  \
    R2   R3
    |     |
   LAN   LAN
```

Build OSPF Area 0.

Then introduce another area:

```text
Area 0
  |
Area 10
```

## Homework

Draw OSPF Areas for a large enterprise.

## Quiz

20 questions.

## Module Exam

Multi-router OSPF configuration + analysis.

---

# MODULE 8 — OSPF OPTIMIZATION & TROUBLESHOOTING

## Learning Objectives

Students can:

- Troubleshoot OSPF Neighbor problems
- Understand OSPF cost
- Configure passive interfaces
- Analyze routing tables
- Identify route failures
- Understand default route propagation

## Commands

```text
show ip ospf neighbor
show ip ospf interface
show ip route
show ip protocols
```

Cost:

```text
ip ospf cost 10
```

Default route:

```text
default-information originate
```

## Packet Tracer Lab

Instructor introduces 10 OSPF faults.

Students must:

```text
Identify
Analyze
Fix
Verify
Document
```

## Homework

Create an OSPF troubleshooting flowchart.

## Quiz

20 scenario questions.

## Practical Exam

Repair a broken enterprise OSPF network.

---

# MODULE 9 — ADVANCED IPv6 ROUTING

## Learning Objectives

Students can:

- Configure IPv6 networks
- Understand Link-Local
- Understand Global Unicast
- Understand SLAAC
- Understand Neighbor Discovery
- Perform IPv6 routing

## Keywords

`IPv6`  
`SLAAC`  
`Link-Local`  
`Global Unicast`  
`Neighbor Discovery`

## Cisco Commands

```text
ipv6 unicast-routing
```

```text
interface gigabitEthernet 0/0
ipv6 address 2001:db8:10::1/64
no shutdown
```

Verify:

```text
show ipv6 interface brief
show ipv6 neighbors
show ipv6 route
```

## Packet Tracer Lab

Build a 3-router IPv6 network.

## Homework

IPv6 addressing worksheet.

## Quiz

15 questions.

## Module Exam

IPv6 Enterprise Connectivity.

---

# MODULE 10 — DHCP, DNS & NETWORK SERVICES

## Learning Objectives

Students can:

- Design centralized DHCP
- Configure DHCP Relay
- Understand DNS
- Understand network service dependency
- Troubleshoot client addressing

## Cisco Commands

```text
ip dhcp pool USERS
network 10.10.10.0 255.255.255.0
default-router 10.10.10.1
dns-server 8.8.8.8
```

Relay:

```text
interface vlan 20
ip helper-address 10.10.100.10
```

Verify:

```text
show ip dhcp binding
show ip dhcp pool
```

## Packet Tracer Lab

Create centralized services:

```text
Clients → VLANs → L3 Switch → Server VLAN
```

Server provides:

- DHCP
- DNS
- HTTP

## Homework

Explain how DHCP, DNS and HTTP work together.

## Quiz

15 questions.

## Module Exam

Centralized network service configuration.

---

# MODULE 11 — NAT, PAT & INTERNET EDGE

## Learning Objectives

Students can:

- Understand NAT design
- Configure PAT
- Configure static NAT
- Identify Inside/Outside interfaces
- Troubleshoot Internet access

## Keywords

`NAT`  
`PAT`  
`Static NAT`  
`Dynamic NAT`  
`Inside`  
`Outside`

## Commands

PAT:

```text
access-list 1 permit 10.0.0.0 0.255.255.255

interface gigabitEthernet 0/0
ip nat inside

interface gigabitEthernet 0/1
ip nat outside

ip nat inside source list 1 interface gigabitEthernet 0/1 overload
```

Verify:

```text
show ip nat translations
show ip nat statistics
```

## Packet Tracer Lab

Build:

```text
Enterprise LAN → Edge Router → ISP
```

Configure PAT.

Then configure Static NAT for a Web Server.

## Homework

Compare:

**Static NAT / Dynamic NAT / PAT**

## Quiz

15 questions.

## Module Exam

Internet Edge Configuration.

---

# MODULE 12 — ADVANCED ACL

## Learning Objectives

Students can:

- Design security policies
- Configure Standard ACL
- Configure Extended ACL
- Understand ACL order
- Understand wildcard masks
- Troubleshoot access control

## Keywords

`ACL`  
`Standard ACL`  
`Extended ACL`  
`Wildcard Mask`  
`Implicit Deny`  
`Ingress`  
`Egress`

## Example

Block Telnet:

```text
access-list 110 deny tcp 10.10.20.0 0.0.0.255 any eq 23
access-list 110 permit ip any any
```

Apply:

```text
interface gigabitEthernet 0/1
ip access-group 110 in
```

Verify:

```text
show access-lists
```

## Packet Tracer Lab

Security requirements:

```text
ADMIN → Everything Allowed
IT → Server Allowed
STUDENT → Internet Only
GUEST → Internet Only
GUEST → Internal Denied
```

Students design ACL policy.

## Homework

Create 10 ACL policies from business requirements.

## Quiz

20 scenario questions.

## Module Exam

Advanced ACL design and troubleshooting.

---

# MODULE 13 — ADVANCED DEVICE SECURITY

## Learning Objectives

Students can:

- Configure SSH
- Configure Local Authentication
- Secure VTY
- Configure privileged access
- Apply basic management-plane security

## Cisco Commands

```text
hostname SW1
ip domain-name company.local
username admin privilege 15 secret StrongPassword
crypto key generate rsa
```

VTY:

```text
line vty 0 4
login local
transport input ssh
```

Verify:

```text
show ip ssh
show users
```

## Additional Security Concepts

`SSH`  
`Local Authentication`  
`Management VLAN`  
`Password Policy`  
`Device Hardening`

## Packet Tracer Lab

Secure all routers and switches.

Students must disable insecure remote management and test SSH.

## Homework

Create a Cisco device security checklist.

## Quiz

15 questions.

## Module Exam

Secure an enterprise network infrastructure.

---

# MODULE 14 — NETWORK REDUNDANCY & HIGH AVAILABILITY

## Learning Objectives

Students can:

- Understand network redundancy
- Understand single point of failure
- Use redundant links
- Use STP to prevent loops
- Understand first-hop redundancy concepts
- Design resilient topology

## Keywords

`Redundancy`  
`High Availability`  
`Single Point of Failure`  
`Failover`  
`FHRP`  
`Default Gateway Redundancy`

## Lecture Notes

Bad design:

```text
PC → SW → Router → Internet
```

If Router fails, entire network loses connectivity.

Better:

```text
           R1
          /  \
        SW1--SW2
          \  /
           R2
```

## Packet Tracer Lab

Design a redundant enterprise network.

Introduce failures:

- Router failure
- Switch failure
- Link failure

Observe recovery.

## Homework

Identify 10 possible Single Points of Failure in a network.

## Quiz

15 questions.

## Module Exam

High-Availability network design.

---

# MODULE 15 — ADVANCED TROUBLESHOOTING

## Learning Objectives

Students can:

- Troubleshoot complex multi-layer problems
- Analyze topology
- Read multiple show commands
- Identify root cause
- Avoid random configuration changes
- Document troubleshooting

## Troubleshooting Framework

```text
1. Identify
2. Gather Evidence
3. Create Theory
4. Test
5. Fix
6. Verify
7. Document
```

## Command Set

```text
show running-config
show interfaces
show interfaces status
show vlan brief
show interfaces trunk
show spanning-tree
show etherchannel summary
show ip interface brief
show ip route
show ip ospf neighbor
show ipv6 route
show access-lists
show ip nat translations
show ip dhcp binding
ping
traceroute
```

## Packet Tracer Lab

Instructor creates a network with **25 hidden faults**.

Example:

```text
Layer 1 → Cable / Interface
Layer 2 → VLAN / Trunk / STP / EtherChannel
Layer 3 → IP / Route / OSPF
Services → DHCP / DNS / NAT
Security → ACL / SSH
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

Write a professional Network Troubleshooting Report.

## Quiz

25 scenario questions.

## Practical Exam

**Advanced Network Fault Isolation**

---

# MODULE 16 — CAPSTONE ENTERPRISE NETWORK

# FINAL PROJECT

## Scenario

A company has:

```text
Administration
Human Resources
Finance
IT
Student/Guest
Server Room
Internet Edge
```

Students must design the entire network.

## Required Technologies

```text
IPv4
VLSM
VLAN
Trunk
RSTP
EtherChannel
Layer 3 Switching
OSPF
IPv6
DHCP
DNS
NAT/PAT
ACL
SSH
Redundancy
Troubleshooting
```

---

# FINAL TOPOLOGY

```text
                           ISP
                            |
                         EDGE-R1
                            |
                  +---------+---------+
                  |                   |
                CORE1               CORE2
                  |\                 /|
                  | \               / |
                  |  \             /  |
                 SW1  SW2=========SW3 SW4
                /  \   |           |  / \
              V10 V20 V30         V40 V50
                       |
                    SERVER
```

Students may modify the design based on requirements.

---

# FINAL PROJECT REQUIREMENTS

## VLAN Design

```text
VLAN 10 = ADMIN
VLAN 20 = HR
VLAN 30 = FINANCE
VLAN 40 = IT
VLAN 50 = GUEST
VLAN 99 = MANAGEMENT
```

## Routing

Use:

```text
OSPF
Area 0
Additional Area where appropriate
```

## Switching

Must include:

```text
RSTP
EtherChannel
Trunk
Access Ports
SVI
```

## Services

```text
DHCP
DNS
HTTP
NAT/PAT
```

## Security

```text
SSH
ACL
Management VLAN
PortFast
BPDU Guard
```

## Addressing

Provide complete:

```text
IPv4 VLSM Table
IPv6 Addressing Table
```

---

# FINAL PROJECT DOCUMENTATION

Students must submit:

## 1. Network Diagram

## 2. IP Addressing Table

## 3. VLAN Table

## 4. Routing Table

## 5. Security Policy

## 6. Cisco Configurations

## 7. Testing Results

## 8. Troubleshooting Report

---

# FINAL EXAM

## PART A — THEORY

**100 Questions**

| Topic | Questions |
|---|---:|
| Network Design | 10 |
| IPv4/VLSM | 15 |
| VLAN | 10 |
| STP/RSTP | 10 |
| EtherChannel | 10 |
| Layer 3 Switching | 10 |
| OSPF | 15 |
| IPv6 | 5 |
| DHCP/DNS | 5 |
| NAT/PAT | 5 |
| ACL/Security | 5 |
| **Total** | **100** |

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

# PART C — CISCO IOS PRACTICAL

Students configure:

```text
Hostname
Secure Access
VLAN
Trunk
EtherChannel
STP
SVI
OSPF
IPv6
DHCP
NAT/PAT
ACL
SSH
```

---

# PART D — TROUBLESHOOTING

Student receives a broken enterprise network.

They must:

```text
Find
↓
Analyze
↓
Fix
↓
Verify
↓
Explain
```

---

# PART E — DESIGN PRESENTATION

Each student/team presents:

### Network Architecture

Why was this topology selected?

### IP Addressing

Why were these subnet sizes selected?

### VLAN Design

Why was each VLAN created?

### Routing

Why was OSPF selected?

### Redundancy

What happens when a link/device fails?

### Security

How are users and devices protected?

### Troubleshooting

How was the fault located?

---

# 4. ASSESSMENT

| Assessment | Weight |
|---|---:|
| Homework | 5% |
| Weekly Quiz | 10% |
| Packet Tracer Labs | 20% |
| Module Exams | 20% |
| Midterm | 10% |
| Capstone Project | 20% |
| Final Exam | 15% |
| **TOTAL** | **100%** |

---

# 5. ADVANCED COMMAND CHECKLIST

## Switching

```text
show vlan brief
show interfaces trunk
show spanning-tree
show etherchannel summary
```

## Layer 3

```text
ip routing
interface vlan
no switchport
show ip route
```

## OSPF

```text
router ospf
router-id
network
passive-interface
ip ospf cost
show ip ospf neighbor
show ip ospf interface
show ip route ospf
```

## IPv6

```text
ipv6 unicast-routing
ipv6 address
show ipv6 interface brief
show ipv6 neighbors
show ipv6 route
```

## DHCP

```text
ip dhcp pool
ip dhcp excluded-address
ip helper-address
show ip dhcp binding
```

## NAT/PAT

```text
ip nat inside
ip nat outside
ip nat inside source
show ip nat translations
show ip nat statistics
```

## ACL

```text
access-list
ip access-group
show access-lists
```

## Security

```text
username
ip domain-name
crypto key generate rsa
login local
transport input ssh
show ip ssh
```

## Troubleshooting

```text
show running-config
show interfaces
show ip interface brief
show ip route
ping
traceroute
```

---

# 6. ADVANCED SKILL MATRIX

| Skill | Beginner | Intermediate | Advanced |
|---|---|---|---|
| IPv4 | Configure | Subnet | VLSM/Design |
| VLAN | Basic | Multi-VLAN | Enterprise Design |
| STP | Understand | Configure | Optimize/Troubleshoot |
| EtherChannel | — | Configure | Design/Troubleshoot |
| Routing | Static | OSPF Basic | Advanced OSPF |
| IPv6 | Basic | Configure | Enterprise IPv6 |
| DHCP | Basic | Relay | Centralized Services |
| NAT | Basic | PAT | Internet Edge |
| ACL | Basic | Extended | Security Policy |
| Security | Password | SSH | Device Hardening |
| Troubleshooting | Basic | Structured | Advanced Fault Isolation |
| Design | Simple LAN | Small Enterprise | Enterprise Architecture |

---

# 7. GRADUATION STANDARD

ដើម្បីឱ្យសិស្ស “Pass CCNA Advanced” គួរតែអាចធ្វើបានដោយខ្លួនឯង៖

```text
[✓] Design Network
[✓] Create VLSM Plan
[✓] Configure VLAN
[✓] Configure Trunk
[✓] Configure STP
[✓] Configure EtherChannel
[✓] Configure Layer 3 Switching
[✓] Configure OSPF
[✓] Configure IPv6
[✓] Configure DHCP
[✓] Configure NAT/PAT
[✓] Configure ACL
[✓] Configure SSH
[✓] Implement Redundancy
[✓] Troubleshoot Complex Problems
[✓] Document Network
[✓] Explain Design Decisions
```

---

# 8. FINAL LEARNING PATH

```text
CCNA BEGINNER
      ↓
Networking Fundamentals
      ↓
Cisco IOS
      ↓
IPv4
      ↓
Basic Switching/Routing
      ↓
           
CCNA INTERMEDIATE
      ↓
VLAN
STP
EtherChannel
Layer 3 Switching
OSPF
IPv6
DHCP
NAT
ACL
SSH
      ↓

CCNA ADVANCED
      ↓
Enterprise Design
Advanced VLSM
Advanced STP
Advanced EtherChannel
Advanced OSPF
IPv6 Routing
Network Services
Advanced ACL
Security
Redundancy
Advanced Troubleshooting
      ↓

ENTERPRISE CAPSTONE
      ↓
DESIGN → CONFIGURE → VERIFY → TROUBLESHOOT → PRESENT
```

# 9. COURSE COMPLETION TARGET

នៅពេលបញ្ចប់ Advanced Course សិស្សគួរតែអាចទទួលបាន Network Scenario មួយដែលមានតែ៖

```text
Business Requirements
IP Requirements
Security Requirements
Availability Requirements
```

ហើយបង្កើតចេញជា៖

```text
Network Diagram
+
IP Plan
+
VLAN Plan
+
Routing Design
+
Security Design
+
Cisco Configuration
+
Testing
+
Troubleshooting Report
```

នេះជាចំណុចដែលសិស្សផ្លាស់ពី **“Cisco Student”** ទៅ **“Junior Network Engineer”**។