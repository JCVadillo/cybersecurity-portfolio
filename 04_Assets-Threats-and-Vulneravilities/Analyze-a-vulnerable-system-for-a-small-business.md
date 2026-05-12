# Vulnerability Assessment of a Publicly Accessible Database Server
*Google Cybersecurity Certificate – Course 04: Assets, Threats, and Vulnerabilities*
*(Portfolio Activity – Analyze a Vulnerable System for a Small Business)*

---

## 🎯 Lab Summary

In this activity, I conducted a **vulnerability assessment** for an e-commerce company whose database server had been publicly accessible since its launch three years ago.
The objective was to identify potential risks, evaluate their likelihood and severity, and recommend realistic remediation strategies to communicate to decision makers.

The main tasks were to:
- Review the system description and scope of the assessment
- Write a purpose statement explaining the business value of securing the server
- Identify threat sources and threat events using **NIST SP 800-30 Rev. 1**
- Score each risk by likelihood and severity
- Document the assessment approach transparently
- Propose actionable remediation controls

---

## ⚙️ Scenario Overview

The company operates an e-commerce platform with a globally distributed remote workforce. Employees regularly query a remote **MySQL database server** to support business operations, including finding and managing customer data.

The server had been **open to the public** since the company's launch — a serious vulnerability, as it exposes the system to any actor on the internet without any access control requirements.

The **scope** of this assessment is focused specifically on the **current access controls of the system**. It does not cover physical security, environmental threats, or vulnerabilities in dependent systems. The assessment was conducted over a three-month period and guided by **NIST SP 800-30 Rev. 1**.

The system runs on the latest version of **Linux**, uses **IPv4 networking**, and already has **SSL/TLS encrypted connections** as a baseline security measure.

---

## 🧾 Vulnerability Assessment Report Summary

### Purpose

*The database server is the organization's most critical asset, supporting day-to-day business operations for a globally distributed workforce. It stores sensitive information including employee records, product data, and current and prospective client data — all of which are subject to both intentional and accidental threats such as unauthorized access, data alteration, or exfiltration. Securing this server is essential to protect the confidentiality, integrity, and availability of business-critical data. A compromise or disruption of the server could halt operations entirely, resulting in significant revenue loss and long-term reputational damage.*

---

### Risk Assessment

| **Threat Source** | **Threat Event** | **Likelihood** | **Severity** | **Risk** |
|---|---|---|---|---|
| Hacker / Hacktivist *(Outsider)* | Perform reconnaissance and surveillance of organization | 3 | 1 | 3 |
| Competitor *(Group)* | Obtain sensitive information via exfiltration | 2 | 3 | 6 |
| Employee / Customer *(Standard User)* | Alter/Delete critical information | 3 | 3 | 9 |

> Scores based on NIST SP 800-30 Rev. 1 scale: **1 = Low**, **2 = Moderate**, **3 = High**. Risk = Likelihood × Severity.

---

### Approach

*The approach for this assessment was guided by the defined scope, which focuses specifically on the access control vulnerabilities of the database server. Threat sources were selected based on their relevance to a publicly accessible system serving a globally distributed workforce, prioritizing those most likely to interact with or exploit the server's exposure.*

*Threat events were identified by evaluating the realistic capabilities and intent of each threat source in the context of an e-commerce environment. Where multiple events were plausible, selection was based on logical sequencing and potential impact — for example, reconnaissance was prioritized over denial-of-service for external actors, as the latter requires targeted motivation unlikely in opportunistic attacks against a public server.*

*Likelihood and severity scores were derived using the NIST SP 800-30 Rev. 1 scoring framework, combining available system information, the nature of each threat source, and the potential business impact of each event. Scores were assigned objectively, avoiding the tendency to overweight threats that appear dramatic while underweighting more probable, everyday risks such as accidental data modification by non-technical users.*

*A key limitation of this assessment is that it focuses exclusively on access control risks as defined by the scope, and does not account for physical security, environmental threats, or vulnerabilities within dependent systems.*

---

### Remediation Strategy

*The system currently implements SSL/TLS encrypted connections, which provides a baseline level of protection by encrypting data in transit between the server and its users. However, given the identified risks, additional controls are necessary to address the vulnerabilities exposed by the server's public accessibility.*

*First, regular vulnerability scanning should be implemented to proactively identify weaknesses across the server and its dependent systems, including the network infrastructure and MySQL database. Since the server is publicly accessible, it is reasonable to assume that other components may also be exposed. Routine scans would allow the organization to detect and remediate vulnerabilities before threat actors can exploit them — directly reducing the likelihood of reconnaissance-based attacks.*

*Second, an Authentication, Authorization, and Accountability (AAA) framework should be enforced across all access points. Authentication controls, including multi-factor authentication (MFA) for employees and system administrators, would significantly reduce the risk of unauthorized access. Authorization controls based on the principles of least privilege and need-to-know would ensure that users — both internal and external — can only access the data required for their specific role. Customers, for example, should only have access to their own purchase history and personal data, with no visibility into server-level resources. Finally, accountability measures such as system logging and session monitoring would create an auditable record of all interactions with the server, enabling the detection of suspicious activity and supporting incident response efforts.*

*Together, these controls directly address the three risks identified in this assessment. Implementing them will reduce the attack surface of the server, limit the potential damage of both intentional and accidental threats, and provide the organization with the visibility needed to detect and respond to security events in a timely manner.*

---

## 🧠 Reflections / Notes

- This activity reinforced the importance of **defining scope clearly** before selecting threat sources — not every threat type is relevant to every assessment
- I learned that a **publicly accessible server** is automatically indexed by tools like **Shodan**, making reconnaissance highly likely regardless of whether the server has been specifically targeted — this is why Likelihood:3 was appropriate for the Hacker/Hacktivist threat source
- The **AAA Framework** (Authentication, Authorization, Accountability) emerged as the most comprehensive single control to address access-related risks across all three threat sources
- Recognizing **existing controls** (SSL/TLS) before recommending new ones is essential to avoid resource duplication and demonstrate analytical credibility
- Scoring risks objectively requires resisting the bias of overweighting "dramatic" threats (e.g., hackers) while underestimating high-probability everyday risks like accidental data alteration by non-technical users

---

## 📚 Key Skills Demonstrated

- Application of **NIST SP 800-30 Rev. 1** for structured risk assessment
- Identification and justification of **threat sources and threat events** in an e-commerce context
- Risk scoring using **Likelihood × Severity** methodology
- Transparent documentation of **assessment approach and limitations**
- Development of **realistic, layered remediation strategies** (vulnerability scanning + AAA framework)
- Recognition of **existing security controls** as a baseline before recommending new ones
- Understanding of how **public exposure** changes the threat landscape (Shodan, automated scanning)

---

*This activity demonstrates the ability to conduct a structured vulnerability assessment using industry-standard frameworks, communicate risk clearly to non-technical stakeholders, and propose actionable remediation strategies aligned with both technical and business objectives.*
