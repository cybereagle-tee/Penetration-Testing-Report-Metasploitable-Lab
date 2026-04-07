Penetration-Testing-Report-Metasploitable-Lab
--
---

- Name: Treasure James (The Cybereagle)
- Date: 7/04/2026

---

Project Overview  
--
This project demonstrates a full penetration testing engagement conducted in a controlled lab environment. The objective was to identify vulnerabilities in a target system, exploit them, and demonstrate post-exploitation activities such as gaining system-level access and creating a new user account.

⚠️ Disclaimer
--
This assessment was performed strictly in a controlled and authorized environment for educational purposes only. Unauthorized testing on systems without explicit permission is illegal and unethical.

---

Lab Environment
--
- Attacker Machine: Kali Linux  
- Target Machine: Metasploitable 2  
- Attacker IP: 192.168.56.102  
- Target IP: 192.168.56.101  
- Network Mode: Host-only / NAT  
- Virtualization Platform: VirtualBox  

Tools Used
--
- Nmap  
- Metasploit Framework  
- PostgreSQL (Metasploit database)  
- Terminal / Linux environment  

---

Methodology
--
(The penetration testing process followed a structured approach):
1. Reconnaissance  
2. Scanning and Enumeration  
3. Vulnerability Analysis  
4. Exploitation  
5. Post-Exploitation  
6. Documentation and Reporting  

---

Reconnaissance
--
The initial phase involved identifying active hosts within the network to determine the target system. The target machine was successfully discovered and confirmed to be reachable.

---

Scanning and Enumeration
--
Comprehensive scanning was performed to identify:
- Open ports  
- Running services  
- Service versions  
- Operating system details  
- Potential vulnerabilities  

The results revealed multiple exposed services, including FTP, which became a key attack vector.

---

Vulnerability Analysis
--

Based on the scan results, a critical vulnerability was identified in the FTP service:

- **vsFTPd 2.3.4 Backdoor Vulnerability**

This vulnerability is well-known for allowing unauthorized remote access due to a backdoor introduced in the service. It does not require authentication and can lead to remote command execution.

---

Exploitation
--

The identified vulnerability was successfully exploited using a Metasploit module targeting the vsFTPd backdoor.

Outcome:
- A command shell session was established on the target system  
- Remote command execution was achieved  
- System-level access was obtained  

---

Post-Exploitation Activities
--

After gaining access to the target system, further actions were performed:

- Accessed a system shell from the exploitation session  
- Verified system-level privileges  
- Created a new user account on the target machine  
- Confirmed persistence by validating the newly created account  

These actions demonstrate the level of control achieved over the compromised system.

---

Findings & Vulnerabilities
--

| ID | Vulnerability | Severity | Description |
|----|-------------|---------|------------|
| 1 | vsFTPd 2.3.4 Backdoor | Critical | Remote code execution without authentication |

---

Impact Assessment
--

The exploitation of the identified vulnerability resulted in:

- Unauthorized access to the system  
- Ability to execute system commands remotely  
- Creation of new user accounts  
- Full compromise of system integrity  

This represents a critical security failure and highlights the risks of unpatched services.

---

Recommendations
--

To mitigate the identified vulnerabilities, the following actions are recommended:

- Upgrade all services to their latest secure versions  
- Disable unnecessary or unused services (e.g., FTP if not required)  
- Apply regular system and security patches  
- Implement strong authentication mechanisms  
- Enforce firewall rules to restrict access to sensitive ports  
- Monitor system logs for suspicious activity  
- Deploy intrusion detection and prevention systems  

---

Evidence
--

- Network discovery scan results
- <img width="612" height="251" alt="image" src="https://github.com/user-attachments/assets/33872cef-16f8-425f-bb1a-9a9bf5db4067" />

---
 
- Full port and service scan outputs
- <img width="749" height="578" alt="image" src="https://github.com/user-attachments/assets/747a1f22-43fb-4538-b756-11c652b14586" />

---

- Vulnerability scan results
- <img width="701" height="572" alt="image" src="https://github.com/user-attachments/assets/ca8b3d81-e9e5-4505-b2ce-5c8e48d95192" />


  ---
  
- Exploitation session proof
- <img width="845" height="292" alt="image" src="https://github.com/user-attachments/assets/f055f944-02dc-4bd5-b7ee-bf30b8155482" />


  ---
  
- Post-exploitation access confirmation
- <img width="544" height="178" alt="image" src="https://github.com/user-attachments/assets/88cb9e20-7793-4181-9cd1-95fac6669c4a" />


---

- Verification of the newly created user account
- <img width="738" height="322" alt="image" src="https://github.com/user-attachments/assets/0db59524-87b0-4300-a7ab-142adde80f6e" />


---

Project Structure

penetration-testing-report/

│

├── README.md

├── reports/
│ └── final-report.pdf

├── screenshots/
│ ├── scan_results.png
│ ├── exploitation.png
│ ├── session_access.png
│ ├── user_creation.png

│

├── scans/
│ ├── full_scan.txt
│ ├── vuln_scan.txt
│ ├── scan.xml



---

Lessons Learned
--

- Practical application of network reconnaissance and enumeration techniques  
- Identification and analysis of real-world vulnerabilities  
- Exploitation of services using penetration testing frameworks  
- Post-exploitation techniques and system interaction  
- Importance of proper system hardening and patch management  
- Professional documentation of penetration testing activities  

---

Conclusion
--

This project successfully demonstrated a complete penetration testing workflow from initial reconnaissance to post-exploitation. A critical vulnerability in the FTP service was exploited, resulting in full system compromise and unauthorized account creation. The exercise highlights the importance of securing exposed services, maintaining updated systems, and implementing strong security controls.

---

Future Improvements
--

- Explore additional exploitation paths across other services  
- Implement automated scanning and reporting workflows  
- Expand testing to include multiple target systems  
- Integrate advanced post-exploitation techniques  
- Enhance reporting with structured visual dashboards  

---

Note:
--

This project forms part of a cybersecurity learning portfolio and demonstrates practical skills in penetration testing, vulnerability analysis, and security reporting.

---
