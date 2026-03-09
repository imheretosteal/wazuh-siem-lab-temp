# Wazuh Installation and Setup

To build the monitoring environment, Wazuh was installed on an Ubuntu virtual machine.

Installation command:
curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh

sudo bash wazuh-install.sh -a 

## Lab Environment

| Component | Technology | Purpose |
|----------|------------|---------|
| SIEM | Wazuh | Collects and analyzes security logs |
| Server OS | Ubuntu | Hosts the Wazuh manager |
| Endpoint | Windows | Generates system activity logs |
| Virtualization | VirtualBox | Runs the virtual machines |
| Monitoring | File Integrity Monitoring | Detects file changes |
