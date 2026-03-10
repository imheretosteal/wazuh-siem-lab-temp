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
## Step 3 – Attack Script Used for Simulation

To simulate suspicious activity, a PowerShell command was executed on the Windows endpoint to automatically generate multiple files inside the monitored directory `C:\wazuh\wazuh_test`.

The command created several files rapidly inside the folder. This type of behavior can be used to test how security monitoring systems detect abnormal file activity.

The following screenshot shows the PowerShell command used to generate the files.

![Attack Simulation](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/attack-simulation-powershell.png)

---

## Step 4 – Suspicious File Activity Generated

After executing the script, multiple files were created inside the monitored directory `C:\wazuh\wazuh_test`.

Files such as `file1.txt`, `file2.txt`, up to `file20.txt` appeared in the folder, demonstrating how quickly automated scripts can generate large numbers of files.

Since this directory is monitored by **Wazuh File Integrity Monitoring (FIM)**, each file creation event is logged and sent to the Wazuh SIEM server for analysis.

The screenshot below shows the files created inside the monitored directory.

![Created Test Files](https://github.com/imheretosteal/wazuh-siem-lab-temp/blob/5cbbe173437cda26c9b8e506bc61bb9ef13b5f01/created-test-files.png)


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
