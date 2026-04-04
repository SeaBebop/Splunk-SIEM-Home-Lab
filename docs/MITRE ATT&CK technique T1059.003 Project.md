# Lab Setup

##  Atomic Red Team MITRE ATT&CK technique T1059.003 VM Setup

### Virtual Machines Created

Four virtual machines were prepared for this security lab:

| VM Name       | Role                  | Operating System      |
|---------------|-----------------------|-----------------------|
| **Kali**      | N/A                   | Kali Linux            |
| **Splunk**    | SIEM Server           | Ubuntu Server         |
| **DC**        | Domain Controller     | Windows Server 2022   |
| **Win10**     | Client Attacker       | Windows 10            |

### Network Configuration

Each virtual machine has the following network adapters:

- **Adapter 1**: NAT  
  → Used for internet access (updates, downloads, etc.)

- **Adapter 2**: Internal Network (`SIEM-LAB`)  
  → Isolated lab network for communication between all VMs

### Snapshots

**Snapshot taken:**
- **Name**: `02 - Client - Just Before Atomic Team`
- **Name**: `00 - Clean Base Install`
- **Name**: `04 - DC + SplunkForwarder w/ Sysmon -Finalized`
- **Name**: `02 - Splunk Set Up - Finalized`
---
### Description

Built a multi-VM security lab consisting of a Windows Server 2022 Domain Controller, Windows 10 client, and Splunk Enterprise SIEM. Configured domain join, deployed Splunk Universal Forwarders, and installed Sysmon with the Olaf Hartong configuration on both Windows machines for high-fidelity logging. <br> 
Used Atomic Red Team to simulate real-world adversary behaviour, specifically MITRE ATT&CK technique T1059.003 (Command and Scripting Interpreter: Windows Command Shell). Captured the attack activity through Sysmon and built detections in Splunk to identify suspicious cmd.exe execution. <br>
This project demonstrates the full detection engineering lifecycle: safely simulating attacks, ingesting quality endpoint logs, and developing actionable Splunk queries to detect malicious activity. <br>

