Digital Forensic Investigation: The Stolen Szechuan Sauce
🔍 Overview
A digital forensic investigation into a simulated data breach where a proprietary Szechuan sauce recipe was stolen from a corporate network.

📋 Case Summary
Incident	Data Breach / IP Theft
Target	Szechuan Sauce Recipe
Initial Access	RDP Brute Force
Malware	Trojan (coreupdater.exe)
Breach Confirmed	Yes
Recipe Stolen	Yes - 2020-09-19 22:35:43 UTC
🖥️ Systems Involved
System	OS	Role
citadeldc01	Windows Server 2012 R2	Domain Controller (10.42.85.10)
DESKTOP-SDN1RPT	Windows	Initial RDP Target
🚨 Attack Timeline
Date (UTC)	Event
2020-09-18	RDP Brute Force from 194.61.24.102
2020-09-19 02:36	RDP Access Gained
2020-09-19 03:56:37	Malware (coreupdater.exe) First Seen
2020-09-19 04:12:18	Persistence Installed (Run Key)
2020-09-19 22:35:43	Szechuan Sauce Recipe Stolen
Ongoing	C2 Communication Active
🦠 Malware Analysis: coreupdater.exe
Attribute	Finding
Type	Trojan (Meterpreter-derived)
Delivery	GET /coreupdater.exe from 194.61.24.102
Final Path	C:\Windows\System32\coreupdater.exe
Persistence	HKLM\Run registry key
C2 Server	203.78.103.109 (5/94 VT detections)
Capabilities
✅ Code Injection (spoolsv.exe, explorer.exe)

✅ Process Manipulation

✅ Persistence

✅ C2 Communication

✅ Data Exfiltration

✅ Remote Control

🌐 Adversary Infrastructure
IP Address	Role	Country
194.61.24.102	Attack Source / Payload Host	-
203.78.103.109	C2 Server	Thailand
📁 Files Stolen/Accessed
File	Time (UTC)	Status
Szechuan Sauce Recipe	22:35:43	✅ STOLEN
Secret Documents (multiple)	2020-09-19	✅ Accessed
🖧 Network Layout
text
[Internet] → 194.61.24.102 (Attacker)
    ↓
[Firewall]
    ↓
10.42.85.0/24 Network
    ├── DC: 10.42.85.10 (citadeldc01)
    └── DESKTOP-SDN1RPT (Initial RDP Target)
🔬 Key Findings
Finding	Status
Breach Confirmed	✅
RDP Brute Force Initial Vector	✅
Malware Deployed	✅
Persistence Established	✅
Process Injection Confirmed	✅
Active C2 Communication	✅
Recipe Stolen	✅
Lateral Movement to DC	✅
🛡️ Critical Recommendations
Priority	Action
🔴	Block external RDP access immediately
🔴	Require VPN for all remote access
🔴	Enforce Multi-Factor Authentication (MFA)
🟠	Implement network segmentation
🟠	Deploy EDR solution
🟡	Enable account lockout policies
📊 Tools Used
RegRipper - Registry analysis

Volatility - Memory analysis (pstree, malfind, netscan)

Wireshark - PCAP analysis

VirusTotal - IP reputation

👨‍💻 Investigator
Digital Forensic Analyst
DFIR | Memory Forensics | Network Analysis
