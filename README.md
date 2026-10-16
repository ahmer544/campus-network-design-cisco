# 🏢 Albion University — Multi-Campus Enterprise Network Design & Simulation

![Cisco Packet Tracer](https://img.shields.io/badge/Simulator-Cisco%20Packet%20Tracer-005073?logo=cisco)
![Networking](https://img.shields.io/badge/Category-Computer%20Networks-blue)
![Security](https://img.shields.io/badge/Security-SSH%20%7C%20Port--Security-red)
![Routing & Switching](https://img.shields.io/badge/Protocols-VLAN%20%7C%20DHCP%20%7C%20RIPv2%20%7C%20Static--Routing-orange)

An enterprise-grade multi-site university network designed and implemented in Cisco Packet Tracer based on the **Albion University** case study. The architecture connects a **Main Campus (3 Buildings)**, a **Branch Campus (20 miles apart)**, and **Cloud Infrastructure** using a 3-tier hierarchical topology (Core, Distribution, and Access layers).

---

## 📐 System Architecture & Topology

<img width="1207" height="364" alt="topology" src="https://github.com/user-attachments/assets/1cbb8078-496a-40f3-8120-529df8adbc8a" />


---

## 📋 Case Study Overview & Requirements

Albion University operates across two geographic locations 20 miles apart, serving staff and students across four core faculties: *Health and Sciences*, *Business*, *Engineering & Computing*, and *Art & Design*.

### Infrastructure Breakdown:
* **Main Campus:**
  * **Building A:** Administrative staff (Management, HR, Finance) and Faculty of Business sharing switch infrastructure via VLAN isolation.
  * **Building B:** Faculty of Engineering & Computing and Faculty of Art & Design.
  * **Building C:** Student Labs and IT Department hosting the internal University Web Server and local services.
* **External Cloud Services:** External Cloud Network hosting the University Email Server.
* **Branch Campus:** Faculty of Health & Sciences with staff offices and student labs segregated on separate floors/VLANs.

---

## ✨ Implemented Technologies & Specifications

1. **Hierarchical 3-Tier Design:** Core, Distribution, and Access switching domains for scalable multi-building connectivity.
2. **VLAN Segmentation (IEEE 802.1Q):** Logical separation of administrative departments, academic faculties, and student labs to reduce broadcast domains.
3. **Subnetting & IP Scheme:** Custom Class C IPv4 addressing with VLSM allocation per department.
4. **Inter-VLAN Routing:** Router-on-a-Stick sub-interface routing enabling secure cross-departmental communication.
5. **Dynamic IP Allocation (DHCP):** Cisco IOS router-based DHCP pools delivering dynamic IP addresses to end-user devices in Building A and academic units.
6. **Dynamic & Static Routing:** 
   * **RIPv2** configured across all internal campus routers for dynamic route convergence.
   * **Static Routing** configured for reachability to the external Cloud Email Server.
7. **Switchport Security (Port-Security):** Configured port-security on access switches to prevent unauthorized MAC address connections and rogue device placement.
8. **Secure Remote Management (SSH):** Configured SSH on core routing and switching hardware for encrypted CLI management.
9. **Cabling & Hardware Selection:** Serial DCE/DTE links for WAN interconnection and standard straight-through/crossover Ethernet connections for LAN infrastructure.

---

## 📊 Network Addressing & VLAN Schema

| Location / Building | Department / Faculty | VLAN ID | Network Subnet | Default Gateway | IP Allocation |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Building A** | Management / Admin | VLAN 10 | `192.168.1.0/24` | `192.168.1.1` | Router DHCP |
| **Building A** | HR Department | VLAN 20 | `192.168.2.0/24` | `192.168.2.1` | Router DHCP |
| **Building A** | Finance Department | VLAN 30 | `192.168.3.0/24` | `192.168.3.1` | Router DHCP |
| **Building A** | Faculty of Business | VLAN 40 | `192.168.4.0/24` | `192.168.4.1` | Router DHCP |
| **Building B** | Engineering & Computing | VLAN 50 | `192.168.5.0/24` | `192.168.5.1` | Router DHCP / Static |
| **Building B** | Art & Design | VLAN 60 | `192.168.6.0/24` | `192.168.6.1` | Router DHCP |
| **Building C** | Student Labs | VLAN 70 | `192.168.7.0/24` | `192.168.7.1` | Router DHCP |
| **Building C** | IT Dept & Web Server | VLAN 80 | `192.168.8.0/24` | `192.168.8.1` | Static / DHCP |
| **Branch Campus** | Health & Sciences Staff | VLAN 90 | `192.168.9.0/24` | `192.168.9.1` | Router DHCP |
| **Branch Campus** | Health & Sciences Labs | VLAN 100| `192.168.10.0/24` | `192.168.10.1` | Router DHCP |
| **External Cloud**| Cloud Email Server | N/A | `20.0.0.0/30` | `20.0.0.1` | Static IP |

---

## 🧪 Verification & Testing

End-to-end communication was verified using ICMP Ping, HTTP access to the internal Web Server, and SMTP/POP3 reachability to the external Cloud Email Server across WAN links:

<img width="415" height="284" alt="ping_test" src="https://github.com/user-attachments/assets/d5583718-9fb5-4723-82c8-f5b1fc49813f" />


---

## 🛠️ Tools & Equipment Used

* **Simulation Platform:** Cisco Packet Tracer
* **Core Hardware:** Cisco 2911 Integrated Services Routers (HWIC-2T Serial Cards), Cisco 3650 Multilayer Switches, Cisco 2960 Access Switches
* **Protocols:** IEEE 802.1Q, RIPv2, Dynamic DHCP, SSH, ICMP, TCP/IP, Static Routing
