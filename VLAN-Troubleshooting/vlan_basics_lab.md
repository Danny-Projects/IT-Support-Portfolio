# VLAN Basics & Network Segmentation Troubleshooting Lab

## Lab Overview
This lab demonstrates basic VLAN concepts using VirtualBox internal networks to simulate network segmentation. Two Windows 10 Home client systems were placed on separate VLANs to validate isolation, followed by troubleshooting steps to restore connectivity.

---

## Environment
- Windows 10 Home (Client 1 – VLAN 10)
- Windows 10 Home (Client 2 – VLAN 20)
- VirtualBox Internal Networks
- Static IPv4 addressing

---

## Objectives
- Demonstrate VLAN-based network isolation
- Verify subnet configuration using ipconfig
- Test connectivity using ping
- Identify host-based firewall restrictions
- Restore network communication through troubleshooting

---

## Step-by-Step Troubleshooting

### 1. Verified IP Configuration and Connectivity Failure (Client 1)
Client 1 was assigned an IP address in the **192.168.10.0/24** subnet and attempted to ping Client 2 in a different subnet.

![Client 1 ipconfig and ping failure](screenshots/ipconfig_ping_client1(1).png)

---

### 2. Verified IP Configuration and Connectivity Failure (Client 2)
Client 2 was assigned an IP address in the **192.168.20.0/24** subnet and was unable to reach Client 1.

![Client 2 ipconfig and ping failure](screenshots/ipconfig_ping_client2(2).png)

---

### 3. Identified Firewall Blocking ICMP Traffic
After placing both clients on the same VLAN and subnet, connectivity was still unsuccessful.  
Investigation revealed that Windows Defender Firewall was blocking ICMP Echo Requests by default.

The **ICMPv4-In** rule was enabled to allow ping responses.

![Firewall ICMPv4 rule enabled](screenshots/firewall_ipv4(3).png)

---

### 4. Verified Connectivity After Firewall Rule Change (Client 1)
Once the firewall rule was enabled, Client 1 successfully pinged Client 2.

![Successful ping from Client 1](screenshots/ping_success_client1(4).png)

---

### 5. Verified Connectivity After Firewall Rule Change (Client 2)
Client 2 was also able to successfully ping Client 1, confirming bidirectional connectivity.

![Successful ping from Client 2](screenshots/ping_success_client2(5).png)

---

## Results
- VLAN separation prevented communication between different subnets
- Moving both systems to the same VLAN corrected network segmentation
- ICMP traffic remained blocked due to host firewall rules
- Enabling ICMP Echo Request rules restored connectivity
- Successful ping confirmed full communication between clients

---

## Key Skills Demonstrated
- VLAN and subnet isolation concepts
- Static IP configuration
- Network troubleshooting using ipconfig and ping
- Firewall rule identification and modification
- Layered troubleshooting methodology

