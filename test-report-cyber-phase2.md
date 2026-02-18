# 1️⃣ Introduction

**Tester(s):**  
- Name:  Matthias | Assil

**Purpose:**  
- Identify vulnerabilities in registration and authentication flows.

**Scope:**  
- Tested components: Registration system
- Exclusions: Login system and reservation system
- Test approach: Gray-box / Black-box / White-box with Burp Suite

**Test environment & dates:**  
- Start:  18/02/2026
- End:  18/02/2026
- Test environment details (OS, runtime, DB, browsers): Docker on Windows 11 | Browser : Blurp Browser | Zap : zap report

**Assumptions & constraints:**  
- Assumption : the application is insecure.
- No contraints

---

# 2️⃣ Executive Summary

This is a test of the lastest version of the website, for the previous tests we encountered many issues that created vulnerabilities easily exploitable by hackers, unfortunately there are still issues that need to be fixed such as the admin priviledges and admin roles that can be bypassed and others that we will see now.

**Overall risk level:** High 

**Top 5 immediate actions:**  
1.  Secure the admin accounts and admin priviledges (e.g remove the option to be an admin in the menu)
2.  User credentials are not encrypted in the database
3.  Use HTTPS + encrypt the requests 
4.  reject weak password
5.  cooldown for account creations to avoid bots

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Fixed** | The issue has been fixed                                            | *None* |


---

# 4️⃣ Findings (filled with examples → replace)

> Fill in one row per finding. Focus on clarity and the most important issues.

| ID | Severity | Finding | Description | Evidence / Proof |
|------|-----------|----------|--------------|------------------|
| F-01 | 🔴 High |  Permissions can be easily bypass. | We can choose to be an administrator when we register. |  <img width="1366" height="595" alt="image" src="https://github.com/user-attachments/assets/fc26e6e8-71f4-4946-852c-f94649d904ba" /> |
| F-02 | 🔵 Fixed | User credentials are not encrypted in the database | The credentials are now crypted in the database | <img width="1020" height="291" alt="database encrypted" src="https://github.com/user-attachments/assets/6e9e7027-273f-4dde-b48c-9009cd684734" /> |
| F-03 | 🔴 High | There is no cooldown on the registration system. | The same IP address can register as many accounts as it want in a short period. | <img width="1322" height="399" alt="image" src="https://github.com/user-attachments/assets/0d976f37-6983-4667-9bac-322c8f48920a" /> <img width="1023" height="723" alt="image" src="https://github.com/user-attachments/assets/4157ac3d-8a7e-40e7-8ba2-c128f60a171a" /> |
| F-04 | 🟡🔵 Partially Fixed | Key informations are not encrypted in the POST request(uses HTTP and not HTTPS) | User email are not encrypted in the POST request and can be modified. |<img width="542" height="19" alt="login visible" src="https://github.com/user-attachments/assets/accf3715-2463-401a-8136-44c399481709" /> <img width="401" height="91" alt="image" src="https://github.com/user-attachments/assets/b6118804-9270-41f8-ad54-68d0d096c41b" /> |
| F-05 | 🟡 Low | Weak password policy | Accepts only passwords over 4 characters but still weak with no specific characters| <img width="529" height="290" alt="password lenght increased" src="https://github.com/user-attachments/assets/a933004b-d469-422b-8010-1b90ee902b9d" /> |




# 5️⃣ OWASP ZAP Test Report (Attachment)

**Purpose:**  
- Attach or link your OWASP ZAP scan results (Markdown format preferred).
https://github.com/acylbenkhaled05-dotcom/zap_report_round3.md/blob/main/zap-report-round3.md
---

**Instructions:**
1. Check lecture recordings
2. Save the report as `zap_report_round1.md` and link it below.
  https://github.com/acylbenkhaled05-dotcom/test-report-cyber-phase-2/blob/main/test-report-cyber-phase2.md

---
> [!NOTE]
> 📁 **Attach full report:** → `check itslearning` → **Add a link here**
https://github.com/acylbenkhaled05-dotcom/test-report-cyber-phase-2/blob/main/test-report-cyber-phase2.md
---
