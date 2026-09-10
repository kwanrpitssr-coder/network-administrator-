# Cisco Networking Fundamentals
## CCNA Beginner-Level Semester Curriculum

**Duration:** 16 Weeks  
**Suggested Hours:** 4 hours/week  
**Total:** 64 hours  
**Target Learners:** Beginners / Students with little or no networking background  
**Main Tool:** Cisco Packet Tracer  
**Primary Cisco Devices:** Switch, Router, End Devices  
**Teaching Language:** Khmer explanation + English networking keywords and Cisco commands

---

# 1. Course Description

Course នេះមានគោលបំណងឱ្យសិស្សចាប់ផ្តើមពី **Networking Fundamentals** រហូតដល់អាចបង្កើត និង Troubleshoot បណ្តាញតូចមួយបានដោយប្រើ **Cisco Packet Tracer**។

សិស្សនឹងរៀនទាំង **Theory**, **Cisco IOS CLI**, **Configuration**, **Verification**, **Troubleshooting**, និង **Hands-on Labs**។

Course នេះផ្តោតលើសមត្ថភាព ៤ សំខាន់ៗ៖

**Understand → Configure → Verify → Troubleshoot**

---

# 2. Overall Course Learning Outcomes

នៅចុង Semester សិស្សអាច៖

1. ពន្យល់ **Network Fundamentals** និងតួនាទី Network Devices។
2. ស្គាល់ និងប្រើ **Cisco IOS CLI**។
3. Configure Basic **Switch** និង **Router**។
4. គណនា និង Configure **IPv4 Addressing / Subnetting**។
5. អនុវត្ត **VLAN, Access Port, Trunk Port**។
6. Configure មូលដ្ឋាន **Inter-VLAN Routing**។
7. Configure **Static Routing**។
8. Configure មូលដ្ឋាន **DHCP**។
9. ប្រើ **Show Commands** ដើម្បី Verify Configuration។
10. Troubleshoot common network problems។
11. បង្កើត Network Topology តូចមួយដោយខ្លួនឯងក្នុង **Cisco Packet Tracer**។
12. មានមូលដ្ឋានរឹងមាំសម្រាប់បន្តសិក្សា **CCNA**។

---

# 3. Semester Schedule

| Week | Module | Main Topic | Practical Focus |
|---|---|---|---|
| 1 | Module 1 | Networking Fundamentals | Build first LAN |
| 2 | Module 2 | Network Devices & Cabling | Device identification |
| 3 | Module 3 | Cisco IOS & CLI | Basic IOS commands |
| 4 | Module 4 | Basic Switch Configuration | Configure Switch |
| 5 | Module 5 | Ethernet & MAC Address | MAC learning |
| 6 | Module 6 | IPv4 Addressing | Configure IP |
| 7 | Module 7 | Subnetting | Subnet calculations |
| 8 | Module 8 | Router Configuration | Configure Router |
| 9 | Module 9 | Static Routing | Connect networks |
| 10 | Module 10 | VLAN | VLAN configuration |
| 11 | Module 11 | Trunking | Access/Trunk |
| 12 | Module 12 | Inter-VLAN Routing | Router-on-a-Stick |
| 13 | Module 13 | DHCP & Network Services | DHCP lab |
| 14 | Module 14 | IPv6 Fundamentals | IPv6 configuration |
| 15 | Module 15 | Security & Troubleshooting | SSH + troubleshooting |
| 16 | Module 16 | Final Project & Final Exam | Complete network |

---

# MODULE 1 — Networking Fundamentals

## Topic
**Introduction to Computer Networking**

## Learning Objectives

សិស្សអាច៖

- ពន្យល់ពាក្យ **Network**
- បែងចែក **LAN, WAN, WLAN**
- ពន្យល់ **Client, Server**
- ស្គាល់ **Bandwidth, Latency**
- ពន្យល់ Basic **Protocol**
- ស្គាល់ **OSI Model** និង **TCP/IP Model**

## Lecture Notes

**Network** គឺជាការភ្ជាប់ Devices ជាច្រើនដើម្បីចែករំលែក Data និង Resources។

### Basic Network Types

**LAN (Local Area Network)**  
Network នៅក្នុងតំបន់តូច ដូចជា Office, School, Lab។

**WAN (Wide Area Network)**  
Network ដែលភ្ជាប់តំបន់ធំៗ។

**WLAN (Wireless LAN)**  
LAN ដែលប្រើ Wireless Connection។

### Important Keywords

`Network`  
`LAN`  
`WAN`  
`WLAN`  
`Client`  
`Server`  
`Protocol`  
`Bandwidth`  
`Latency`  
`Packet`

## Packet Tracer Lab 1

Topology:

```text
PC1 -------- Switch -------- PC2
```

Task:

1. Add 2 PCs.
2. Add 1 Switch.
3. Connect using Copper Straight-Through.
4. Assign IPv4:
   - PC1: `192.168.1.10/24`
   - PC2: `192.168.1.20/24`
5. Ping PC2 from PC1.

## Homework

សរសេរ៖

1. What is a Network?
2. Difference between LAN and WAN.
3. What is a Protocol?
4. What is a Packet?
5. Give 5 examples of Network Devices.

## Quiz

1. LAN មានន័យថាអ្វី?
2. តើ Device ណាធ្វើការភ្ជាប់ Devices នៅក្នុង LAN?
3. What is a Protocol?
4. WAN ប្រើសម្រាប់អ្វី?
5. What is a Packet?

## Module Assessment

**Practical:** Build a simple LAN and successfully ping between two PCs.

---

# MODULE 2 — Cisco Network Devices & Connections

## Learning Objectives

សិស្សអាច៖

- ស្គាល់ **Router**
- ស្គាល់ **Switch**
- ស្គាល់ **Access Point**
- ស្គាល់ **Firewall**
- ស្គាល់ **Ethernet Interface**
- ស្គាល់ **Console Port**
- ជ្រើសរើស Cable ត្រឹមត្រូវ

## Lecture Notes

### Switch

ប្រើសម្រាប់ភ្ជាប់ End Devices នៅក្នុង LAN។

### Router

ប្រើសម្រាប់ភ្ជាប់ **Different Networks**។

### Access Point

ប្រើសម្រាប់ Wireless Connectivity។

### Common Cables

`Copper Straight-Through`  
`Copper Cross-Over`  
`Fiber`  
`Console Cable`

## Packet Tracer Lab

Build:

```text
PC1 ---- SW1 ---- Router1
PC2 ----/
```

Task:

- Identify each device.
- Identify interfaces.
- Select suitable cable.
- Check link status.

## Homework

បង្កើតតារាង៖

| Device | Function |
|---|---|
| Switch | ? |
| Router | ? |
| Access Point | ? |
| Firewall | ? |

## Quiz

10 questions based on:

- Router vs Switch
- Interfaces
- Cable types
- End Device vs Network Device

## Module Assessment

**Practical Device Identification Test**

---

# MODULE 3 — Cisco IOS & CLI Fundamentals

## Learning Objectives

សិស្សអាច៖

- ចូល **Cisco CLI**
- ស្គាល់ IOS Modes
- ប្រើ `?`
- ប្រើ `show`
- ប្រើ `configure terminal`
- ចាកចេញពី Configuration Modes

## Lecture Notes

### Cisco IOS Modes

```text
User EXEC Mode
Privileged EXEC Mode
Global Configuration Mode
Interface Configuration Mode
```

### Basic Commands

```text
enable
disable
configure terminal
exit
end
?
show
```

### Example

```text
Switch> enable
Switch# configure terminal
Switch(config)#
```

## Packet Tracer Lab

Task:

1. Connect PC to Switch Console.
2. Open Terminal.
3. Enter CLI.
4. Change hostname.

```text
Switch> enable
Switch# configure terminal
Switch(config)# hostname SW1
SW1(config)#
```

## Homework

សិស្សត្រូវសរសេរ៖

- IOS Modes ចំនួន 4
- Function របស់ Mode នីមួយៗ
- 10 Cisco commands និងមុខងារ

## Quiz

10 questions about:

- Prompt symbols
- CLI Modes
- `enable`
- `configure terminal`
- `exit`
- `end`
- `show`

## Module Exam

**Practical CLI Test**

សិស្សត្រូវចូល CLI និង Configure hostname ដោយមិនមើលឯកសារ។

---

# MODULE 4 — Basic Switch Configuration

## Learning Objectives

សិស្សអាច Configure៖

- `hostname`
- `enable secret`
- `console`
- `VTY`
- `banner motd`
- Password encryption
- Save configuration

## Cisco Commands

```text
enable
configure terminal
hostname SW1
enable secret cisco
line console 0
password cisco
login
line vty 0 4
password cisco
login
service password-encryption
banner motd #Authorized Access Only#
end
copy running-config startup-config
```

## Lecture Notes

**running-config** = configuration currently active.

**startup-config** = configuration stored for next boot.

## Packet Tracer Lab

Configure:

```text
Hostname: SW1
Enable Secret: class123
Console Password: cisco
VTY Password: cisco
MOTD Banner
```

Verify:

```text
show running-config
```

## Homework

សរសេរមូលហេតុដែលត្រូវ Save Configuration។

## Quiz

10 questions + command matching.

## Module Practical Exam

Configure a Switch from blank configuration.

---

# MODULE 5 — Ethernet, MAC Address & Switching

## Learning Objectives

សិស្សអាច៖

- ពន្យល់ **Ethernet Frame**
- ពន្យល់ **MAC Address**
- ពន្យល់ **MAC Address Table**
- ពន្យល់ Switching Process
- ប្រើ `show mac address-table`

## Lecture Notes

Switch ប្រើ **MAC Address Table** ដើម្បីសម្រេចថាត្រូវបញ្ជូន Frame ទៅ Port ណា។

Important concepts:

`Source MAC`  
`Destination MAC`  
`MAC Address Table`  
`Frame`  
`Flooding`  
`Forwarding`

## Cisco Commands

```text
show mac address-table
show interfaces
show interfaces status
```

## Packet Tracer Lab

Topology:

```text
PC1 ---- SW1 ---- PC2
          |
         PC3
```

Task:

1. Ping between PCs.
2. Check MAC table.
3. Observe learned MAC addresses.

## Homework

ពន្យល់៖

- How does a Switch learn a MAC address?
- What happens if destination MAC is unknown?

## Quiz

10 questions.

## Module Exam

**MAC Learning Practical Lab**

---

# MODULE 6 — IPv4 Addressing

## Learning Objectives

សិស្សអាច៖

- អាន IPv4 Address
- ស្គាល់ **Subnet Mask**
- ស្គាល់ **Network Address**
- ស្គាល់ **Host Address**
- ស្គាល់ **Broadcast Address**
- Configure IPv4 នៅ End Device

## Lecture Notes

Example:

```text
IP Address:   192.168.10.20
Subnet Mask:  255.255.255.0
```

Equivalent:

```text
192.168.10.20/24
```

Important:

`IPv4 Address`  
`Subnet Mask`  
`Default Gateway`  
`Network Address`  
`Broadcast Address`

## Packet Tracer Lab

Configure:

```text
PC1 = 192.168.10.10/24
PC2 = 192.168.10.20/24
```

Test:

```text
ping 192.168.10.20
```

## Homework

Calculate:

- Network address
- Broadcast address
- First host
- Last host

for 5 networks.

## Quiz

15 questions on IPv4.

## Module Exam

**IPv4 Address Configuration + Ping Test**

---

# MODULE 7 — IPv4 Subnetting

## Learning Objectives

សិស្សអាច៖

- Convert Decimal ↔ Binary
- Understand `/24`, `/25`, `/26`, `/27`, `/28`, `/29`, `/30`
- Calculate subnets
- Calculate usable hosts
- Select correct subnet

## Lecture Notes

Students learn the basic formula:

```text
Number of Hosts = 2^h - 2
```

Examples:

```text
/24 = 254 usable hosts
/25 = 126 usable hosts
/26 = 62 usable hosts
/27 = 30 usable hosts
/28 = 14 usable hosts
/29 = 6 usable hosts
/30 = 2 usable hosts
```

## Packet Tracer Lab

Build:

```text
PC1 -- SW1 -- Router1 -- SW2 -- PC2
```

Use different subnets for each network.

## Homework

Subnetting Worksheet:

- 10 questions
- Network address
- Broadcast
- Host range
- Number of hosts

## Quiz

20 subnetting questions.

## Module Final Exam

**Subnetting Examination**

Theory + Calculation + Practical IP Planning.

---

# MODULE 8 — Basic Router Configuration

## Learning Objectives

សិស្សអាច៖

- Configure Router hostname
- Configure Interface IP
- Enable interface
- Verify interfaces
- Understand Default Gateway

## Cisco Commands

```text
enable
configure terminal
hostname R1

interface gigabitEthernet 0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

show ip interface brief
```

## Lecture Notes

Common interface states:

```text
up/up
down/down
administratively down
```

`no shutdown` ត្រូវបានប្រើដើម្បី enable interface។

## Packet Tracer Lab

Topology:

```text
PC1 ---- SW1 ---- R1
```

Configure:

```text
PC1 = 192.168.1.10/24
R1 G0/0 = 192.168.1.1/24
```

Ping R1.

## Homework

Write the complete configuration sequence for G0/0.

## Quiz

10 questions.

## Module Exam

Configure Router from blank configuration and successfully ping Router.

---

# MODULE 9 — Static Routing

## Learning Objectives

សិស្សអាច៖

- Explain **Routing**
- Explain **Routing Table**
- Configure **Static Route**
- Verify route
- Troubleshoot routing failure

## Cisco Commands

```text
show ip route
ip route
```

Example:

```text
R1(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

## Packet Tracer Lab

Topology:

```text
PC1 -- SW1 -- R1 -------- R2 -- SW2 -- PC2
```

Task:

- Configure both routers.
- Configure static routes.
- Test end-to-end connectivity.

## Homework

Draw a 3-router topology and identify:

- Destination network
- Next hop
- Exit interface

## Quiz

15 questions.

## Module Exam

**3-network Static Routing Practical**

---

# MODULE 10 — VLAN Fundamentals

## Learning Objectives

សិស្សអាច៖

- Explain **VLAN**
- Create VLAN
- Name VLAN
- Assign Access Port
- Verify VLAN

## Cisco Commands

```text
vlan 10
name STUDENT

interface fastEthernet 0/1
switchport mode access
switchport access vlan 10
```

Verify:

```text
show vlan brief
```

## Packet Tracer Lab

Create:

```text
VLAN 10 = STUDENT
VLAN 20 = TEACHER
```

Assign PCs to each VLAN.

## Homework

Explain:

- Why do we use VLAN?
- What is an Access Port?

## Quiz

10 questions.

## Module Exam

Configure 2 VLANs and assign ports correctly.

---

# MODULE 11 — Trunking

## Learning Objectives

សិស្សអាច៖

- Explain **Access Port**
- Explain **Trunk Port**
- Understand **802.1Q**
- Configure Trunk
- Verify Trunk

## Cisco Commands

```text
interface gigabitEthernet 0/1
switchport mode trunk
```

Verify:

```text
show interfaces trunk
```

## Packet Tracer Lab

Topology:

```text
PC1 -- SW1 ===== SW2 -- PC3
PC2 --/           \-- PC4
```

Configure:

```text
VLAN 10
VLAN 20
```

Configure link between switches as Trunk.

## Homework

Compare:

```text
Access Port
vs
Trunk Port
```

## Quiz

10 questions.

## Module Exam

Configure VLAN + Trunk between two switches.

---

# MODULE 12 — Inter-VLAN Routing

## Learning Objectives

សិស្សអាច៖

- Explain why VLANs need routing
- Configure **Router-on-a-Stick**
- Configure Subinterfaces
- Configure `802.1Q`
- Verify connectivity

## Cisco Commands

Example:

```text
interface gigabitEthernet 0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

interface gigabitEthernet 0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
```

## Packet Tracer Lab

Topology:

```text
PC1 -- SW1 ---- R1
PC2 --/
```

VLAN:

```text
VLAN 10 = STUDENT
VLAN 20 = TEACHER
```

Task:

- Configure VLANs.
- Configure Trunk.
- Configure Router-on-a-Stick.
- Configure Default Gateway.
- Test communication between VLANs.

## Homework

Draw and explain traffic flow:

```text
PC → Switch → Trunk → Router → Trunk → Switch → PC
```

## Quiz

15 questions.

## Module Exam

**Inter-VLAN Routing Practical Examination**

---

# MODULE 13 — DHCP & Basic Network Services

## Learning Objectives

សិស្សអាច៖

- Explain **DHCP**
- Explain **DHCP Pool**
- Configure Cisco DHCP
- Configure Default Gateway
- Configure DNS Server
- Verify DHCP

## Cisco Commands

```text
ip dhcp excluded-address 192.168.1.1 192.168.1.10

ip dhcp pool LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
```

Verify:

```text
show ip dhcp binding
show ip dhcp pool
```

## Packet Tracer Lab

Configure Router as DHCP Server.

PCs should receive addresses automatically.

## Homework

Explain:

```text
DHCP Discover
DHCP Offer
DHCP Request
DHCP ACK
```

## Quiz

10 questions.

## Module Exam

**DHCP Practical Test**

---

# MODULE 14 — IPv6 Fundamentals

## Learning Objectives

សិស្សអាច៖

- Explain why IPv6 is used
- Identify IPv6 address format
- Recognize Prefix
- Configure IPv6
- Verify IPv6

## Important Keywords

`IPv6`  
`Global Unicast`  
`Link-Local`  
`Prefix`  
`Interface ID`

## Cisco Commands

```text
ipv6 unicast-routing

interface gigabitEthernet 0/0
ipv6 address 2001:db8:1::1/64
no shutdown
```

Verify:

```text
show ipv6 interface brief
show ipv6 route
```

## Packet Tracer Lab

Configure IPv6 between:

```text
PC1 ---- SW1 ---- R1
```

Test IPv6 connectivity.

## Homework

Write 10 IPv6 addresses and identify `/64` prefix.

## Quiz

10 questions.

## Module Exam

IPv6 configuration + connectivity test.

---

# MODULE 15 — Basic Network Security & Troubleshooting

## Learning Objectives

សិស្សអាច៖

- Understand basic **Network Security**
- Configure password protection
- Configure basic **SSH**
- Use troubleshooting commands
- Find configuration errors

## Cisco Commands

Useful commands:

```text
show running-config
show startup-config
show ip interface brief
show interfaces
show ip route
show vlan brief
show interfaces trunk
show mac address-table
ping
traceroute
```

Basic SSH preparation:

```text
hostname R1
ip domain-name lab.local
username admin secret cisco123

crypto key generate rsa

line vty 0 4
login local
transport input ssh
```

## Troubleshooting Method

Use:

**Physical → Interface → IP → VLAN → Routing → Service**

Students learn to ask:

1. Is the cable connected?
2. Is interface `up/up`?
3. Is IP address correct?
4. Is subnet mask correct?
5. Is VLAN correct?
6. Is Trunk correct?
7. Is route available?
8. Is Default Gateway correct?

## Packet Tracer Troubleshooting Lab

Instructor introduces errors such as:

- Wrong IP address
- Wrong VLAN
- Wrong subnet mask
- Shutdown interface
- Wrong default gateway
- Missing static route
- Wrong trunk configuration

Students must diagnose and fix them.

## Homework

Complete a troubleshooting worksheet with 10 scenarios.

## Quiz

20 troubleshooting questions.

## Module Final Practical Exam

Student receives a broken network and must:

**Identify → Diagnose → Fix → Verify**

---

# MODULE 16 — Final Project + Final Examination

# Final Practical Project

## Project Title

**Small Enterprise Network Design**

## Requirements

Students must create a complete network containing:

- 2 Routers
- 2 Switches
- At least 6 PCs
- VLAN 10
- VLAN 20
- Trunk Link
- Inter-VLAN Routing
- Static Routing
- DHCP
- Basic Security
- IPv4 Addressing
- Verification

## Suggested Topology

```text
               R1 -------- R2
                |          |
                |          |
               SW1        SW2
              /   \      /   \
           VLAN10 VLAN20 VLAN10 VLAN20
             |       |     |      |
            PC1     PC2   PC3    PC4
```

## Required Configuration

### Switch

```text
hostname
enable secret
VLAN
Access Port
Trunk
```

### Router

```text
hostname
IP Address
no shutdown
Static Route
DHCP
Inter-VLAN Routing
```

### Security

```text
enable secret
username
SSH
VTY
banner motd
```

### Verification

Students must demonstrate:

```text
show running-config
show ip interface brief
show vlan brief
show interfaces trunk
show ip route
show ip dhcp binding
ping
traceroute
```

---

# 4. Assessment System

Recommended grading:

| Component | Weight |
|---|---:|
| Attendance & Participation | 10% |
| Homework | 10% |
| Weekly Quizzes | 10% |
| Packet Tracer Labs | 20% |
| Module Exams | 20% |
| Final Project | 15% |
| Final Exam | 15% |
| **Total** | **100%** |

---

# 5. Recommended Weekly Lesson Structure

Each class = **4 hours**

## Hour 1 — Lecture

Teacher explains:

**Concept → Diagram → Keyword → Real-world Example**

## Hour 2 — Cisco CLI Demonstration

Teacher demonstrates configuration step by step.

Example:

```text
enable
configure terminal
hostname SW1
```

## Hour 3 — Packet Tracer Lab

Students independently configure the topology.

Teacher provides guidance but does not immediately give the answer.

## Hour 4 — Verification + Troubleshooting + Quiz

Students:

- Verify
- Troubleshoot
- Explain their configuration
- Complete short quiz

---

# 6. Teaching Method for Beginners

Use this sequence for each new Cisco technology:

### STEP 1 — What?

Example:

**What is VLAN?**

### STEP 2 — Why?

**Why do we need VLAN?**

### STEP 3 — How?

**How does VLAN work?**

### STEP 4 — Configure

```text
vlan 10
name STUDENT
```

### STEP 5 — Verify

```text
show vlan brief
```

### STEP 6 — Troubleshoot

Teacher creates a configuration error.

### STEP 7 — Explain

Student must explain not only **what command** was used but **why**.

---

# 7. Weekly Quiz Format

Recommended each quiz = 10–20 questions.

Question types:

**Type A — Multiple Choice**

Example:

Which device connects different IP networks?

A. Hub  
B. Switch  
C. Router  
D. PC

**Answer:** C

**Type B — Command Identification**

What does this command do?

```text
show ip interface brief
```

**Type C — Configuration**

Write the Cisco command to assign:

```text
192.168.1.1/24
```

**Type D — Troubleshooting**

Interface shows:

```text
administratively down
```

What is the problem?

**Type E — Scenario**

PC1 cannot ping PC2. Identify three possible causes.

---

# 8. Module Exam Structure

Each Module Exam can contain:

### Part A — Theory
20%

### Part B — Cisco Commands
20%

### Part C — Configuration
30%

### Part D — Troubleshooting
20%

### Part E — Explanation
10%

This prevents students from simply memorizing commands.

---

# 9. Final Examination

## Part A — Networking Theory
20 questions

Topics:

- LAN/WAN
- OSI
- TCP/IP
- Switch
- Router
- Ethernet
- MAC
- IPv4
- IPv6
- VLAN
- Routing
- DHCP
- Security

## Part B — IPv4 & Subnetting

Students solve:

- Network Address
- Broadcast
- Host Range
- Prefix
- Number of Hosts

## Part C — Cisco CLI

Students write commands for:

- Switch
- Router
- VLAN
- Trunk
- Static Route
- DHCP

## Part D — Packet Tracer Practical

Build and configure the final topology.

## Part E — Troubleshooting

Teacher provides a broken network.

Student must:

**Find the problem → Fix it → Verify it → Explain it**

---

# 10. Final Project Rubric

| Category | Points |
|---|---:|
| Topology Design | 10 |
| IPv4 Addressing | 15 |
| Switch Configuration | 15 |
| VLAN Configuration | 10 |
| Trunk Configuration | 10 |
| Inter-VLAN Routing | 10 |
| Static Routing | 10 |
| DHCP | 5 |
| Security | 5 |
| Verification | 5 |
| Troubleshooting | 5 |
| **Total** | **100** |

---

# 11. Essential Cisco Commands Students Should Know

## Basic

```text
enable
disable
configure terminal
exit
end
?
```

## Configuration

```text
hostname
enable secret
banner motd
service password-encryption
```

## Interface

```text
interface
ip address
no shutdown
shutdown
description
```

## Verification

```text
show running-config
show startup-config
show ip interface brief
show interfaces
```

## Switching

```text
show mac address-table
show vlan brief
show interfaces trunk
switchport mode access
switchport access vlan
switchport mode trunk
```

## Routing

```text
show ip route
ip route
```

## DHCP

```text
ip dhcp pool
ip dhcp excluded-address
show ip dhcp binding
show ip dhcp pool
```

## IPv6

```text
ipv6 unicast-routing
ipv6 address
show ipv6 interface brief
show ipv6 route
```

## Testing

```text
ping
traceroute
```

## Security / SSH

```text
username
ip domain-name
crypto key generate rsa
login local
transport input ssh
```

---

# 12. Instructor Teaching Philosophy

សិស្ស Beginner មិនគួររៀនដោយ **Memorize Commands Only** ទេ។

ត្រូវឱ្យសិស្សយល់៖

**Concept → Packet Flow → Configuration → Verification → Troubleshooting**

ឧទាហរណ៍ នៅពេលសិស្សរៀន VLAN គួរតែអាចឆ្លើយបានទាំង៖

> VLAN គឺជាអ្វី?

> ហេតុអ្វីបានជាយើងប្រើ VLAN?

> Access Port ខុសពី Trunk Port ដូចម្តេច?

> Packet ឆ្លងពី VLAN 10 ទៅ VLAN 20 តាមណា?

> Command ណាដែលប្រើ Configure VLAN?

> Command ណាដែលប្រើ Verify VLAN?

> បើ PC មិនអាច Ping បាន តើត្រូវ Troubleshoot តាមជំហានណា?

នេះជាវិធីដែលធ្វើឱ្យសិស្សមាន **Networking Skill** ពិតប្រាកដ មិនមែនចេះតែ Copy Cisco Commands ប៉ុណ្ណោះ។