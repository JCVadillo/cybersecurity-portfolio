# Use the NIST CSF to respond to a security incident

## DDoS Incident Response – ICMP Flood Attack  
*Google Cybersecurity Certificate – Course 03: Connect and Protect: Networks and Network Security*  
*(Portfolio Activity #2)*  

---

## 🎯 Scenario Summary  
- The organization experienced a **2-hour outage of internal network services** due to a Distributed Denial of Service (DDoS) attack caused by an **ICMP flood**.  
- The attack exploited an **unconfigured firewall**, allowing a flood of ICMP packets to overwhelm servers and disrupt normal internal traffic.  

---

## 🛡 NIST CSF Application  
This report follows the **NIST Cybersecurity Framework (CSF)** to document the incident and outline security improvements.

### 🔍 Identify  
- An **unconfigured firewall** allowed malicious ICMP traffic into the network.  
- The attack overwhelmed servers and **saturated the LAN**, preventing normal internal access to network resources.  

### 🔒 Protect  
- Implemented **firewall rules** to limit incoming ICMP packet rates.  
- Enabled **IP source verification** to detect and block spoofed addresses.  
- Deployed **IDS/IPS filtering** and **network monitoring software** to mitigate malicious ICMP traffic.

### 🕵️ Detect  
- Configured **IDS/IPS** and monitoring tools to **detect abnormal traffic patterns** in real time.  
- Established **alerts for suspicious ICMP activity** to improve response speed in future incidents.

### 🚨 Respond  
- Blocked incoming ICMP packets during the attack.  
- Stopped all **non-critical network services** and prioritized restoring **critical ones**.  
- Future plans: Implement **network segmentation and security zones** to isolate critical resources and reduce internal impact.

### 🔄 Recover  
- Restored **critical network services** and full LAN functionality within 2 hours.  
- Notified IT staff of resolution and advised continued monitoring for residual issues.

---

## 📦 Deliverable  
This portfolio activity deliverable includes:  
- An **incident analysis report** applying the NIST CSF framework.  
- Supporting reference material outlining CSF core functions and response guidelines.  

---

## 📂 Files Included  
- **`NIST-CSF-incident-respond/`** – Contains the full incident analysis report ([incident-analysis-report.pdf](./NIST-CSF-incident-respond/incident-analysis-report.pdf)).  
- **`supporting-material/`** – Contains the reference guide on applying the NIST CSF ([Applying the NIST CSF.pdf](./supporting-material/Applying%20the%20NIST%20CSF.pdf)).  
- **`README.md`** – This documentation overview.  

---

## 🧠 Reflections / Notes  
- This incident highlighted the importance of **proper firewall configuration** and **real-time monitoring** to prevent DDoS attacks.  
- Applying the **NIST CSF** provided a structured method for analyzing and documenting security incidents.  
- Future improvements may include **network segmentation** and **response drills** to minimize downtime during similar incidents.  

---

## 📚 Key Skills Demonstrated  
- Incident analysis and **root cause identification**.  
- Application of the **NIST Cybersecurity Framework (Identify, Protect, Detect, Respond, Recover)**.  
- Planning **technical mitigations** (firewall rules, IDS/IPS, monitoring) and **future response strategies**.  
- Clear technical documentation suitable for cybersecurity portfolios.  

---

*This exercise demonstrates the structured application of NIST CSF to DDoS incident response and showcases professional reporting aligned with industry best practices.*

