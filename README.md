<img width="1536" height="1024" alt="HUBSPOKE" src="https://github.com/user-attachments/assets/3f2605dc-d9fa-4aec-9088-13a761afa41a" /># Azure Hub-Spoke Network Architecture with Security, Grafana Monitoring & Smart Alerts 🚀

## Architecture Diagram
![Uploading HUBSPOKE.png…]()

## Project Overview

This project demonstrates a secure and scalable **Azure Hub-Spoke Network Architecture** designed using Microsoft Azure services with centralized security, real-time monitoring, dashboards, and intelligent alerting.

It simulates an enterprise-grade cloud environment focused on **network segmentation, traffic inspection, private access, observability, and proactive incident response**.

---

## Architecture Highlights

✅ Hub-Spoke VNet topology for centralized connectivity  
✅ Route Tables (UDRs) to route spoke traffic through Azure Firewall  
✅ Azure Firewall for traffic filtering and threat protection  
✅ Azure Bastion for secure VM access without public IP exposure  
✅ Network Security Groups (NSGs) for subnet-level security control  
✅ NGINX Frontend deployed on Linux VM  
✅ Tomcat Backend deployed on Linux VM  
✅ Azure Monitor Agent installed on Linux VMs  
✅ Azure Monitor + Log Analytics integration  
✅ Grafana dashboards for real-time monitoring  

---

## Smart Alerting Configured

🚨 Email alert triggered when CPU usage crosses the configured threshold during spike testing  

🔥 Email alert triggered when Azure Firewall deny rules detect blocked traffic  

📩 Automated notifications improve incident response time and operational awareness  

---

## Monitoring & Dashboards

📊 Azure Monitor + Log Analytics Workspace  

📈 Grafana dashboards for:

- CPU Usage  
- Memory Utilization  
- VM Health  
- Network Trends  
- Resource Performance  

📌 Firewall logs, denied traffic insights, and security analytics  

📉 End-to-end VM, network, and application performance monitoring  

---




```markdown
![Architecture Diagram](images/architecture.png)
