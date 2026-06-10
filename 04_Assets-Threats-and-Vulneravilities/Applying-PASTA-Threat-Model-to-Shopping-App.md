# Applying the PASTA Threat Model Framework to a Mobile Shopping App
*Google Cybersecurity Certificate – Course 04: Assets, Threats, and Vulnerabilities*
*(Portfolio Activity – Apply the PASTA Threat Model Framework)*

---

## 🎯 Lab Summary

In this activity, I performed a **threat model** of a new mobile shopping application using the **Process for Attack Simulation and Threat Analysis (PASTA)** framework.
The objective was to assess the risk profile of a sneaker marketplace app—still in development—and determine whether it is safe to launch by working through all seven stages of the PASTA framework.

The main tasks were to:
- Identify the app's business and security objectives
- Define the technical scope and prioritize the most critical technology
- Decompose the application by reviewing a data flow diagram
- Apply an attacker mindset to identify potential threats
- List exploitable vulnerabilities
- Map assets, threats, and vulnerabilities to an attack tree
- Recommend security controls to reduce risk

---

## ⚙️ Scenario Overview

The company serves sneaker enthusiasts and collectors and is preparing to launch a **mobile app** that allows customers to **buy and sell shoes**.

The app is expected to seamlessly connect sellers and shoppers, making it easy for users to sign up, log in, and manage their accounts. **Data privacy is a major concern**, as the business wants users to feel confident their information is handled responsibly. Buyers can directly message sellers, rate them to encourage good service, and complete purchases quickly through **several payment options**. Proper payment handling is critical to avoid legal issues.

As a member of the security team, my responsibility was to evaluate the application's architecture for security risks **before launch**, following the seven stages of the PASTA framework.

---

## 🧾 PASTA Worksheet Summary

### Stage I – Define Business and Security Objectives

*The goal of this stage is to understand why the application was developed and what it is expected to do.*

- The app must **securely process customer transactions** through multiple payment options.
- The app performs significant **back-end processing**: account sign-up/login, account management, connecting buyers and sellers, direct messaging, and seller ratings.
- The app must **comply with industry regulations** for payment handling (e.g., PCI DSS) and data privacy/protection in order to avoid legal issues.

---

### Stage II – Define the Technical Scope

*The technologies in scope are: API, PKI (AES + RSA), SHA-256, and SQL. The goal of this stage is to prioritize which technology to evaluate first from a security perspective.*

> SQL should be evaluated first. The database stores the application's most critical data—user accounts, seller information, and payment records—and is accessed during every transaction. Because SQL injection is among the most common and damaging attack vectors, securing queries against injection takes priority over assessing the API, PKI, and SHA-256 components.

| **Technology** | **Priority** | **Security Consideration** |
|---|---|---|
| **SQL** | 🔴 Highest | Stores all critical data; SQL injection is a top OWASP risk if input is not validated. |
| **API** | 🟠 High | Third-party APIs expand the attack surface; require strong authentication and trusted, updated sources. |
| **PKI (AES + RSA)** | 🟡 Moderate | Protects data in transit; spoofing/MITM is always a risk, but the AES + RSA combination is robust. |
| **SHA-256** | 🟢 Lower | Strong hashing algorithm; risk lies in implementation—**salting** should be enforced. |

---

### Stage III – Decompose the Application

*The goal of this stage is to analyze how the application handles information by reviewing a data flow diagram. The provided diagram models a single process: a buyer searching the database for sneakers for sale.*

**Data flow:** `User → Product Search Process → Database → User`

Mapping the prioritized technologies to this process:

| **Stage of the flow** | **Protecting technology** |
|---|---|
| Data in transit (user ↔ process, over the network) | **PKI (AES + RSA)** encrypts the data while it travels. |
| User input reaching the database | **SQL + input validation/sanitization** protects against malicious queries. |
| Client–server data exchange | **API** governs how the data is requested and returned. |

> Note: SHA-256 plays a minimal role in this specific search process, as no passwords or sensitive credentials are handled here—its relevance lies in login and payment processes.

---

### Stage IV – Threat Analysis

*The goal of this stage is to identify potential threats to the information handled by the app, considering both internal and external threat sources.*

| **Type** | **Threat** |
|---|---|
| 🏢 **Internal** | A customer support employee whose elevated permissions are not revoked after a task—violating the **least privilege** and **need-to-know** principles—could expose client information, either accidentally or intentionally. |
| 🌐 **External** | A malicious actor attempting to compromise the application's data through external attack techniques such as **SQL injection**. |

---

### Stage V – Vulnerability Analysis

*The goal of this stage is to identify weaknesses in the attack surface of the in-scope technologies that the identified threats could exploit.*

| **#** | **Vulnerability** |
|---|---|
| 1️⃣ | The application's database is vulnerable to **SQL injection** because user input is not properly validated or sanitized before being processed in queries. |
| 2️⃣ | **Unpatched or outdated server software** leaves known vulnerabilities (e.g., CVEs) exposed, giving attackers an entry point to compromise the system. |

> Resources such as the **CVE® list** and **OWASP** are useful for identifying common software vulnerabilities.

---

### Stage VI – Attack Modeling

*The goal of this stage is to map assets, threats, and vulnerabilities to an attack tree. The provided attack tree targets **User Data** as the attacker's objective.*

```text
                    +-----------------+
                    |   User Data     |   <- Attacker's objective (root)
                    +--------+--------+
              +--------------+--------------+
        +-----v-----+                 +-----v--------+
        |   SQL     |                 |   Session    |
        | Injection |                 |  Hijacking   |
        +-----+-----+                 +-----+--------+
        +-----v----------+          +-------v----------+
        |  Lack of       |          |   Weak login     |
        |  prepared      |          |   credentials    |
        |  statements    |          |                  |
        +----------------+          +------------------+
```

The attack tree confirms and connects the prior analysis:
- The **SQL injection** branch ↔ maps to the external threat (Stage IV) and vulnerability #1 (Stage V); its leaf, *lack of prepared statements*, points directly to the technical defense.
- The **session hijacking** branch ↔ introduces an **authentication** attack vector, enabled by *weak login credentials*, reinforcing the need for stronger access controls.

---

### Stage VII – Risk Analysis and Impact (Security Controls)

*The final goal is to recommend defenses and safeguards that mitigate the identified threats and reduce the likelihood of a security incident, such as a data breach.*

| **#** | **Security Control** | **Purpose** |
|---|---|---|
| 1️⃣ | **Implement SQL injection prevention techniques** | Use prepared statements (parameterized queries) along with input validation and sanitization to protect the database from malicious queries. |
| 2️⃣ | **Enforce strong login credentials and MFA** | Require strong password policies and multi-factor authentication to reduce the risk of weak credentials being exploited for session hijacking or unauthorized access. |
| 3️⃣ | **Keep server software up to date** | Regularly patch and update server software to close known vulnerabilities (CVEs) that attackers could exploit. |
| 4️⃣ | **Ensure compliance with laws and regulations** | Adhere to applicable standards such as **PCI DSS** (payment handling) and data protection regulations to safeguard user data and avoid legal issues. |

---

## 🧠 Reflections / Notes

- This activity reinforced that **PASTA is a risk-centric framework**—each stage builds on the previous one, turning business objectives into concrete, prioritized security controls.
- I learned to clearly distinguish between a **threat** (the actor or event that can cause harm) and a **vulnerability** (the weakness it exploits)—a distinction that is easy to confuse but essential for accurate threat modeling.
- Mapping technologies to the **data flow diagram** showed that not every technology applies to every process (e.g., SHA-256 is irrelevant to a simple search query but critical at login/payment).
- The **attack tree** demonstrated the value of defending at the *root cause* (the leaf of the tree)—for example, addressing *weak login credentials* with MFA and secure session management rather than only reacting to the attack itself.
- Prioritizing **SQL** as the most critical technology highlighted how a single component can concentrate the majority of an application's risk when it stores and serves all business-critical data.

---

## 📚 Key Skills Demonstrated

- Application of the **PASTA** (Process for Attack Simulation and Threat Analysis) threat model framework
- Translation of **business objectives** into **security requirements**
- **Technical scope definition** and risk-based prioritization of technologies (API, PKI, SHA-256, SQL)
- Interpretation of **data flow diagrams** to analyze how data is processed and protected
- Application of an **attacker mindset** to identify internal and external threats
- **Vulnerability analysis** using industry resources (CVE®, OWASP)
- Construction and interpretation of **attack trees** to map assets, threats, and vulnerabilities
- Recommendation of **layered, actionable security controls** aligned with both technical and business objectives

---

*This activity demonstrates the ability to perform a structured, risk-centric threat model of an application before launch—translating business goals into prioritized security requirements, identifying realistic threats and vulnerabilities, and recommending defenses that align technical controls with regulatory and business needs.*

