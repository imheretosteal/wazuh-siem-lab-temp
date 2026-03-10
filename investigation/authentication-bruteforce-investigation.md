## Authentication Failure Investigation

### Attack Simulation

To simulate suspicious authentication activity, multiple login attempts were performed using incorrect credentials from the Windows endpoint.

This behavior mimics a **password guessing or brute-force attempt**, where an attacker repeatedly tries incorrect passwords to gain access.

![Authentication Attempt](../authentication-attempt.png)

---

### Detection in Wazuh

The Wazuh SIEM detected these authentication failures and generated security events.

The event logs show failed login attempts with the following rule descriptions:

* **Logon Failure – Unknown user or bad password**
* **PAM: User login failed**

These logs confirm that the SIEM successfully detected the simulated authentication failures.

![Authentication Failure Logs](../authentication-logs.png)

---

### Threat Hunting Dashboard Analysis

The Wazuh Threat Hunting dashboard highlights authentication-related security events detected from the monitored endpoint.

The dashboard shows:

* **4 authentication failure events**
* **0 authentication success events**

This indicates multiple failed login attempts were detected but none were successful.

![Authentication Dashboard](../authentication-dashboard.png)

---

### Security Insight

Repeated authentication failures may indicate a **brute-force attack or unauthorized access attempt**.

Monitoring these events helps security teams detect suspicious login behavior and investigate potential security incidents.

