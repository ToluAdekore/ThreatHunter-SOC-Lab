🔍 SOC Threat Hunting Lab  

🚨 Project Overview  
The SOC Threat Hunting Lab is a hands-on cybersecurity project designed to simulate real-world SOC operations using Splunk. This lab focuses on log analysis, threat detection, and incident response, providing practical experience in security monitoring, investigating cyber threats, and building SIEM dashboards.  

---

🛠️ Setup Instructions  

1️⃣ Install Splunk Free  
- Download [Splunk Free](https://www.splunk.com/en_us/download/splunk-enterprise.html)  
- Install on Windows/Linux  
- Start Splunk Web UI (`http://localhost:8000`)  

2️⃣ Ingest Security Logs  
- Windows Event Logs (`Security.evtx`, `Sysmon logs`)  
- Firewall/IDS Logs (Suricata, Zeek)  
- Sample datasets from Blue Team Labs, Security Onion, or Splunk Attack Range 

3️⃣ Run SOC Threat Hunting Queries  
🚨 Brute Force Login Detection 
```spl
index=windows EventCode=4625 
| stats count by Account_Name, IpAddress 
| where count > 5
