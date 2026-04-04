# Atomic Red Team: Threat Simulation and Detection Using Splunk 
This project features splunk detecting malicious activies of a domain joined user in an internal network. All logs are CIM compliant and a dashboard was created.
### Quick Demo

  <img src="assets/Security_Lab_Demo.gif" />

### Red Atomic Team attacks Used
|  Technique ID    | TestNumber| Description                                                                       | 
|------------------|-----------|-----------------------------------------------------------------------------------|
| **T1059.001**    | 1         |  Mimics attacker behavior by spawning cmd.exe with suspicious arguments           |
| **T1059.001**    | 6         | Simulates trojan/downloader activity using encoded PowerShell to execute a payload|
| **T1562.001**    | 1         | Emulates defense evasion by tampering with Windows Defender using PowerShell      |
##  Base VM Setup

### Virtual Machines Created

Four virtual machines were prepared for this security lab:

| VM Name       | Role                  | Operating System      |
|---------------|-----------------------|-----------------------|
| **Splunk**    | SIEM Server           | Ubuntu Server         |
| **DC**        | Domain Controller     | Windows Server 2022   |
| **Win10**     | Client Workstation    | Windows 10            |

### Network Configuration

Each virtual machine has the following network adapters:

- **Adapter 1**: NAT  
  → Used for internet access (updates, downloads, etc.)

- **Adapter 2**: Internal Network (`SIEM-LAB`)  
  → Isolated lab network for communication between all VMs


---

