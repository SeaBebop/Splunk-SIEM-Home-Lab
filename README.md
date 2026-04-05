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
-  Detailed test results and Defender behavior → [**analysis.md**](https://github.com/SeaBebop/Splunk-SIEM-Home-Lab/blob/main/analysis.md)

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

## How to Replicate This Lab

1. Install Oracle VM VirtualBox.  

2. Download and install the following operating systems:
   - Windows 10  
   - Windows Server 2022  
   - Ubuntu  

3. Create an account with Splunk Enterprise and follow the official guide to set up the free tier.  

4. Set up each virtual machine in VirtualBox and assign a **static IP address** to each system.  

5. On the Ubuntu machine, install Splunk Enterprise using the official command-line instructions.  

6. On the Windows Server 2022 machine, install the **Splunk Universal Forwarder** and Sysmon with Olaf Hartong configurations. And configure it to send data to the Ubuntu (Splunk) server.  

7. Configure a domain on Windows Server 2022 (Domain Controller) and create a user account for the Windows 10 machine.  

8. Join the Windows 10 machine to the domain and install the **Splunk Universal Forwarder** and Sysmon with Olaf Hartong configurations. Configure it to forward logs to the Ubuntu server.  

9. On the Windows 10 machine, install Atomic Red Team by following the official documentation.  

10. Execute Atomic Red Team tests using the documented commands and monitor the generated telemetry in Splunk.

## Technologies Used
Splunk Enterprise, Sysmon (Olaf Hartong), Atomic Red Team, MITRE ATT&CK, Windows Event Logs, CIM-compliant logging
