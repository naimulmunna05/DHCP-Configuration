# DHCP-Configuration
# 🌐 DHCP-Server-Configuration

💡 Overview: A foundational network simulation built in Cisco Packet Tracer to configure a Cisco router as a DHCP server for automated IP address allocation across local devices.

---

## 📋 Project Summary Table

| Category | Details / Description |
| :--- | :--- |
| Network Scope | `192.168.1.0/24` (Local Area Network used to manage automated IP distribution) |
| Hardware Architecture | • Cisco 2811 Router<br>• Cisco 2960 Switch<br>• Server & Client PCs / Laptops |
| Tools & Skills | • Cisco Packet Tracer<br>• Router Interface Configuration<br>• DHCP Pool & Excluded Address Setup<br>• Dynamic IP Verification |

---

## 📊 IP Addressing Table

| Device / Role | Host Name | Interface | IP Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Router | Router0 | FastEthernet0/0 | `192.168.1.1` | `255.255.255.0` | `-` |
| Server | Server0 | FastEthernet0 | `192.168.1.6` | `255.255.255.0` | `192.168.1.1` |
| Client Device | PC0 - PC2 | FastEthernet0 | *Dynamic (DHCP)* | `255.255.255.0` | `192.168.1.1` |
| Client Device | Laptop0 | FastEthernet0 | *Dynamic (DHCP)* | `255.255.255.0` | `192.168.1.1` |

---

## 📷 Screenshots

![DHCP Configuration Overview](DHCP%20Conf/images/DHCP_Conf.png)

## 💻 Configuration Commands (CLI)

### 1. Router Interface Configuration
```text
Router(config)# interface fastethernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown

2. DHCP Pool Setup
Plaintext
Router(config)# ip dhcp pool MY_POOL
Router(config-dhcp)# network 192.168.1.0 255.255.255.0
Router(config-dhcp)# default-router 192.168.1.1
Router(config-dhcp)# dns-server 8.8.8.8
Router(config)# ip dhcp excluded-address 192.168.1.1

🚀 How to Test
Download and open the .pkt file in Cisco Packet Tracer.

Click on any PC or Laptop, navigate to Desktop -> IP Configuration, and switch from Static to DHCP.

Verify that the device automatically receives a valid IP address from the router pool.
