# Basic VLAN Configuration Using Cisco Packet Tracer

## 📘 Project Overview
This lab demonstrates a **basic VLAN configuration** using a single Cisco switch.  
The objective is to logically segment a network so that devices in **VLAN 10** cannot communicate with devices in **VLAN 20**, even though all PCs are connected to the same physical switch.

This project helps in understanding **Layer 2 network isolation** using VLANs.

---

## 🎯 Lab Objectives
- Create multiple VLANs on a switch
- Assign switch ports to specific VLANs
- Configure access ports
- Verify VLAN-based communication
- Ensure traffic isolation without using a router

---

## 🧱 Network Topology

### Devices Used
- **1 × Cisco 2960 Switch**
- **4 × PCs**

### VLAN Structure
| VLAN ID | VLAN Name | Group |
|-------:|-----------|-------|
| 10 | STUDENTS | Group A |
| 20 | FACULTY | Group B |

---

## 🔌 Physical Connections

### Cabling
- **PC-to-Switch**: Copper Straight-Through

| PC  | Switch Port | VLAN |
|-----|------------|------|
| PC0 | Fa0/1 | VLAN 10 |
| PC1 | Fa0/2 | VLAN 10 |
| PC2 | Fa0/3 | VLAN 20 |
| PC3 | Fa0/4 | VLAN 20 |

---

## 🌐 IP Addressing Scheme

### VLAN 10 – Group A (Students)
- PC0 → `192.168.10.2 /24`
- PC1 → `192.168.10.3 /24`

### VLAN 20 – Group B (Faculty)
- PC2 → `192.168.20.2 /24`
- PC3 → `192.168.20.3 /24`

> No default gateway is configured because routing is not required.

---

## ⚙️ Switch Configuration Summary

### VLAN Creation
- VLAN 10 named **STUDENTS**
- VLAN 20 named **FACULTY**

### Port Assignment
- **Fa0/1 – Fa0/2** → VLAN 10 (Access Ports)
- **Fa0/3 – Fa0/4** → VLAN 20 (Access Ports)

Configuration was saved using `write memory`.

---

## ✅ Verification & Testing

### VLAN Verification
Command used:

Expected output:
- VLAN 10 → Fa0/1, Fa0/2
- VLAN 20 → Fa0/3, Fa0/4

---

### Connectivity Tests

#### Same VLAN Communication
- PC0 → PC1 ✔ (Success)
- PC2 → PC3 ✔ (Success)

#### Inter-VLAN Isolation Test
- PC0 → PC2 ❌ (Request Timed Out)

This confirms proper VLAN isolation.

---

## 📂 Files Included
- `Basic VLAN Configuration.pkt` – Cisco Packet Tracer lab file
- `README.md` – Project documentation

---

## 🧠 Key Learning Outcomes
- VLAN creation and management
- Logical network segmentation
- Access port configuration
- Security through traffic isolation
- VLAN behavior without routing

---

## 🛠 Tools Used
- Cisco Packet Tracer
- Cisco 2960 Switch

---

## 👤 Author
**Umar Farooq**  
Networking Lab Assignment
