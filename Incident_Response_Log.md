# Security Incident Response Log

> **Note:** These incident logs were developed within a simulated lab environment for practical hands-on security training. Any references to company data or networks are used solely for demonstration and learning purposes.

## Executive Summary
Security Operations Center (SOC) analysts rely on meticulous documentation to track, investigate, and remediate security events. This journal details the triage and analysis of multiple security incidents, ranging from ransomware infections and malicious file executions to large-scale data breaches. By applying structured triage methodologies, this log demonstrates effective incident response, threat analysis, and remediation planning.

## Objective
The objective of this log is to document and analyze various security incidents, identify threat vectors and impacts, and recommend appropriate remediation strategies to improve overall organizational security posture.

## Skills and Tools Demonstrated
- **Tools:** VirusTotal, tcpdump, Intrusion Detection Systems (IDS)
- **Concepts:** Incident Response, Threat Intelligence, Malware Analysis, Network Traffic Analysis, Phishing Mitigation, Vulnerability Patching

---
### Incident 01: Ransomware Infection via Phishing
**Date of Entry:** September 4, 2026

* **Incident Summary:** A group of threat actors successfully installed ransomware on the systems of a healthcare organization.
* **Attack Vector & Timeline:** The incident occurred on a Tuesday at 9:00 AM. The attackers gained initial access to the company systems through a targeted phishing attack. 
* **Impact:** Once inside the network, the attackers encrypted critical system files and deployed a ransom note demanding financial payment in exchange for the release of these files.
* **Recommended Remediation:** 
  * **Immediate Action:** The organization should attempt to regain access and control of its files through internal recovery efforts before considering paying the ransom. 
  * **Preventative Action:** Mandate comprehensive security awareness training so that all employees become more aware of phishing tactics and likely attacks based on the company's weak points.

### Incident 02: Malicious File Execution and Hash Analysis

* **Incident Summary:** An employee received and executed a malicious file from an unknown threat actor operating under the alias "Clyde West".
* **Attack Vector & Timeline:** At 1:20 PM, the Intrusion Detection System (IDS) alerted the SOC to an unauthorized file download on an employee's computer containing a suspicious hash. 
* **Investigation:** The suspicious file hash was investigated using the VirusTotal tool. The file was officially confirmed as malicious based on its vendor ratio, community score, and specific flags found in the detection tab.
* **Recommended Remediation:** Increase employee awareness through targeted security training, focusing specifically on personal workplace security and the risks of executing unsolicited files.

### Incident 03: Data Breach and Web Exploit

* **Incident Summary:** An attacker gained unauthorized access to approximately 50,000 records, compromising customer personally identifiable information (PII) and financial information.
* **Attack Vector & Timeline:** The unauthorized access occurred across two instances on December 22, 2022, at 3:13, and December 28, 2022, at 7:20 PM. The attacker targeted multiple employee email accounts at their computers using a known web exploit.
* **Impact:** The breach exposed sensitive customer records and resulted in an estimated $100,000 in direct financial costs to the organization.
* **Recommended Remediation:** The known web exploit used in the attack must be patched immediately. Additionally, the security system should be audited and tested for performance so that any weak points can be reinforced or fixed.
