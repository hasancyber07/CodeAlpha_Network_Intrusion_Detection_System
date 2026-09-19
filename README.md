# Network Intrusion Detection System (NIDS) 🛡️

This repository contains the implementation of a Network Intrusion Detection System (NIDS) using **Snort 3** on Kali Linux, developed as part of the **CodeAlpha Cybersecurity Internship**.

## 📌 Project Overview
The objective of this project is to set up a network-based intrusion detection system, configure custom security rules, and continuously monitor network traffic to detect potential threats and malicious activities in real time.

## 🛠️ Features & Technologies
- **Technology:** Snort 3 (Next-Generation Snort NIDS)
- **Environment:** Kali Linux / Ubuntu
- **Detection Capabilities:**
  - Real-time ICMP Ping sweep / Echo Request detection
  - Nmap Stealth SYN Port Scan identification
  - Suspicious HTTP directory traversal / unauthorized `/admin` request alerts
- **Interface Monitored:** `eth0`

## 🚀 Installation & Setup

1. **Install Snort 3:**
   ```bash
   sudo apt update
   sudo apt install snort -y
Configure Custom Rules:
Add the detection rules from local.rules to your Snort configuration path (/etc/snort/rules/local.rules).

Validate Configuration:

```bash
sudo snort -c /etc/snort/snort.lua -T
```




Run Snort in Live Detection Mode:

```bash
sudo snort -c /etc/snort/snort.lua -R /etc/snort/rules/local.rules -i eth0 -A alert_fast
```

📊 Live Detection Example
When ICMP traffic is detected on the interface, Snort triggers the following real-time alert:


09/19-03:50:36.519724 [**] [1:1000001:1] "[DIQQET] ICMP Ping Trafiki Ashkar Edildi!" [**] [Priority: 0] {ICMP} fe80::1 -> fe80::a3a0:d918:37ff:53f2
Developed during CodeAlpha Cybersecurity Internship.
