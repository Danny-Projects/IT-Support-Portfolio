# Networking Basics Troubleshooting Lab

## **Scenario**
A user reports that they cannot access the internet reliably.  
To diagnose and resolve the issue, I performed a series of core networking tests including IP configuration review, ping tests, route tracing, and adapter reconfiguration.

This lab demonstrates essential Tier 1 IT troubleshooting skills.

---

# 1. **Check Local Network Configuration**

To understand the workstation's current network settings, I ran:
```cmd
ipconfig /all
```

This reveals IP address information, DNS settings, DHCP status, MAC address, and adapter properties.

### **Screenshot 1 — ipconfig command**
![ipconfig_cmd](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/ipconfig_all.png)

### **Screenshot 2 — Wi-Fi Adapter Details**
*(Sensitive fields redacted for privacy)*
![ipconfig_adapter](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/ip_wifi.png)

---

# 2️. **Test Network Connectivity with Ping**

Ping tests help identify where connectivity breaks along the network path.

---

## **A. Ping Localhost (127.0.0.1)**
Verifies that TCP/IP is functioning correctly on the local device.
```cmd
ping 127.0.0.1
```

### **Screenshot 3**
![ping_localhost](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/ping_localhost%20.png)

---

## **B. Ping Default Gateway**
Tests whether the device can reach the local router.
```cmd
ping <default-gateway-ip>
```

### **Screenshot 4**
![ping_gateway](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/ip_gateway.png)

---

## **C. Ping External IP (Google DNS 8.8.8.8)**
Verifies WAN connectivity without involving DNS.

```cmd
ping 8.8.8.8
````

### **Screenshot 5**
![ping_external](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/ping_external_ip.png)

---

## **D. Ping a Domain Name (google.com)**
Confirms DNS resolution in addition to connectivity.
```cmd
ping google.com
```

### **Screenshot 6**
![ping_domain](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/ping_domain.png)

---

# 3️. **Trace Routing Path with tracert**

`tracert` shows the path packets take across the internet and helps identify where connection issues occur.
```cmd
tracert google.com
```

### **Screenshot 7**
![tracert](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/tracert.png)

---

# 4️. **Disable and Re-enable Network Adapter**

Resetting the adapter is a common help-desk fix that reinitializes network hardware and resets DHCP/DNS bindings.

### Steps:
- Open **ncpa.cpl**
- Right-click the Wi-Fi adapter → **Disable**
- Wait a few seconds
- Right-click → **Enable**

### **Screenshot 8 — Adapter Disabled**
![adapter_disabled](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/adapter_disabled.png)

### **Screenshot 9 — Adapter Enabled**
![adapter_enabled](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/adapter_enabled.png)

---

# 5️. **Review IPv4 Properties**

Verifying adapter configuration ensures DNS is set correctly and DHCP is used when intended.

### Checked:
- IPv4 set to **Obtain IP automatically**
- DNS set to **Obtain DNS automatically**

### **Screenshot 10 — IPv4 Properties**
![ipv4_properties](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Networking%20/screenshots/ipv4_properties.png)

---

#  **Conclusion**

This Networking Basics Lab demonstrates essential connectivity troubleshooting skills used in real IT support roles:

- Collecting network configuration  
- Testing local vs. gateway vs. WAN connectivity  
- Diagnosing DNS vs. IP routing issues  
- Using ping and tracert effectively  
- Resetting network adapters  
- Verifying IPv4 and DNS settings  



