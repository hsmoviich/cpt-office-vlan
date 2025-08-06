# 🧠 Small Office Network Design – CPT Lab with VLSM

## 🎯 Objective

Design and configure a small office network using **Cisco Packet Tracer**. This lab focuses on implementing **VLANs**, **inter-VLAN routing**, and **VLSM (Variable Length Subnet Masking)**. It simulates a realistic office environment with multiple departments and services. The goal is to demonstrate your understanding of L2/L3 devices, subnetting, and basic network services like DHCP and DNS.

---

## 🖥️ VLAN Structure and Host Requirements

| VLAN Name       | Description             | Number of Hosts | Devices Included                     |
|-----------------|-------------------------|------------------|--------------------------------------|
| Admin VLAN      | Admin department        | 10               | 10 PCs                               |
| HR VLAN         | Human Resources         | 15               | 15 PCs                               |
| IT VLAN         | IT department           | 25               | 25 PCs                               |
| Guest VLAN      | Visitors/Guests         | 20               | 20 PCs (with internet-only access)   |
| Servers VLAN    | Internal servers        | 5                | DHCP Server, DNS Server, 3 other servers |
| Router & L3 SW  | Core infrastructure     | 2                | 1 Router, 1 Layer 3 Switch           |

🧮 Total usable hosts required: **77**  
You must perform **VLSM subnetting** on the base network: `192.168.0.0/24` to accommodate all VLANs efficiently.

---

## 🗂️ Network Design Requirements

- Assign **each VLAN its own subnet** using **VLSM**
- Configure **Router-on-a-Stick** or **L3 Switch inter-VLAN routing**
- Set up:
  - **DHCP Server** for dynamic IP assignment (excluding Server VLAN)
  - **DNS Server** in the Server VLAN
- Assign **default gateways** for each VLAN
- Use **static IPs** for network infrastructure (router, L3 switch, servers)
- Implement **trunking** between the Layer 3 switch and the router (if used)
- Apply **basic security settings**:
  - Disable unused ports
  - Assign access ports to correct VLANs
  - Use meaningful port descriptions

---

## 🧩 Devices Required

- 1 × Router (e.g., Cisco 2911)
- 1 × Layer 3 Switch
- 2 × Standard Switches (optional, for VLAN separation)
- 75+ PCs (for Admin, HR, IT, Guests)
- 1 × DHCP Server
- 1 × DNS Server
- 3 × Additional Servers (e.g., Web, File, Mail)

---

## 📝 Tasks

1. **Design the IP Addressing Scheme**  
   - Subnet the `192.168.0.0/24` using VLSM
   - Assign IPs to each VLAN based on host needs

2. **Topology Creation in Packet Tracer**
   - Add and label all required devices
   - Assign VLANs and port configurations
   - Use trunks and access ports appropriately

3. **Configure Inter-VLAN Routing**
   - Use either a router-on-a-stick or Layer 3 switch SVI
   - Assign IP addresses to VLAN interfaces

4. **Configure DHCP and DNS**
   - DHCP server should serve Admin, HR, IT, Guest VLANs
   - DNS Server in Server VLAN for domain resolution

5. **Test Connectivity**
   - Ping across VLANs
   - Test DHCP and DNS resolution
   - Verify isolation between Guest VLAN and internal VLANs

---

## 🧠 Bonus Ideas

- Add ACLs to restrict Guest VLAN access
- Simulate internet access via NAT or cloud device
- Add a backup DNS or DHCP server

---

## 📁 Deliverables

- `.pkt` file with fully configured lab
- Screenshot of the topology
- This `instructions.md` and your `README.md` on GitHub

---

✅ Use this project to **demonstrate your practical networking skills** and ability to design real-world topologies. It’s perfect for internships and job applications in **networking and cybersecurity**.
