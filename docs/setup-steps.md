# Lab Setup Guide

##  Base VM Setup

### Virtual Machines Created

Four virtual machines were prepared for this security lab:

| VM Name       | Role                  | Operating System      |
|---------------|-----------------------|-----------------------|
| **Kali**      | Attacker              | Kali Linux            |
| **Splunk**    | SIEM Server           | Ubuntu Server         |
| **DC**        | Domain Controller     | Windows Server 2022   |
| **Win10**     | Client Workstation    | Windows 10            |

### Network Configuration

Each virtual machine has the following network adapters:

- **Adapter 1**: NAT  
  → Used for internet access (updates, downloads, etc.)

- **Adapter 2**: Internal Network (`SIEM-LAB`)  
  → Isolated lab network for communication between all VMs

### Snapshots

**Snapshot taken:**
- **Name**: `00 - Clean Base Install`
- **Description**: All VMs are freshly installed, fully updated, and configured with dual network adapters (NAT + Internal Network `SIEM-LAB`). No additional software or roles installed yet.

---
