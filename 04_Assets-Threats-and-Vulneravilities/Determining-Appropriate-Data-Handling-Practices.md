# Determining Appropriate Data Handling Practices  
*Google Cybersecurity Certificate – Course 04: Assets, Threats, and Vulnerabilities*  
*(Portfolio Activity – Data Privacy and Least Privilege Controls)*  

---

## 🎯 Lab Summary  
In this activity, I evaluated whether appropriate **data handling practices** were being applied after a **data leak incident** at an educational technology company.  
The objective was to identify weaknesses in the company’s implementation of the **principle of least privilege**, review guidance from **NIST SP 800-53 AC-6**, and recommend improvements to prevent future data leaks.  

The main tasks were to:  
- Analyze the incident and identify contributing factors.  
- Review NIST SP 800-53 AC-6 (“Least Privilege”) controls and enhancements.  
- Recommend two control improvements aligned with AC-6.  
- Justify how these enhancements would strengthen information privacy.  

---

## ⚙️ Scenario Overview  
The company developed a grading application used by academic institutions, instructors, parents, and students.  
During a sales meeting, a **manager shared access** to a folder containing internal business documents—including marketing materials and customer data—with their team. After the meeting, the manager **failed to revoke access**.  

Later, a sales representative—intending to share promotional content with a business partner—**accidentally sent a link to the entire internal folder**. The partner then **posted the link publicly on social media**, exposing confidential internal data.  

---

## 🧾 Data Leak Worksheet Summary  

| **Control** | **Least Privilege** |
|--------------|---------------------|
| **Issue(s)** | Permissions to the internal folder were not revoked after the meeting, leaving unnecessary access to all team members. Human error occurred when a sales representative ignored the warning and shared the wrong link. The folder also contained mixed data types, combining sensitive customer data with non-confidential marketing files. |
| **Review** | NIST SP 800-53 AC-6 establishes that users should only have the minimum level of access necessary to perform their specific tasks. It also includes control enhancements such as revoking access after a defined time period. In this case, access to the shared folder exceeded what was required for the sales meeting. |
| **Recommendation(s)** | 1️⃣ Implement automated access revocation after a defined period or event, such as post-meeting completion.  <br> 2️⃣ Enforce role-based access controls (RBAC) to ensure that employees only receive permissions necessary for their assigned tasks. |
| **Justification** | These controls will reduce the likelihood of future data leaks by ensuring access is granted only for specific tasks and automatically revoked afterward. Limiting permissions based on user roles prevents employees from unintentionally sharing confidential data outside the organization. |

---

## 🧠 Reflections / Notes  
- This activity emphasized the importance of **least privilege** as a foundational privacy control.  
- I learned how **AC-6** of NIST SP 800-53 defines clear steps to minimize exposure, including **time-based revocation** and **role-based access restriction**.  
- Properly configuring access workflows and data segmentation significantly reduces both **human error** and **information leakage**.  
- Documenting incidents and linking them to control standards provides a structured path for risk mitigation and compliance.  

---

## 📚 Key Skills Demonstrated  
- Application of **NIST SP 800-53 AC-6 (Least Privilege)**  
- Identification and analysis of **data-handling weaknesses**  
- Development of **control enhancement recommendations**  
- Understanding of **access management and data governance**  
- Professional documentation of **incident analysis and risk justification**  

---

*This activity demonstrates the ability to analyze data handling issues and apply the principle of least privilege to strengthen information privacy and prevent data leaks in real-world organizational settings.*  

