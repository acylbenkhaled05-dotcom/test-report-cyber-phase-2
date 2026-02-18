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

**Top 4 immediate actions:**  
1.  Secure the admin accounts and admin priviledges (e.g remove the option to be an admin in the menu)
2.  Use HTTPS + encrypt the requests 
3.  reject weak password
4.  cooldown for account creations to avoid bots

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
| F-02 | 🔵 Fixed | User credentials are not encrypted in the database | The credentials are now crypted in the database | <img width="1020" height="291" alt="database encrypted" src="https://github.com/user-attachments/assets/6e9e7027-273f-4dde-b48c-9009cd684734" />
 |
| F-03 | 🔴 High | There is no cooldown on the registration system. | The same IP address can register as many accounts as it want in a short period. | <img width="1744" height="489" alt="image" src="https://github.com/user-attachments/assets/8939473e-c22d-4cc2-b817-d7050b5a97f9" /> <img width="1311" height="498" alt="image" src="https://github.com/user-attachments/assets/1a274cdf-c227-487a-a48c-e4cc34333d17" /> <img width="984" height="654" alt="image" src="https://github.com/user-attachments/assets/9492d576-3418-40d9-baa5-507f94b2129c" /> |
| F-04 | 🟡🔵 Partially Fixed | Key informations are not encrypted in the POST request(uses HTTP and not HTTPS) | User email are not encrypted in the POST request and can be modified. | <img width="522" height="17" alt="image" src="https://github.com/user-attachments/assets/7edc4d5a-a48b-4cba-9298-cff9637e79a2" /> <img width="165" height="18" alt="image" src="https://github.com/user-attachments/assets/a660a5fb-e1e2-4711-acc1-d729dac8dfe9" /> |
| F-05 | 🟡 Low | Weak password policy | Accepts passwords like "mdp". | <img width="534" height="134" alt="image" src="https://github.com/user-attachments/assets/11118e47-2dbd-4f6f-886b-eb9568276f74" /> <img width="963" height="213" alt="image" src="https://github.com/user-attachments/assets/2b47edc4-1f04-47cf-841d-df00612821e5" /> |




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
