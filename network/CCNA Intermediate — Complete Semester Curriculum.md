# CCNA INTERMEDIATE
## Complete Semester Curriculum with Lessons, Notes, Commands, Packet Tracer Labs, Homework, Quizzes & Module Exams

**Level:** Intermediate  
**Duration:** 16 Weeks  
**Class Time:** 4 Hours / Week  
**Total:** 64 Hours  
**Prerequisite:** Basic Cisco Networking / CCNA Beginner  
**Main Lab Platform:** Cisco Packet Tracer  
**Teaching Language:** Khmer + English Technical Keywords  
**Assessment:** Theory + Configuration + Troubleshooting

---

# PART 1 — COURSE OVERVIEW

## 1. Course Purpose

Course នេះបន្តពី **CCNA Beginner** ទៅកាន់កម្រិត Intermediate ដោយផ្តោតលើការប្រើ Cisco Network Devices ដើម្បីបង្កើត Network ដែលមានច្រើន VLAN, Redundancy, Dynamic Routing, Network Security និង Network Services។

សិស្សត្រូវផ្លាស់ពី៖

```text
Memorize Commands
        ↓
Understand Commands
        ↓
Configure
        ↓
Verify
        ↓
Troubleshoot
        ↓
Design
```

---

# 2. Course Learning Outcomes

នៅចុង Semester សិស្សអាច៖

1. Perform advanced **IPv4 Subnetting / VLSM**.
2. Design a logical **VLAN** structure.
3. Configure **Access Ports** និង **Trunk Ports**.
4. Explain and configure **STP / RSTP**.
5. Configure **EtherChannel** using LACP.
6. Configure **Inter-VLAN Routing**.
7. Configure **Layer 3 Switching**.
8. Configure **OSPF** ក្នុង network ច្រើន Router។
9. Configure basic **IPv6** connectivity.
10. Configure **DHCP / DHCP Relay**.
11. Configure basic **NAT/PAT**.
12. Configure **Standard and Extended ACLs**.
13. Configure secure remote management using **SSH**.
14. Troubleshoot Layer 1, Layer 2 និង Layer 3 problems.
15. Design and configure a small enterprise network.

---

# 3. Semester Schedule

| Week | Module | Topic | Lab |
|---|---|---|---|
| 1 | M1 | Advanced IPv4 & VLSM | IP Planning |
| 2 | M2 | VLAN & Inter-VLAN Routing | VLAN Network |
| 3 | M3 | STP Fundamentals | Layer 2 Redundancy |
| 4 | M4 | RSTP & Port Security | STP Security |
| 5 | M5 | EtherChannel | LACP |
| 6 | M6 | Layer 3 Switching | Multilayer Switch |
| 7 | M7 | OSPF Fundamentals | 3-Router OSPF |
| 8 | M8 | OSPF Troubleshooting | Broken OSPF |
| 9 | M9 | IPv6 | IPv6 Network |
| 10 | M10 | DHCP & DHCP Relay | Central DHCP |
| 11 | M11 | NAT & PAT | Internet Simulation |
| 12 | M12 | ACL | Traffic Filtering |
| 13 | M13 | SSH & Device Security | Secure Management |
| 14 | M14 | Troubleshooting Methodology | Fault Lab |
| 15 | M15 | Integrated Enterprise Network | Full Project |
| 16 | M16 | Final Review & Final Exam | Practical + Written |

---

# MODULE 1 — ADVANCED IPv4 & VLSM

## Learning Objectives

សិស្សអាច៖

- Review **IPv4 Addressing**
- Calculate **Subnet Mask**
- Calculate **Network Address**
- Calculate **Broadcast Address**
- Calculate **Usable Host Range**
- Use **VLSM**
- Create an IP Addressing Plan
- Understand **CIDR**

## Lecture Notes

### IPv4 Structure

Example:

```text
192.168.10.25/24
```

- Network portion → `192.168.10`
- Host portion → `25`

### Host Formula

```text
Usable Hosts = 2^h - 2
```

Examples:

```text
/25 = 126 Hosts
/26 = 62 Hosts
/27 = 30 Hosts
/28 = 14 Hosts
/29 = 6 Hosts
/30 = 2 Hosts
```

### VLSM Concept

បើមាន Requirement:

```text
Department A = 100 Hosts
Department B = 50 Hosts
Department C = 25 Hosts
Department D = 10 Hosts
```

ត្រូវចាប់ផ្តើមពី Network ដែលត្រូវការ Host ច្រើនជាងគេ។

## Cisco Commands

```text
show ip interface brief
show ip route
```

## Packet Tracer Lab

Build:

```text
                R1
          ______|______
         /      |      \
       LAN1    LAN2    LAN3
```

Requirements:

```text
LAN1 = 100 Hosts
LAN2 = 50 Hosts
LAN3 = 20 Hosts
LAN4 = 10 Hosts
```

Students create:

- Network Address
- Prefix
- First Host
- Last Host
- Broadcast

## Homework

20 VLSM questions.

## Quiz

15 questions:

- Binary
- Prefix
- Host calculation
- Network calculation
- Broadcast

## Module Exam

### Theory — 30%

### Subnetting — 40%

### Practical IP Design — 30%

---

# MODULE 2 — VLAN & INTER-VLAN ROUTING

## Learning Objectives

Students can:

- Create VLANs
- Assign Access Ports
- Configure Trunks
- Understand VLAN segmentation
- Configure Router-on-a-Stick
- Troubleshoot VLAN communication

## Lecture Notes

Example:

```text
VLAN 10 = ADMIN
VLAN 20 = HR
VLAN 30 = IT
VLAN 40 = GUEST
```

VLAN separates one physical network into multiple logical networks.

### Important Keywords

`VLAN`  
`Access Port`  
`Trunk Port`  
`802.1Q`  
`Native VLAN`  
`Subinterface`

## Cisco Commands

Create VLAN:

```text
vlan 10
name ADMIN
```

Assign Access Port:

```text
interface fastEthernet 0/1
switchport mode access
switchport access vlan 10
```

Configure Trunk:

```text
interface gigabitEthernet 0/1
switchport mode trunk
```

Router-on-a-Stick:

```text
interface gigabitEthernet 0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
```

## Verification

```text
show vlan brief
show interfaces trunk
show ip interface brief
```

## Packet Tracer Lab

```text
PC1 ----\
PC2 ----- SW1 ===== R1
PC3 ----/
```

Create:

```text
VLAN 10 = ADMIN
VLAN 20 = IT
VLAN 30 = SALES
```

Configure Inter-VLAN Routing.

## Homework

Explain why devices in different VLANs cannot communicate directly through a Layer 2 Switch.

## Quiz

15 questions.

## Module Practical Exam

Configure:

- 3 VLANs
- Access Ports
- Trunk
- Router-on-a-Stick
- Default Gateway

---

# MODULE 3 — STP FUNDAMENTALS

## Learning Objectives

Students can:

- Explain Layer 2 loop
- Explain **STP**
- Understand **BPDU**
- Identify **Root Bridge**
- Identify **Root Port**
- Identify **Designated Port**
- Understand Path Cost

## Lecture Notes

Without STP:

```text
       SW1
      /   \
    SW2---SW3
```

Looping may occur.

STP creates a loop-free logical topology.

### Important Keywords

`STP`  
`BPDU`  
`Root Bridge`  
`Root Port`  
`Designated Port`  
`Blocking`  
`Path Cost`

## Cisco Commands

```text
show spanning-tree
show spanning-tree vlan 10
```

Set Root:

```text
spanning-tree vlan 10 root primary
```

## Packet Tracer Lab

Create:

```text
        SW1
       /   \
     SW2---SW3
```

Observe:

- Root Bridge
- Forwarding Ports
- Alternate/Blocked Path

## Homework

Draw the STP tree manually.

## Quiz

15 questions.

## Module Exam

Students receive a 3-switch topology and identify STP roles.

---

# MODULE 4 — RSTP, PORTFAST & BPDU GUARD

## Learning Objectives

Students can:

- Compare STP vs RSTP
- Configure **Rapid PVST+**
- Configure **PortFast**
- Configure **BPDU Guard**
- Understand Edge Ports

## Lecture Notes

**RSTP** provides faster convergence than traditional STP.

PortFast should be used on ports connected to End Devices.

BPDU Guard helps protect an Edge Port if a BPDU is received unexpectedly.

## Cisco Commands

```text
spanning-tree mode rapid-pvst
```

PortFast:

```text
interface fastEthernet 0/10
spanning-tree portfast
```

BPDU Guard:

```text
spanning-tree bpduguard enable
```

## Verification

```text
show spanning-tree
```

## Packet Tracer Lab

Create:

```text
SW1 ---- SW2
 |
 +---- PC1
 +---- PC2
```

Configure:

- RSTP
- PortFast
- BPDU Guard

## Homework

Explain why PortFast should normally not be configured on a switch-to-switch link.

## Quiz

10 questions.

## Module Practical Exam

Configure access-port protection.

---

# MODULE 5 — ETHERCHANNEL

## Learning Objectives

Students can:

- Explain **EtherChannel**
- Explain **LACP**
- Understand Logical Port-Channel
- Configure multiple physical links
- Configure Port-Channel as Trunk
- Verify EtherChannel

## Lecture Notes

EtherChannel combines multiple physical links into one logical link.

```text
SW1
 ||||
 ||||
SW2
```

Instead of STP treating every physical link independently, the bundle appears as one logical connection.

### Keywords

`EtherChannel`  
`LACP`  
`PAgP`  
`Port-Channel`

## Cisco Commands

LACP:

```text
interface range gigabitEthernet 0/1-2
channel-group 1 mode active
```

Configure logical interface:

```text
interface port-channel 1
switchport mode trunk
```

Verification:

```text
show etherchannel summary
```

## Packet Tracer Lab

Connect SW1 and SW2 using 2–4 links.

Configure:

```text
Port-Channel 1
LACP
Trunk
```

## Homework

Compare:

**STP vs EtherChannel**

## Quiz

15 questions.

## Module Practical Exam

Configure LACP EtherChannel and prove it works.

---

# MODULE 6 — LAYER 3 SWITCHING

## Learning Objectives

Students can:

- Understand Layer 2 vs Layer 3 Switching
- Configure **SVI**
- Configure `ip routing`
- Perform Inter-VLAN Routing using a Multilayer Switch
- Verify routing table

## Lecture Notes

A Layer 3 Switch can perform switching and routing.

### Key Terms

`SVI`  
`Layer 3 Switch`  
`Inter-VLAN Routing`  
`ip routing`

## Cisco Commands

Enable routing:

```text
ip routing
```

Create SVI:

```text
interface vlan 10
ip address 192.168.10.1 255.255.255.0
no shutdown
```

Verify:

```text
show ip interface brief
show ip route
```

## Packet Tracer Lab

```text
PCs
 |
Multilayer Switch
 |
Router
```

Create 3 VLANs.

Use SVI as Default Gateway.

## Homework

Compare:

```text
Router-on-a-Stick
vs
Layer 3 Switch
```

## Quiz

10 questions.

## Module Exam

Configure a Multilayer Switch for Inter-VLAN Routing.

---

# MODULE 7 — OSPF FUNDAMENTALS

## Learning Objectives

Students can:

- Explain Dynamic Routing
- Explain **OSPF**
- Understand Router ID
- Understand Neighbor Adjacency
- Advertise networks
- Read OSPF routes

## Lecture Notes

**OSPF = Open Shortest Path First**

OSPF is a dynamic **Link-State Routing Protocol**.

Important concepts:

```text
Neighbor
Adjacency
Router ID
Area
LSA
Cost
SPF
```

## Cisco Commands

```text
router ospf 1
router-id 1.1.1.1
network 192.168.1.0 0.0.0.255 area 0
network 10.0.0.0 0.0.0.3 area 0
```

Verify:

```text
show ip ospf neighbor
show ip route ospf
show ip protocols
```

## Packet Tracer Lab

```text
LAN1 -- R1 ---- R2 ---- R3 -- LAN3
```

Configure:

**OSPF Area 0**

Verify Neighbor relationships.

## Homework

Explain how a router learns a remote network through OSPF.

## Quiz

20 questions.

## Module Practical Exam

3-Router OSPF network.

---

# MODULE 8 — OSPF TROUBLESHOOTING

## Learning Objectives

Students can troubleshoot:

- Incorrect IP Address
- Incorrect Area
- Incorrect Network Statement
- Passive Interface
- Missing OSPF
- Wrong Router ID
- Neighbor Failure

## Cisco Commands

```text
show ip ospf neighbor
show ip ospf interface
show ip protocols
show ip route
```

## Packet Tracer Lab

Teacher prepares a broken topology containing:

```text
Fault 1 = Wrong IP
Fault 2 = Wrong Area
Fault 3 = Passive Interface
Fault 4 = Missing Network
Fault 5 = Incorrect Subnet
```

Students must document:

```text
Problem
Cause
Command Used
Solution
Verification
```

## Homework

10 OSPF troubleshooting scenarios.

## Quiz

15 scenario questions.

## Module Practical Exam

Repair a broken OSPF network.

---

# MODULE 9 — IPv6

## Learning Objectives

Students can:

- Explain IPv6
- Identify IPv6 address types
- Configure Global Unicast
- Configure Link-Local
- Understand SLAAC
- Verify IPv6 Neighbor information

## Keywords

`IPv6`  
`Global Unicast`  
`Link-Local`  
`SLAAC`  
`EUI-64`  
`Neighbor Discovery`

## Cisco Commands

```text
ipv6 unicast-routing
```

Interface:

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

```text
PC1 -- R1 ---- R2 -- PC2
```

Configure IPv6 connectivity.

## Homework

Write and classify 15 IPv6 addresses.

## Quiz

15 questions.

## Module Exam

IPv6 configuration + troubleshooting.

---

# MODULE 10 — DHCP & DHCP RELAY

## Learning Objectives

Students can:

- Explain DHCP
- Explain **DORA**
- Configure DHCP Server
- Configure DHCP Pool
- Exclude addresses
- Configure DHCP Relay

## Lecture Notes

DHCP process:

```text
Discover
Offer
Request
ACK
```

## Cisco Commands

```text
ip dhcp excluded-address 192.168.10.1 192.168.10.20
```

Pool:

```text
ip dhcp pool STUDENT
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 8.8.8.8
```

Relay:

```text
interface vlan 20
ip helper-address 192.168.100.10
```

Verify:

```text
show ip dhcp binding
show ip dhcp pool
```

## Packet Tracer Lab

Topology:

```text
VLAN 10 \
VLAN 20  --- Router --- DHCP Server
VLAN 30 /
```

Use one central DHCP Server.

## Homework

Explain each stage of DORA.

## Quiz

15 questions.

## Module Practical Exam

Configure DHCP for multiple VLANs.

---

# MODULE 11 — NAT & PAT

## Learning Objectives

Students can:

- Explain NAT
- Explain PAT
- Understand Inside Local
- Understand Inside Global
- Configure basic PAT
- Verify NAT translations

## Keywords

`NAT`  
`PAT`  
`Inside Local`  
`Inside Global`  
`Outside Local`  
`Outside Global`

## Cisco Commands

ACL:

```text
access-list 1 permit 192.168.1.0 0.0.0.255
```

Inside:

```text
interface gigabitEthernet 0/0
ip nat inside
```

Outside:

```text
interface gigabitEthernet 0/1
ip nat outside
```

PAT:

```text
ip nat inside source list 1 interface gigabitEthernet 0/1 overload
```

Verify:

```text
show ip nat translations
show ip nat statistics
```

## Packet Tracer Lab

```text
LAN ---- R1 -------- ISP
```

Configure PAT for internal users.

## Homework

Explain the difference between NAT and PAT.

## Quiz

15 questions.

## Module Exam

Configure PAT + Verify Translation Table.

---

# MODULE 12 — ACCESS CONTROL LIST

## Learning Objectives

Students can:

- Explain ACL
- Understand Standard ACL
- Understand Extended ACL
- Understand Permit / Deny
- Understand Implicit Deny
- Apply ACL correctly
- Troubleshoot ACL

## Keywords

`ACL`  
`Standard ACL`  
`Extended ACL`  
`Permit`  
`Deny`  
`Implicit Deny`

## Standard ACL

```text
access-list 10 deny 192.168.10.0 0.0.0.255
access-list 10 permit any
```

Apply:

```text
interface gigabitEthernet 0/0
ip access-group 10 in
```

## Extended ACL

Example:

```text
access-list 100 deny tcp 192.168.10.0 0.0.0.255 any eq 23
access-list 100 permit ip any any
```

Verify:

```text
show access-lists
```

## Packet Tracer Lab

Requirement:

```text
VLAN 10 → Server = Allowed
VLAN 20 → Server = Denied
VLAN 30 → HTTP = Allowed
VLAN 30 → Telnet = Denied
```

Students design ACL rules.

## Homework

Create ACLs for 10 scenarios.

## Quiz

20 questions.

## Module Practical Exam

Traffic filtering based on business requirements.

---

# MODULE 13 — SSH & DEVICE SECURITY

## Learning Objectives

Students can:

- Secure Cisco Router/Switch
- Create Local User
- Configure SSH
- Restrict VTY Access
- Understand Secure Remote Management

## Cisco Commands

```text
hostname R1
ip domain-name school.local
username admin privilege 15 secret cisco123
```

Generate RSA key:

```text
crypto key generate rsa
```

Configure VTY:

```text
line vty 0 4
login local
transport input ssh
```

Verify:

```text
show ip ssh
show running-config
```

## Packet Tracer Lab

Students configure:

- Local username
- SSH
- VTY
- Password security
- MOTD Banner

Then connect from PC using SSH.

## Homework

Why is **SSH** preferred over **Telnet**?

## Quiz

15 questions.

## Module Exam

Secure Router + Switch management.

---

# MODULE 14 — NETWORK TROUBLESHOOTING

## Learning Objectives

Students can:

- Follow structured troubleshooting
- Identify Layer 1 problems
- Identify Layer 2 problems
- Identify Layer 3 problems
- Troubleshoot Routing
- Troubleshoot VLAN
- Troubleshoot ACL
- Verify the final solution

## Troubleshooting Process

```text
1. Identify the Problem
2. Establish a Theory
3. Test the Theory
4. Implement Solution
5. Verify
6. Document
```

## Cisco Verification Commands

```text
show running-config
show startup-config
show ip interface brief
show interfaces
show vlan brief
show interfaces trunk
show etherchannel summary
show spanning-tree
show ip route
show ip ospf neighbor
show access-lists
show ip nat translations
show ip dhcp binding
ping
traceroute
```

## Packet Tracer Lab

Teacher creates **20 hidden faults**:

```text
Wrong Cable
Wrong VLAN
Wrong IP
Wrong Subnet Mask
Shutdown Interface
Wrong Trunk
EtherChannel Failure
STP Problem
Missing Route
OSPF Problem
DHCP Problem
ACL Problem
NAT Problem
SSH Problem
```

Students must submit:

```text
Problem
Evidence
Root Cause
Fix
Verification
```

## Homework

Troubleshooting Report.

## Quiz

20 scenario-based questions.

## Module Practical Exam

Students repair a broken enterprise topology within a fixed time.

---

# MODULE 15 — INTEGRATED ENTERPRISE NETWORK

## Final Project Objective

Students build a complete small enterprise network.

## Company Departments

```text
ADMIN
HR
FINANCE
IT
GUEST
```

## Network Requirements

### VLAN

```text
VLAN 10 = ADMIN
VLAN 20 = HR
VLAN 30 = FINANCE
VLAN 40 = IT
VLAN 50 = GUEST
```

### Switching

Students must use:

```text
Access Ports
Trunk Ports
EtherChannel
RSTP
PortFast
BPDU Guard
```

### Routing

Use:

```text
Inter-VLAN Routing
OSPF Area 0
```

### Services

Use:

```text
DHCP
DNS
NAT/PAT
```

### Security

Use:

```text
ACL
SSH
Enable Secret
Local User
PortFast
BPDU Guard
```

### Addressing

Students must design:

**IPv4 VLSM Addressing Plan**

---

# FINAL PROJECT TOPOLOGY

```text
                          ISP
                           |
                          R1
                           |
                      +----+----+
                      |         |
                    SW-CORE   Server
                   /    \
                 SW1    SW2
                /  \    /  \
              PC  PC  PC   PC
             V10 V20 V30  V40
                    |
                   V50
```

Students may expand the topology according to their design.

---

# FINAL PROJECT REQUIREMENTS

Students must demonstrate:

## 1. IP Addressing

Provide:

```text
Network Address
Subnet Mask
Default Gateway
Broadcast Address
Usable Host Range
```

## 2. VLAN

Five VLANs.

## 3. Trunking

At least two trunk links.

## 4. EtherChannel

At least one LACP Port-Channel.

## 5. STP

Configure root bridge intentionally.

## 6. Inter-VLAN Routing

All required VLANs can communicate according to security policy.

## 7. OSPF

At least two routers participate in OSPF.

## 8. DHCP

Users obtain IP automatically.

## 9. NAT/PAT

Internal hosts can reach the simulated ISP network.

## 10. ACL

Guest users must have restricted access.

## 11. SSH

Administrator can securely manage the Cisco devices.

## 12. Troubleshooting

Students must explain how they verified each technology.

---

# MODULE 16 — FINAL EXAM

# PART A — Written Examination

**100 Questions**

| Topic | Questions |
|---|---:|
| IPv4 / VLSM | 15 |
| VLAN | 10 |
| STP / RSTP | 10 |
| EtherChannel | 10 |
| Layer 3 Switching | 10 |
| OSPF | 15 |
| IPv6 | 10 |
| DHCP | 5 |
| NAT/PAT | 5 |
| ACL | 5 |
| Security | 5 |
| **Total** | **100** |

---

# PART B — Cisco IOS Exam

Students receive an unconfigured device and must perform:

```text
Hostname
Password Security
VLAN
Access Port
Trunk
EtherChannel
STP
SVI
OSPF
DHCP
NAT
ACL
SSH
```

---

# PART C — Subnetting Exam

Students must solve:

- IPv4 Address
- Prefix
- Network
- Broadcast
- First Host
- Last Host
- Number of Hosts
- VLSM Design

---

# PART D — Troubleshooting Exam

Instructor gives a broken network.

Students must:

```text
Identify
↓
Analyze
↓
Test
↓
Fix
↓
Verify
↓
Document
```

---

# PART E — Final Presentation

Each student/team presents:

### Network Design

Why did you choose this topology?

### VLAN Design

Why are departments separated?

### IP Addressing

Why did you choose these subnet sizes?

### Routing

Why did you use OSPF?

### Security

How did your ACL protect the network?

### Troubleshooting

What problem occurred and how was it solved?

---

# 4. ASSESSMENT SYSTEM

| Component | Weight |
|---|---:|
| Attendance / Participation | 5% |
| Homework | 5% |
| Weekly Quizzes | 10% |
| Packet Tracer Labs | 20% |
| Module Exams | 20% |
| Midterm Exam | 10% |
| Final Project | 15% |
| Final Exam | 15% |
| **TOTAL** | **100%** |

---

# 5. WEEKLY CLASS STRUCTURE

## 4 Hours / Week

### Hour 1 — Theory

```text
Concept
↓
Diagram
↓
Real-world Example
↓
Keywords
```

### Hour 2 — Cisco Demonstration

Teacher demonstrates:

```text
Command
↓
Output
↓
Meaning
```

### Hour 3 — Packet Tracer Lab

Students configure independently.

### Hour 4 — Troubleshooting + Quiz

Students:

```text
Verify
Troubleshoot
Explain
Quiz
```

---

# 6. TEACHER'S METHOD FOR EVERY TOPIC

Use the same learning sequence:

## WHAT?

What is the technology?

## WHY?

Why do we need it?

## HOW?

How does it work?

## CONFIGURE

What commands are used?

## VERIFY

How do we know it works?

## TROUBLESHOOT

What can go wrong?

## EXPLAIN

Can the student explain it without memorizing?

---

# 7. ESSENTIAL CCNA INTERMEDIATE COMMAND CHEAT SHEET

## Basic

```text
enable
configure terminal
exit
end
do show
```

## Interface

```text
interface
interface range
ip address
no shutdown
shutdown
description
```

## VLAN

```text
vlan
name
switchport mode access
switchport access vlan
switchport mode trunk
show vlan brief
show interfaces trunk
```

## STP

```text
spanning-tree mode rapid-pvst
spanning-tree vlan root primary
show spanning-tree
spanning-tree portfast
spanning-tree bpduguard enable
```

## EtherChannel

```text
channel-group
interface port-channel
show etherchannel summary
```

## Layer 3 Switching

```text
ip routing
interface vlan
```

## OSPF

```text
router ospf
router-id
network
passive-interface
show ip ospf neighbor
show ip ospf interface
show ip route ospf
show ip protocols
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
show ip dhcp pool
```

## NAT

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

## SSH

```text
username
ip domain-name
crypto key generate rsa
login local
transport input ssh
show ip ssh
```

## Testing

```text
ping
traceroute
```

---

# 8. MODULE EXAM TEMPLATE

Every module should use the following format.

## Section A — Theory

20%

## Section B — Command Knowledge

20%

## Section C — Configuration

30%

## Section D — Troubleshooting

20%

## Section E — Explanation

10%

This ensures that students are assessed on:

**Knowledge + Skill + Troubleshooting**

---

# 9. FINAL STUDENT COMPETENCY CHECKLIST

At the end of the semester, students should be able to perform these tasks without step-by-step instructions:

```text
[ ] IPv4 Subnetting
[ ] VLSM
[ ] VLAN
[ ] Access Port
[ ] Trunk
[ ] STP
[ ] RSTP
[ ] PortFast
[ ] BPDU Guard
[ ] EtherChannel
[ ] LACP
[ ] SVI
[ ] Layer 3 Switching
[ ] OSPF
[ ] IPv6
[ ] DHCP
[ ] DHCP Relay
[ ] NAT
[ ] PAT
[ ] ACL
[ ] SSH
[ ] Network Troubleshooting
```

---

# 10. END-OF-SEMESTER EXPECTATION

Students should move from:

```text
Beginner
   ↓
Can follow configuration instructions
   ↓
Intermediate
   ↓
Can understand the topology
   ↓
Can design the configuration
   ↓
Can configure independently
   ↓
Can verify
   ↓
Can troubleshoot
   ↓
Can explain WHY
```

The final goal is not simply:

> “Student can type Cisco commands.”

The real goal is:

> **Student can understand, design, configure, verify, troubleshoot, and explain a Cisco-based network.**