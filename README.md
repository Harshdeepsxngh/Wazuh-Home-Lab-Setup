🛡️ Wazuh SIEM Home Lab & Attack Simulation

📝 Objective

The goal of this project is to set up a local Security Information and Event Management (SIEM) environment using Wazuh to monitor a Windows endpoint. This lab focuses on real-time log analysis, network troubleshooting, and simulating cyber attacks to test detection capabilities.

🏗️ Architecture & Environment

SIEM Manager: Ubuntu Desktop (Bare-metal deployment to optimize RAM/hardware resources)

Target Endpoint (Agent): Windows 10 Pro (Dell Laptop)

Network: Local Wi-Fi Network

🛠️ Tools & Technologies Used

Wazuh SIEM: Agent deployment, log aggregation, and security monitoring.

Nmap: Network reconnaissance and port scanning.

Windows Event Viewer: Native OS logging (Event ID 4625 for failed logins).

Command Prompt/PowerShell: System configuration and disk health checks (CHKDSK).

🚀 Key Learnings & Troubleshooting

Resource Optimization: Initially planned a VM-based Kali Linux setup but pivoted to a bare-metal Ubuntu setup to bypass hardware-reserved GPU memory limitations, ensuring smooth SIEM performance.

Network Diagnostics: Successfully troubleshooted agent registration failures by diagnosing DHCP IP changes, routing issues (Destination host unreachable), and fixing PowerShell deployment scripts.

Hardware Health Detection: Discovered and diagnosed physical hardware degradation (Bad Blocks - Event ID 7) on the target Windows machine entirely through Wazuh's continuous log analysis, prompting proactive disk repair (chkdsk /f /r).

⚔️ Attack Simulations & Detections

1. Network Reconnaissance (Nmap)

Performed aggressive port scanning from the Ubuntu host to the Windows endpoint to identify open ports (e.g., Port 5357/wsdapi).

(Add your Nmap terminal screenshot here)
![Nmap Scan](link-to-your-nmap-image.png)

2. Brute-Force Authentication Attack

Simulated a manual brute-force attack on the Windows lock screen to trigger authentication alerts. Wazuh successfully ingested Windows Event logs and flagged the multiple failed login attempts.

(Add your Wazuh Failed Login Alert screenshot here)
![Failed Login Alert](link-to-your-wazuh-alert-image.png)

3. System Integrity & Anomaly Detection

Wazuh's Rootcheck module successfully detected hidden content and NTFS Alternate Data Streams on the target machine, highlighting advanced anomaly detection capabilities.

(Add your Bad Block / Event ID 7 screenshot here)
![System Event Logs](link-to-your-system-logs-image.png)

This project demonstrates hands-on experience with endpoint security monitoring, log analysis, and network troubleshooting in a realistic home lab environment.
