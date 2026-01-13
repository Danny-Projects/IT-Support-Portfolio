# DNS Troubleshooting Lab

## **Scenario**
A user reports that they cannot access websites.  
Browser errors appear, suggesting DNS resolution is failing.

This lab demonstrates how to diagnose and resolve DNS issues using Windows tools such as nslookup, ipconfig, and adapter settings.

---

## **1. Reproducing the DNS Issue**

I manually configured invalid DNS servers to simulate a DNS outage.

**Browser Error:**  
The browser could not load the website and showed a DNS-related failure.

**Screenshot 1:**  
![DNS_Error](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/DNS-Troubleshooting/screenshots/dns_google.png?raw=true)

---

## **2. DNS Diagnostic Testing**

### **nslookup Test**
I used `nslookup` to confirm DNS resolution was failing.

**Screenshot 2:**  
![nslookup_failure](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/DNS-Troubleshooting/screenshots/dns_nslookup_failure.png?raw=true)

---

## **3. Flushing DNS Cache**

To remove potentially corrupted or stale cached DNS entries, I ran:
```cmd
ipconfig /flushdns
```

**Screenshot 3:**  
![flushdns](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/DNS-Troubleshooting/screenshots/flushdns.png?raw=true)

---

## **4. Releasing & Renewing IP Address**

To force a new DHCP lease and refresh network configuration, I ran:
```cmd
ipconfig /release
ipconfig /renew
```

**Screenshot 4 (Release):**  
![release](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/DNS-Troubleshooting/screenshots/release.png?raw=true)

**Screenshot 5 (Renew):**  
![renew](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/DNS-Troubleshooting/screenshots/renew.png?raw=true)

---

## **5. Correcting DNS Settings**

I reverted DNS configuration to a valid setting (Automatic/DHCP or Google DNS).

**Screenshot 6:**  
![dns_settings](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/DNS-Troubleshooting/screenshots/dns_automatic.png?raw=true)

---

## **6. Validating DNS Resolution**

### **nslookup Test (Success)**
After correcting DNS, resolution worked properly and returned valid IP addresses.

**Screenshot 7:**  
![browser_success](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/DNS-Troubleshooting/screenshots/google_working%20.png?raw=true)

---

#  **Conclusion**

This lab simulates a real-world help desk ticket where a user cannot access websites due to DNS configuration issues.

In this exercise, I:

- Simulated a DNS outage  
- Confirmed failure with `nslookup`  
- Flushed DNS cache  
- Renewed DHCP lease  
- Repaired DNS settings  
- Validated proper DNS resolution  
- Confirmed browser access restored  

This demonstrates practical, hands-on troubleshooting skills with Windows networking tools.
