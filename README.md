# wazuh-siem-lab-temp  

# Wazuh SIEM Home Lab – Suspicious File Activity Detection

## Overview

This project demonstrates how a **Security Information and Event Management (SIEM)** system can detect suspicious file activity using **Wazuh File Integrity Monitoring (FIM)**.

A simulated attack was performed on a Windows endpoint by automatically creating multiple files inside a monitored directory.
The Wazuh SIEM successfully detected this activity and generated security alerts.

This lab demonstrates a basic **SOC investigation workflow** from attack simulation to detection.

---

## Lab Architecture

The SIEM environment consists of the following components:

| Component                 | Description                                       |
| ------------------------- | ------------------------------------------------- |
| Wazuh Manager             | SIEM server running on Ubuntu                     |
| Windows Endpoint          | Monitored system running the Wazuh agent          |
| File Integrity Monitoring | Detects file creation, modification, and deletion |
| PowerShell Script         | Used to simulate suspicious activity              |

---

## Wazuh Installation

The Wazuh SIEM server was installed on an Ubuntu virtual machine.

![Wazuh Installation](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/ba9bd968af582f19588ccec291e4e51676ee2871/wazuh-installation.png)

---

## Attack Simulation

To simulate suspicious behavior, a PowerShell script created multiple files inside a monitored directory:

```
C:\wazuh\wazuh_test
```

This behavior is similar to ransomware activity where many files are created or modified rapidly.

![Attack Simulation](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/attack-simulation-powershell.png)

---

## Detection in Wazuh

After the attack simulation, Wazuh detected multiple file creation events using **File Integrity Monitoring (FIM)**.

### Wazuh Dashboard

![Wazuh Dashboard](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/wazuh-dashboard-overview.png)

### File Creation Detection Logs

![File Creation Logs](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/file-creation-detected.png)

---

## Skills Demonstrated

* SIEM deployment and configuration
* Endpoint monitoring using Wazuh agents
* File Integrity Monitoring (FIM)
* Security event analysis
* Basic SOC investigation workflow
* Attack simulation using PowerShell

---

## Tools Used

* Wazuh SIEM
* Ubuntu Linux
* Windows Endpoint
* PowerShell
* VirtualBox

---

## Project Structure

```
architecture/
attack-simulation/
investigation/
setup-guide/
README.md
```

Each folder contains documentation explaining the setup process, attack simulation, and detection analysis.

---

## Key Takeaway

This lab demonstrates how SIEM platforms like **Wazuh** can detect suspicious file activity in real time.
Such detection capabilities are important for identifying potential ransomware behavior and responding to security incidents.

