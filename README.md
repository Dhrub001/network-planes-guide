# 📡 Network Planes Architecture — From Theory to Real Networks

## 🚀 Overview

This repository provides a **practical and in-depth guide** to understanding **Data Plane, Control Plane, and Management Plane** in real-world networking.

Unlike basic theory notes, this project includes:

* ✅ Architecture explanations
* ✅ Real device configurations (OSPF, BGP, MPLS)
* ✅ Packet flow analysis
* ✅ Troubleshooting scenarios
* ✅ SDN comparison

---

## 🧠 Network Planes Explained

| Plane            | Role            | Real Function                     |
| ---------------- | --------------- | --------------------------------- |
| Data Plane       | Forward traffic | Packet switching, MPLS forwarding |
| Control Plane    | Make decisions  | OSPF, BGP route calculation       |
| Management Plane | Operate network | SSH, SNMP, monitoring             |

---

## 🖼️ Architecture Diagram

![Network Planes](diagrams/network-planes.png)

---

## ⚙️ Data Plane (Forwarding)

* Operates at **line rate (ASIC-based)**
* Uses **FIB, MAC, ARP tables**
* No decision-making → only execution

### 🔥 Example

```text
Packet arrives → FIB lookup → Forwarded
```

---

## 🧠 Control Plane (Decision Engine)

* Runs routing protocols:

  * OSPF
  * BGP
* Builds:

  * RIB → FIB

### 🔥 Example Config

```bash
router ospf 1
 network 10.0.0.0 0.0.0.255 area 0
```

---

## 🛠️ Management Plane (Operations)

* SSH access
* Monitoring (SNMP, NetFlow)
* Logging (Syslog)

---

## 🔄 Packet Flow (Real Scenario)

![Packet Flow](diagrams/packet-flow.png)

### Flow:

1. Control Plane decides path
2. Data Plane forwards packets
3. Management Plane monitors

---

## 🔥 SDN vs Traditional Networking

![SDN](diagrams/sdn-architecture.png)

| Feature       | Traditional | SDN         |
| ------------- | ----------- | ----------- |
| Control Plane | Distributed | Centralized |
| Data Plane    | Integrated  | Separated   |

---

## 🧪 Hands-On Labs

| Lab   | Description          |
| ----- | -------------------- |
| Lab 1 | Packet Flow Analysis |
| Lab 2 | OSPF Configuration   |
| Lab 3 | BGP Basic Setup      |

👉 Check `/labs/`

---

## ⚙️ Configurations

* OSPF → `/configs/ospf-basic/`
* BGP → `/configs/bgp-basic/`
* MPLS → `/configs/mpls-intro/`

---

## 🛑 Troubleshooting

Common real-world issues:

* Route not installed in FIB
* OSPF neighbor down
* BGP session not established

👉 See `/troubleshooting/common-issues.md`

---

## 💼 Real-World Relevance

This project reflects:

* ISP routing design (BGP)
* Enterprise networks (OSPF)
* Data center networking
* SDN architectures

---

## 📈 Skills Demonstrated

* Network architecture design
* Routing protocol understanding
* Packet flow analysis
* Troubleshooting methodology
* Documentation & visualization

---

## 📌 Author

**Dhrub Raj Giri**
Network Engineer | Cybersecurity Enthusiast

---
# 📡 Network Planes Architecture Guide

## 📌 Overview

This repository provides a detailed explanation of **network architecture planes**—a fundamental concept in modern networking. It covers the **Data Plane, Control Plane, and Management Plane**, along with real-world examples, packet flow, and relevance in traditional and Software-Defined Networking (SDN).

This guide is designed for:

* Network Engineers
* CCNA / CCNP learners
* Cybersecurity enthusiasts
* Anyone interested in understanding how networks operate internally

---

## 🧠 What are Network Planes?

In networking, operations are logically divided into three planes:

| Plane                | Purpose                              |
| -------------------- | ------------------------------------ |
| **Data Plane**       | Forwards traffic                     |
| **Control Plane**    | Makes routing decisions              |
| **Management Plane** | Handles configuration and monitoring |

---

## ⚙️ Data Plane (Forwarding Plane)

### 📌 Definition

The Data Plane is responsible for **forwarding packets** from source to destination using precomputed decisions.

### 🔍 Key Functions

* Packet forwarding
* Frame switching
* MPLS label switching
* QoS enforcement
* ACL filtering

### ⚡ How It Works

1. Packet arrives at interface
2. Lookup performed in forwarding tables
3. Best path already known
4. Packet forwarded immediately

### 🧠 Key Tables

| Table                             | Description         |
| --------------------------------- | ------------------- |
| FIB (Forwarding Information Base) | Fast routing lookup |
| MAC Table                         | Layer 2 forwarding  |
| ARP Table                         | IP-to-MAC mapping   |

### 🧪 Example

```
PC → Switch → Router → Internet
```

👉 The Data Plane forwards packets using the FIB without making decisions.

### ⚡ Insight

* Operates at **high speed**
* Runs in **hardware (ASICs)**

---

## 🧠 Control Plane

### 📌 Definition

The Control Plane is responsible for **decision-making** and determining the best path for traffic.

### 🔍 Key Functions

* Routing protocol operation
* Topology discovery
* Path calculation
* Route selection

### ⚙️ Protocols

* OSPF
* BGP
* RIP
* IS-IS

### ⚡ How It Works

1. Routers exchange routing updates
2. Build topology database
3. Run routing algorithms
4. Populate routing table (RIB)
5. Install best routes into FIB

### 🧠 Key Tables

| Table                          | Description        |
| ------------------------------ | ------------------ |
| RIB (Routing Information Base) | Stores all routes  |
| LSDB (Link-State Database)     | OSPF topology info |

### 🧪 Example

```bash
router ospf 1
 network 10.0.0.0 0.0.0.255 area 0
```

👉 This configuration operates in the **Control Plane**.

### ⚡ Insight

* Acts as the **brain of the network**
* Runs in **CPU (software)**

---

## 🛠️ Management Plane

### 📌 Definition

The Management Plane is responsible for **configuration, monitoring, and administration** of network devices.

### 🔍 Key Functions

* Device configuration
* Monitoring and logging
* Authentication and access control
* Performance analysis

### ⚙️ Tools & Protocols

* SSH / Telnet
* SNMP
* Syslog
* NetFlow
* REST APIs

### 🧪 Example

```bash
ssh admin@router
```

👉 This is part of the **Management Plane**.

### ⚡ Insight

* Interface between **network and administrator**

---

## 🔄 End-to-End Packet Flow

### 📡 Scenario

```
User → Internet → Server
```

### Flow Explanation

1. **Control Plane**

   * Determines best path using routing protocols

2. **Data Plane**

   * Forwards packets hop-by-hop

3. **Management Plane**

   * Used by admin to monitor and troubleshoot

---

## 🔥 Traditional Networking vs SDN

| Feature       | Traditional Network | SDN         |
| ------------- | ------------------- | ----------- |
| Control Plane | Distributed         | Centralized |
| Data Plane    | Integrated          | Separated   |
| Management    | Manual              | Automated   |
| Flexibility   | Low                 | High        |

### 💡 Key Concept

* In SDN:

  * Control Plane → Centralized Controller
  * Data Plane → Network Devices

---

## 🎯 Real-World Use Cases

* ISP networks (BGP routing)
* Enterprise networks (OSPF, VLANs)
* Data centers (leaf-spine architecture)
* SDN environments (centralized control)

---

## 📊 Summary

| Plane            | Role                | Runs On         | Example           |
| ---------------- | ------------------- | --------------- | ----------------- |
| Data Plane       | Forward packets     | Hardware (ASIC) | Packet forwarding |
| Control Plane    | Decide routes       | CPU             | OSPF, BGP         |
| Management Plane | Configure & monitor | Admin tools     | SSH, SNMP         |

---

## 🚀 Future Improvements (Planned)

* [ ] Add network diagrams (draw.io)
* [ ] Include packet flow visualization
* [ ] Add real lab configurations (OSPF, BGP)
* [ ] Expand SDN architecture section
* [ ] Add troubleshooting scenarios

---

## 📚 References

* RFC documents (IETF)
* Cisco Networking Documentation
* Juniper Documentation
* Networking textbooks and labs

---

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome.

---

## 📌 Author

**Dhrub Raj Giri**
Network Engineer | Cybersecurity Enthusiast

---
