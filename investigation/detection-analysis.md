# SOC Investigation – Suspicious File Activity

## Step 1 – Wazuh Server Setup

The Wazuh manager was installed on an Ubuntu virtual machine.

This server collects logs from monitored endpoints.

![Wazuh Installation](../screenshots/wazuh-installation.png)

---

## Step 2 – Windows Agent Connection

The Windows system was registered as an endpoint in the Wazuh manager.

Once connected, the agent began sending security logs.

![Agent Connected](../screenshots/agent-connected.png)

---

## Step 3 – File Integrity Monitoring Configuration

A monitored directory was created to track suspicious file activity.
C:\wazuh\wazuh_test


Wazuh was configured to monitor this directory in real time.

![FIM Config](../screenshots/fim-config.png)

---

## Step 4 – Attack Simulation

To simulate suspicious activity, multiple files were created using PowerShell.



This behavior mimics ransomware activity.

![Attack Simulation](../screenshots/attack-simulation.png)

---

## Step 5 – Detection in Wazuh

After the files were created, Wazuh generated security alerts.

The SIEM dashboard shows multiple file modification events.

![Wazuh Alerts](../screenshots/wazuh-dashboard-alerts.png)

---

## Conclusion

This investigation demonstrates how Wazuh can detect suspicious file activity using File Integrity Monitoring.

Such behavior is commonly associated with ransomware or automated malicious scripts.
