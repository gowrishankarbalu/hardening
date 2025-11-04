**SSH and Access Control Hardening: Secure Your Linux Server Like a Pro**


This repository outlines **proven commands, configuration examples, and outputs** for implementing strong **SSH and Access Control Hardening** on Linux servers, specifically targeting **Ubuntu** and **openSUSE** distributions. By following these steps, you can significantly strengthen system security and achieve better compliance.

## **Overview and Key Benefits**

Hardening access controls is critical for protecting Linux systems and digital ecosystems. The comprehensive application of these steps yields several advantages:

*   **Enhanced Security:** This process **reduces the risk of unauthorized access** to critical systems, files, and services, effectively limiting potential attack vectors for cybercriminals or malicious insiders.
*   **Compliance with Regulations:** Implementing these controls helps meet industry standards and regulatory requirements such as **SOC 2, ISO 27001, GDPR, and HIPAA**, demonstrating due diligence in protecting sensitive data.
*   **Reduced Attack Surface:** By tightening access and removing unnecessary permissions, fewer potential entry points are available for attackers, protecting against common attacks like brute force and privilege escalation.
*   **Minimized Insider Threats:** Proper access controls enforce the **principle of least privilege**, restricting users to only what they need, thus reducing accidental or intentional misuse of sensitive data.
*   **Improved Audit and Monitoring:** Hardening enables better tracking of user activities and access logs, which facilitates auditing, forensic investigations, and accountability.

## **Comprehensive Hardening Steps Covered**

This guide details nine essential steps for securing SSH access:

1.  **Disable Root Login:** Prevents attackers from brute-forcing the default "root" account by ensuring only non-root users can connect via SSH.
2.  **Enforce Key-Based Authentication:** Significantly enhances security by using cryptographic login keys (like `ed25519`) and **disabling password authentication** to eliminate brute-force vulnerabilities.
3.  **Restrict SSH Access:** Limits exposure by using commands like `AllowUsers` (Ubuntu) or `AllowGroups` (openSUSE) to ensure only selected, trusted accounts can connect via SSH.
4.  **Change the Default SSH Port:** Reduces automated attacks and scanning noise by moving SSH from the default port 22 to a custom port (e.g., 2222), requiring corresponding firewall configurations (UFW or firewalld).
5.  **Enable Two-Factor Authentication (2FA):** Provides an additional layer of protection using a one-time password (OTP) via tools like Google Authenticator, making SSH require both a private key and a time-based OTP.
6.  **Protect Against Brute-Force Attacks with Fail2Ban:** Monitors SSH logs and automatically blocks IPs that show repeated failed authentication attempts, significantly reducing malicious activity.
7.  **Set Idle Timeouts and Session Limits:** Automatically disconnects idle or incomplete SSH sessions using settings like `ClientAliveInterval 300` (disconnects after 5 minutes of idle time) and `LoginGraceTime 60` (cancels incomplete logins after 1 minute).
8.  **Audit SSH Logs Regularly:** Provides methods (using `tail -f /var/log/auth.log` for Ubuntu or `sudo journalctl -u sshd -f` for openSUSE) for frequently reviewing logs to detect unusual activity and suspicious source IPs.
9.  **SSH Hardening Checklist:** Includes a checklist of verification commands (e.g., `grep PermitRootLogin /etc/ssh/sshd_config`) and their expected secure results.

***

📖 **Full Blog Reference:**  
👉 [Access Control Hardening – Secure Your Linux Server Like a Pro](https://blog.gowrishankar.me/2025/10/31/access-control-hardening/)


**In essence, implementing these SSH and access control hardening steps is like installing multiple robust security gates around your critical resources.** Instead of relying on a single, easily guessable password (a simple padlock), you enforce layered security: requiring cryptographic keys, a separate login process (non-root), a secret access code (2FA), and a watchful guard (Fail2Ban) that quickly blocks unauthorized intruders. This structured approach ensures business continuity by safeguarding key resources.
