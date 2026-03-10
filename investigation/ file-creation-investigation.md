# SOC Investigation – Suspicious File Activity

## Step 1 – Wazuh Server Setup

The Wazuh manager was installed on an Ubuntu virtual machine.

This server collects logs from monitored endpoints.

![Wazuh Installation](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/779dfb63ae3744c4887671c78def449c0f0d6d50/wazuh-installation.png)

---

## Step 2 – Server Network Configuration

The IP address of the Ubuntu server was identified using the `ifconfig` command.

This IP address is used to access the Wazuh dashboard from the browser.

![Ubuntu Server IP](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/ubuntu-ip-config.png)

---

## Step 3 – File Integrity Monitoring Configuration

A monitored directory was created on the Windows endpoint to track suspicious file activity.

C:\wazuh\wazuh_test

The Wazuh agent monitors this directory using File Integrity Monitoring (FIM).  
Any file creation, deletion, or modification inside this directory will generate security events that are sent to the Wazuh SIEM server.
---

## Step 4 – Attack Simulation

To simulate suspicious activity, multiple files were created using PowerShell.



This behavior mimics ransomware activity.

![Attack Simulation](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/attack-simulation-powershell.png))

---

## Step 5 – Detection in Wazuh

After the attack simulation, Wazuh began collecting events from the monitored endpoint.

The SIEM dashboard shows multiple alerts generated from endpoint activity.

### Wazuh Dashboard Overview

![Wazuh Dashboard](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/wazuh-dashboard-overview.png)

### File Creation Events Detected

The File Integrity Monitoring (FIM) module detected the newly created files inside the monitored directory.

Each file creation event appears with the event type **added**, confirming that the SIEM detected the simulated activity.

![File Creation Logs](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/file-creation-detected.png)

## Conclusion

This investigation demonstrates how Wazuh can detect suspicious file activity using File Integrity Monitoring.

Such behavior is commonly associated with ransomware or automated malicious scripts.
