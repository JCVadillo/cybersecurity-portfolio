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

## 🧠 Reflections / Notes  
- This activity reinforced the importance of **proper firewall configuration** and **real-time network monitoring** to mitigate DDoS attacks.  
- Applying the **NIST CSF** provided a clear structure for addressing incidents, separating immediate containment from long-term prevention.  
- Future improvements could include **response drills** and **stricter segmentation**, minimizing disruption during volumetric attacks.

---

## 📚 Key Skills Demonstrated  
- Incident analysis and **root cause identification**.  
- Application of the **NIST Cybersecurity Framework (Identify, Protect, Detect, Respond, Recover)**.  
- Planning **technical mitigations** (firewall rules, IDS/IPS, monitoring) and **future response strategies**.  
- Clear technical documentation suitable for security portfolios.  

---

*This exercise showcases the structured application of NIST CSF for DDoS incident response and demonstrates network security response planning in a real-world scenario.*

