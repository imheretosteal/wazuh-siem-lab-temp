# Attack Simulation – File Activity

To simulate suspicious activity, a monitored directory was created on the Windows system.



Wazuh File Integrity Monitoring (FIM) was configured to track changes in this directory.

A PowerShell script was executed to create multiple files rapidly.


This behavior mimics patterns seen during ransomware attacks, where many files are created or modified within a short period of time.

## Attack Simulations

| Attack Type | Simulation Method | Detection |
|-------------|------------------|----------|
| Brute Force Login | Multiple login attempts | Authentication failure alerts |
| File Activity | PowerShell script creating multiple files | File Integrity Monitoring alerts |
| Registry Changes | System registry modifications | Registry monitoring alerts |
