## 📌 Overview
This repository documents a hands-on **Security Operations Centre (SOC) simulation** designed around a **segmented healthcare network** handling sensitive patient data.  
The lab demonstrates how network misconfigurations, insufficient monitoring, and weak segmentation can expose critical systems — and how centralized visibility, detection, and response can significantly improve security posture.

The project mirrors real-world SOC workflows by combining **network design, attack simulation, SIEM monitoring, traffic analysis, and active response** in a controlled environment.

---

## 🧠 Lab Concept
Healthcare organizations are prime targets for cyberattacks due to the value of Electronic Health Records (EHRs) and the stringent regulatory requirements.  
This lab simulates a healthcare technology environment with:

- A **DMZ-hosted Ubuntu EHR server**
- Internal SOC and analyst systems
- Centralized security enforcement and monitoring

Common attacker techniques, such as **network reconnaissance** and **SSH brute-force attempts**, are simulated to evaluate the effectiveness of detection, correlation, and response across segmented network zones.

---

## 🎯 Objectives
- Design and deploy a **segmented WAN / LAN / DMZ architecture**
- Identify weaknesses caused by **overly permissive firewall rules**
- Simulate real-world attack techniques
- Detect malicious activity using **SIEM and packet analysis**
- Demonstrate **automated incident response**
- Apply remediation to improve security posture

---

## 🛠 Tools & Technologies Used
| Category | Tools |
|-------|------|
| Network & Firewall | pfSense |
| SIEM / SOC Platform | Wazuh |
| Operating Systems | Ubuntu, Kali Linux |
| Traffic Analysis | Wireshark |
| Attack Simulation | Nmap, Hydra |
| Design & Documentation | Draw.io, VirtualBox |

---

## 🏗 Network Architecture
- **WAN** – External network access
- **LAN** – Internal SOC systems (Kali, Wazuh Manager)
- **DMZ** – Ubuntu-based EHR server
- **pfSense** – Central routing, firewall enforcement, and logging

Initial misconfigurations (broad “allow any” rules and exposed services) were intentionally identified to demonstrate real-world security gaps.

---

## 🔍 Attack Simulation
Simulated attacks were executed from **Kali Linux** to emulate common attacker behaviour:

- Network reconnaissance with **Nmap**
- Service and port discovery
- SSH brute-force attempts using **Hydra**
- Packet capture and analysis via **Wireshark**

These activities generated realistic indicators suitable for SOC detection and investigation.

---

## 🚨 Detection & Response
- **Wazuh agents** collected authentication, system, and security logs
- Alerts detected:
  - Port scanning
  - Repeated SSH authentication failures
  - Suspicious access attempts
- **Log correlation** identified the attacker source IP
- **Active Response** automatically blocked malicious IPs via firewall actions
- pfSense rules were hardened, and unnecessary services (e.g., SNMP) were disabled

---

## 📊 Key Findings
- Network segmentation alone is ineffective without **strict firewall enforcement**
- Overly permissive rules increase the risk of **lateral movement**
- Centralized logging and correlation greatly improve visibility
- Attack activity is often **noisy and detectable** when monitoring is correctly configured
- Automated response significantly reduces exposure time

---

## 🧩 Indicators of Compromise (IoCs)
- Repeated SSH login failures
- Port scanning patterns
- Correlated Wazuh alerts tied to `sshd` rule group
- Source IP identified as the attacking Kali host

---

## ✅ Key Takeaways
- Proper firewall configuration is critical to segmentation
- SIEM effectiveness depends on **log quality and rule tuning**
- Packet-level evidence strengthens investigations
- SOC operations rely on **integration, correlation, and response**
- Continuous validation of controls is essential

---

## 🔐 Recommendations
- Enforce **least-privilege firewall policies**
- Disable unnecessary services on security devices
- Harden SSH with key-based authentication and restricted sources
- Improve log retention and alert tuning
- Establish incident response playbooks
- Regularly review and test firewall and SOC configurations

---

## 🧾 Conclusion
This project demonstrates how a well-integrated SOC environment can detect, analyze, and respond to common attack techniques in a healthcare context.  
By combining segmentation, SIEM monitoring, traffic analysis, and automated response, the lab reflects real-world blue-team operations and highlights the importance of continuous security validation.

---

## 📄 Full Project Report

The complete technical report, including screenshots, configurations, alerts, and traffic analysis evidence, is available below:

👉 SOC Threat Detection in a Segmented Healthcare Network – Full Report (https://drive.google.com/file/d/1ASOgZOTvpC-tx5cO-0MWDXvvhmfVVDP_/view?usp=sharing)  

---

