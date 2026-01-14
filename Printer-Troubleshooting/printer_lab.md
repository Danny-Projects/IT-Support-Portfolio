# Printer Troubleshooting Lab — Incorrect TCP/IP Port Simulation

## Overview
This lab simulates a common enterprise IT support scenario where a network printer fails due to an incorrect TCP/IP configuration.  
You diagnose the issue, inspect printer ports, restart the Print Spooler, fix the port, and confirm that the printer returns to a normal state.

---

## Scenario
A user reports they cannot print. A test page appears to send but remains stuck in the queue, and the printer displays an error state.  
Your task is to identify the cause and resolve the issue.

---

## Symptoms
- Print job stuck in queue  
- “Error – Printing”  
- Printer shows **Error** under its status  
- Incorrect TCP/IP port assigned  
- Spooler-related issues  

---

## Tools Used
- Printers & Scanners (Windows Settings)  
- Printer Properties  
- Print Queue  
- services.msc (Print Spooler)  
- TCP/IP Port configuration  

---

# Step-by-Step Troubleshooting

---

## 1. Added a Fake TCP/IP Printer
A fake network printer was manually added using an unreachable IP address to simulate real-world connection failures.

**Screenshot #1 — Add Fake Printer**  
![Screenshot 1 – Add Fake Printer](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/add_fake_printer%20.png)

---

## 2. Print Job Failed / Queue Shows Error  
A test page was printed. The job entered the queue but failed with an error.

**Screenshot #2 — Print Queue Error**  
![Screenshot 2 – Queue Error](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/test_page_error.png)

---

## 3. Restarted the Print Spooler  
To rule out spooler issues, the **Print Spooler** service was restarted through `services.msc`.

**Screenshot #3 — Print Spooler Highlighted**  
![Screenshot 3 – Spooler Highlighted](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/spooler%20.png)

**Screenshot #4 — Restart Option**  
![Screenshot 4 – Spooler Restart](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/spooler_restart.png)

---

## 4. Inspected TCP/IP Port Configuration  
Inside **Printer Properties → Ports**, the printer was mapped to a TCP/IP address that does not exist, causing all print jobs to fail.

**Screenshot #5 — Printer Properties**  
![Screenshot 5 – Printer Properties[]()](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/printer_properties%20.png)

**Screenshot #6 — Ports Tab with Incorrect TCP/IP Port Selected & Configure Port Dialog Showing Fake IP**  
![Screenshot 6 – Ports Tab/Configure Port Fake IP](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/ports_fake_ip.png)

**Root Cause:**  
The printer was assigned a TCP/IP port with an unreachable or invalid IP address.

---

## 5. Fixed the Printer  
To resolve the issue, the printer was switched to the **FILE:** port, which simulates a valid working configuration.

**Screenshot #7 — Port Updated to FILE:**  
![Screenshot 7 – Port Fixed](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/port_fixed.png)

---

## 6. Successful Test Page  
After correcting the port, a test page was printed.  
Windows displayed a **“Save Print Output As”** dialog, indicating the job was successfully processed.

**Screenshot #8 — Test Page Success (Save Output Dialog)**  
![Screenshot 8 – Test Page Success](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/test_page_success.png)

---

## 7. Printer Status Normalized  
After clearing the queue and restarting the spooler again, the printer showed an **Idle** state with no errors.

**Screenshot #9 — Printer Status: Idle**  
![Screenshot 9 – Printer Ready](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Printer-Troubleshooting/screenshots/printer_ready.png)

---

# Conclusion
This lab demonstrates professional printer troubleshooting techniques used daily in IT support:

- Diagnosing print queue issues  
- Restarting the Print Spooler  
- Inspecting and correcting TCP/IP printer ports  
- Resolving “Error – Printing” conditions  
- Verifying successful print job processing  
- Confirming printer returns to an operational state  
