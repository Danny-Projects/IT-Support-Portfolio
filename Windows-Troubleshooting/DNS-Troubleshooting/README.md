# DNS Troubleshooting Lab

## Scenario
The user reports that they cannot access any websites. They receive DNS-related browser errors such as **DNS_PROBE_FINISHED_NXDOMAIN** or “This site can’t be reached.”

This lab demonstrates how to diagnose and fix DNS resolution issues in Windows.

---

## Symptoms
- Cannot load websites  
- Internet icon may show “Connected”  
- Browser errors referencing DNS  
- `nslookup` fails  
- Incorrect or missing DNS server settings  

---

## Tools Used
- Command Prompt  
- Network Adapter Settings  
- DNS cache tools (`ipconfig /flushdns`)  
- `nslookup` for DNS testing  

---

## Step-by-Step Troubleshooting

### Step 1 — Confirm DNS Failure  
Check whether the system can resolve domain names.

### Step 2 — Check Local DNS Cache  
Use `ipconfig /displaydns` to examine cached records.

### Step 3 — Test Connectivity Without DNS  
Ping by IP to confirm the internet connection is working.

### Step 4 — Flush the DNS Cache  
Use `ipconfig /flushdns` to clear stale or corrupted entries.

### Step 5 — Release/Renew IP  
Use `ipconfig /release` and `ipconfig /renew` to refresh DHCP settings.

### Step 6 — Change DNS Servers  
Test with a known-good DNS server like Google (8.8.8.8) or Cloudflare (1.1.1.1).

### Step 7 — Validate with nslookup  
Ensure DNS resolution works for domains.

### Step 8 — Confirm Browsing Works Again  
Verify that websites load properly once DNS is corrected.

---

## Screenshots
A minimum of 5 screenshots will be included:

1. Browser DNS error  
2. `nslookup` failure  
3. `ipconfig /flushdns` + `ipconfig /release`  
4. DNS server settings changed  
5. `nslookup` success + webpage loading

---

## Root Cause
Incorrect or unreachable DNS server caused name resolution failure.

---

## Resolution Summary
✔ Confirmed DNS failure  
✔ Flushed DNS cache  
✔ Renewed IP configuration  
✔ Updated DNS servers  
✔ Verified DNS resolution via nslookup  
✔ Confirmed restored web access  

---
