# Incident Response Handbook
This Handbook provides guidelines for IT adminsitrators in case of a Cyber Incident. This is a **WORK IN PROGRESS, so please continuously follow it to stay updated**.   
1. [Communication with Malicious IP address](#communication-with-malicious-ip-address)


---
# Communication with malicious IP address

### **1. Isolate the Affected System**
- **Disconnect from the Network** : Disconnect both wired and wireless network to prevent further infection.
- **Quanrantine** the system using VLAN, if disconnection is not possible.

### **2. Preserve Evidence**
- **Capture Network Logs** : Collect relevant firewall, IDS/IPS, router and switch logs.
    - Windows Network Capture Tutorial [[video]]()
    - Linux Windows Capture Tutorial [[video]]()
- **Memory Dump** : Take a memory dump of the affected system for forensic analysis.
    - Windows Memory Dump Capture Tutorial [[video]]()
    - Linux Memory Dump Capture Tutorial [[video]]()
- **Disk Image** : Create forensic image of the Disk.
    - Windows Disk Imaging Tutorial [[video]]()
    - Linux Disk Imaging Tutorial [[video]]()

### **3. Investigate the Incident**
- **Identify and investigate the Source of Infection** : Determine source of infection (e.g., phishing email [[video]](), malicious download [[video]](), malicious website browsing [[video]]() etc).
- **Check for Lateral Movement**: Investigate other systems in the network for signs of compromise or communication with the malicious IP 
    - using wireshark [[video]]()
    - using network logs [[video]]()
- **Review Infected PC Logs**: **<span class="warning">DO NOT TAMPER ORIGINAL EVIDENCE. </span> Check logs from syslog server**. Examine logs of concerned PC from syslog server (e.g., Windows Event Logs, application logs) for suspicious activity[[video]]().

### **4. Contain Threat**
- **Block Malicious IPs**: Update firewalls, IDS/IPS, and endpoint protection tools to block the malicious IP address across the network.
    - IP blocking on Firewall [[video]]()
    - IP blocking on Endpoint [[video]]()
- **Malware Scanning on Network PCs**: **<span class="warning">DO NOT TAMPER ORIGINAL EVIDENCE. </span>**. Run antivirus scan on **other PCs** of the same network, to rule out lateral movement.

### **5. Preventive Measures**
- **Run Windows Update**: 
- **Update user installed softwars**: Identify and patch any vulnerabilities that may have been exploited.
- **Reset Credentials**: **<span class="warning">assume that all credentials saved on infected pc, browser have been compromised </span>**. Use a differnt PC to login to those accounts and change their passwords.
- **Document Security**: If any **CLASSIFIED DOCUMENT** was saved on infected PC, assume they have been leaked and take preventive measures.

### **6. Recover and Restore**
- **Resumption of Business**: Until the company disposes off investigation, take a new PC, run a anti-malware scan on the backup, restore it and resume your daily routine. 
- **Post investigation** : On completion of investigation, ensure **</span class="warning">FORENSIC WIPING</span>** of the hard disk, reinstall OS from **CLEAN INSTALLATION MEDIA** and resume your routine.
- **Monitor for Recurrence**: Closely monitor the system and network for any signs of re-infection or unusual activity.

### **7. Post-Incident Actions**
- **Conduct a Root Cause Analysis (RCA)**: Identify user actions, unsafe browsing, not adhering to standard operating procedures and network misconfiguration to identify ROOT CAUSE. **IDENTIFY GAPS IN YOUR SECURITY POSTURE**.
- **Update Policies and Procedures**: Strengthen security policies, such as email filtering, endpoint protection, and network monitoring.
- **Train Employees**: **<span class="emphasize">EDUCATE USERS</span>** on phishing and other attack vectors to reduce likelihood of future incidents.
- **Document the Incident**: Record all actions taken, findings, and lessons learned for future reference and compliance purposes.
- **User awareness** : Inform other users on the same network, aboutthe incident, and tell them to look out for signs of suspicious activity. 

---


---
<style>
    .warning{
        color: red;
        font-family: "Arial", "sans-serif";
        font-size: 18px;
        }
    .emphasize{
        color: green;
        font-family: "Arial", "sans-serif";
        font-size: 18px;
        }
    </style>