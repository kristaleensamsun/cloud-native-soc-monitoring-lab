## Project Status
Current Phase:
- Azure Infrastructure Deployment

Completed:
- Azure subscription
- Resource planning
- Cybersecurity architecture design


In Progress:
- Windows VM deployment
- Linux VM deployment
- Network segmentation

 
Planned:
- Microsoft Sentinel
- Log Analytics Workspace
- Entra ID
- Threat Detection Rules
- MITRE ATT&CK Mapping
----
# Cloud-Native Cybersecurity Monitoring Lab
This project documents my beginner-friendly cybersecurity home lab designed to simulate a small Security Operations Center (SOC) environment.

Building a Mini SOC Environment Using Azure, Microsoft Sentinel, and Security Analytics

---

## Project Objective
The goal of this project is to build and explain a realistic cybersecurity monitoring environment that demonstrates how security events are generated, collected, analyzed, and investigated.

This lab is designed for **learning** and **demonstration purposes** only.

---

## Key Components

- **Azure Subscription** - Cloud environment for hosting lab resource
- **Resource Group** - Logical container for all lab resources
- **Virtual Network** - Isolated network for lab systems
- **Windows VM** - Generates Windows event logs and authentication activity
- **Linux VM** - Generates Linux authentication and syslog activity
- **Log Analytics Workspace** - Centralized log storage and query platform
- **Microsoft Sentinel** - Cloud-native SIEM for monitoring and investigation
- **Microsoft Entra ID** - Identity and access management concepts
- **Network Security Group** - Controls inbound and outbound traffic

---
## Architecture


                 ┌──────────────────────────┐
                 │    Azure Subscription    │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │      Resource Group      │
                 │       rg-cyberlab        │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │   Azure Virtual Network  │
                 │      10.10.0.0/16        │
                 └──────┬────────────┬──────┘
                        │            │
                        ▼            ▼
                 ┌────────────┐ ┌───────────┐
                 │ Windows VM │ │ Linux VM  │
                 │ win-lab01  │ │ ubuntu01  │
                 └──────┬─────┘ └─────┬─────┘
                        │             │   
                        │             │   Security Logs
                        ▼             ▼
                 ┌──────────────────────────┐
                 │ Log Analytics Workspace  │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │   Microsoft Sentinel     │
                 │ Detection & Investigation│
                 └──────────────────────────┘

