# Splunk SIEM Home Lab – Detection Engineering with Atomic Red Team

This project demonstrates practical **detection engineering** in a Windows Active Directory environment. I built a small security lab to simulate real adversary behavior using Atomic Red Team and detect it using Splunk SIEM and Sysmon.

## Lab Architecture
- **Windows Server 2022** – Domain Controller + Splunk Universal Forwarder + Sysmon (Olaf Hartong config)  
- **Windows 10** – Domain-joined client + Splunk Universal Forwarder + Sysmon  
- **Splunk Enterprise** – Central SIEM with custom indexes and CIM-compliant parsing  

## Techniques Simulated (MITRE ATT&CK)
- [**T1059.001 Test Number 1**](./assets/T1059.001%231.gif) – Command and Scripting Interpreter (Windows Command Shell)  
-  [**T1059.001 Test Number 6**](./assets/T1059.001%236.gif) – PowerShell Execution (basic and download/execute variants)  
-   [**T1562.001 Test Number 1**](./assets/T1562.001%231.gif) – Impair Defenses (attempt to disable Windows Defender)
- [**Detailed Demo Here**](https://github.com/SeaBebop/Splunk-SIEM-Home-Lab/blob/main/analysis.md)

## Key Achievements
- Configured domain environment with proper logging infrastructure  
- Ingested high-fidelity Sysmon logs into Splunk  
- Built and tuned detections for suspicious execution techniques  
- Created a custom dashboard to visualize attack activity  
- Documented troubleshooting process (time sync, Defender alerts, domain join issues, etc.)  

## Demo (Example)
<div style="display: flex; justify-content: center; gap: 1rem;">
  <img src="assets/Security_Lab_Demo.gif" alt="Security Lab Demo" style="max-width: 100%; height: auto;" />
</div>

## Dashboard
<div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;">
  <img src="assets/Simple_Dashboard_cmd.gif" alt="Dashboard Command" style="max-width: 48%; height: auto;" />
</div>

## Challenges & Lessons Learned
- Overcame time synchronization issues between Windows and Linux  
- Handled Windows Defender false positives during Atomic Red Team installation  
- Fixed inconsistent sourcetypes and `inputs.conf` parsing  
- Resolved domain join DNS and network profile problems  
- [**Detailed Analysis Here**](https://github.com/SeaBebop/Splunk-SIEM-Home-Lab/blob/main/lessons.md)
## Technologies Used
Splunk Enterprise, Sysmon (Olaf Hartong), Atomic Red Team, MITRE ATT&CK, Windows Event Logs, CIM-compliant logging
