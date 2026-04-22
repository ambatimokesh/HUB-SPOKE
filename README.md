🚀 Azure Hub-Spoke Network Architecture with Security, Monitoring & Smart Alerts
📌 Project Overview

This project demonstrates the implementation of a secure, scalable Azure Hub-Spoke Architecture with:

🔐 Centralized Security using Azure Firewall
🌐 Network Isolation using VNets & Subnets
🖥️ Linux VM Deployment (NGINX & Tomcat)
🔎 Monitoring with Azure Monitor & Log Analytics
📊 Visualization using Grafana Dashboards
🚨 Smart Alerts for CPU & Firewall events
🏗️ Architecture
🔹 Hub-Spoke Model
Hub VNet → Centralized services (Firewall, Bastion)
Spoke VNets → Application workloads
📌 Components
Hub VNet (10.0.0.0/16)
Spoke1 VNet (10.1.0.0/16)
Spoke2 VNet (10.2.0.0/16)
Azure Firewall (Central security control)
Azure Bastion (Secure VM access)
Linux VMs (NGINX & Tomcat)
⚙️ Implementation Steps
1️⃣ Resource Group
Created: RG-HubSpoke-Project
Region: Central India
2️⃣ Virtual Networks & Subnets
Hub VNet
Address Space: 10.0.0.0/16
Subnets:
AzureFirewallSubnet → 10.0.0.0/26
AzureBastionSubnet → 10.0.1.0/24
Spoke VNets
Spoke1 → 10.1.0.0/16
Spoke2 → 10.2.0.0/16
3️⃣ VNet Peering
Hub ↔ Spoke1
Hub ↔ Spoke2
Spoke1 ↔ Spoke2

Enabled:

✔ VNet Access
✔ Forwarded Traffic
4️⃣ Virtual Machines
VM	Purpose	Software
Spoke1	Web Server	NGINX
Spoke2	App Server	Tomcat
5️⃣ Security Configuration
🔥 Azure Firewall
SKU: Standard
Centralized traffic control
Rules Implemented:
Allow HTTP (Port 80)
Allow HTTPS (Port 443)
Internal communication rules
Proxy (8080) communication
Reverse traffic rules
DNAT rule for external access
🛡️ Network Security Groups (NSG)
Spoke1 NSG
Allow:
HTTP (80)
SSH (22)
Outbound:
Port 8080
Spoke2 NSG
Allow:
SSH (22)
Port 8080
6️⃣ Azure Bastion
Secure SSH access without public IP
Connected to Hub VNet
7️⃣ Software Installation
Spoke1 (NGINX)
sudo apt update
sudo apt install nginx -y
Spoke2 (Tomcat)
sudo apt update
sudo apt install default-jdk -y
sudo apt install tomcat10
8️⃣ Connectivity Testing
SSH via Bastion
Verified ports:
22 (SSH)
80 (NGINX)
8080 (Tomcat)
Test Command:
curl http://10.2.1.4:8080
🌐 Final Output

Access application via Firewall Public IP:

http://<Firewall-Public-IP>
📊 Monitoring & Logging
🔹 Log Analytics Workspace
Name: LAW-HubSpoke
🔹 Azure Monitor Agent (AMA)

Enabled on:

Spoke1 VM
Spoke2 VM

Collects:

CPU Metrics
Memory Usage
Syslogs
VM Health
🔥 Firewall Logs

Enabled:

Network Rule Logs
Application Rule Logs
DNS Proxy Logs
🚨 Alerts Configuration
CPU Alert
Trigger: CPU > 50%
Action: Email Notification
Firewall Alert
Trigger: Deny Traffic Logs
Query:
AzureDiagnostics
| where Category == "AzureFirewallNetworkRule"
| where msg_s contains "Deny"
📈 Metrics & Dashboard
CPU Usage
Memory Usage
Network Metrics
Grafana Dashboard
Integrated with Azure Monitor
Visualized CPU metrics
🧪 Load Testing

Generate CPU load:

yes > /dev/null &

Stop load:

killall bash
📜 Sample Log Queries
Heartbeat
Heartbeat | take 5
Firewall Logs
AzureDiagnostics
| where Category == "AzureFirewallNetworkRule"
| take 20
Deny Count
AzureDiagnostics
| where Category == "AzureFirewallNetworkRule"
| where msg_s contains "Deny"
| summarize Count = count()
🎯 Key Learnings
Hub-Spoke architecture design in Azure
Secure communication using Azure Firewall
VM-to-VM connectivity without public exposure
Real-time monitoring & alerting
Log analysis using KQL
Dashboard visualization using Grafana
📌 Future Improvements
Add Load Balancer
Implement WAF (Web Application Firewall)
CI/CD integration
Auto-scaling setup
🙌 Conclusion

This project provides a complete real-world cloud architecture covering:

Networking
Security
Monitoring
Automation readiness
