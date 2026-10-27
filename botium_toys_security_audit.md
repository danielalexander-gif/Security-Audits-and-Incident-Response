# Security Audit and Compliance Assessment: Botium Toys

> **Note:** This risk assessment and compliance audit was developed within a simulated lab environment for practical hands-on security training. Any references to company data, systems, or networks are used solely for demonstration and learning purposes.

## Executive Summary
Botium Toys currently operates with an elevated risk profile (scored 8 out of 10) due to inadequate asset management and the absence of critical security controls. This audit assesses the organization's existing infrastructure against industry standards to identify gaps in data protection, access management, and system resilience. By completing a comprehensive controls and compliance checklist, this report provides a strategic roadmap to align Botium Toys with PCI DSS, GDPR, and SOC frameworks.

## Objective
The objective of this project is to evaluate Botium Toys' current security posture against established frameworks and provide actionable recommendations to mitigate operational risks and achieve regulatory compliance.

## Controls Assessment Checklist
*Evaluation of existing controls based on the provided risk assessment data.*

| Control | In Place? | 
| :--- | :--- | 
| Least Privilege | No | 
| Disaster recovery plans | No | 
| Password policies | Yes (Requires update) | 
| Separation of duties | No | 
| Firewall | Yes | 
| Intrusion detection system (IDS) | No | 
| Backups | No | 
| Antivirus software | Yes | 
| Manual monitoring, maintenance, and intervention for legacy systems | Yes (Lacks defined schedule) | 
| Encryption | No | 
| Password management system | No | 
| Locks (offices, storefront, warehouse) | Yes | 
| Closed-circuit television (CCTV) surveillance | Yes | 
| Fire detection/prevention (fire alarm, sprinkler system, etc.) | Yes |

## Compliance Checklist
*Evaluation of adherence to regulatory best practices based on current infrastructure.*

### Payment Card Industry Data Security Standard (PCI DSS)
| Best Practice | In Place? |
| :--- | :--- |
| Only authorized users have access to customers' credit card information. | No |
| Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment. | No |
| Implement data encryption procedures to better secure credit card transaction touchpoints and data. | No |
| Adopt secure password management policies. | No |

### General Data Protection Regulation (GDPR)
| Best Practice | In Place? |
| :--- | :--- |
| E.U. customers' data is kept private/secured. | No |
| There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach. | Yes |
| Ensure data is properly classified and inventoried. | No |
| Enforce privacy policies, procedures, and processes to properly document and maintain data. | Yes |

### System and Organizations Controls (SOC type 1, SOC type 2) 
| Best Practice | In Place? |
| :--- | :--- |
| User access policies are established. | No |
| Sensitive data (PII/SPII) is confidential/private. | No |
| Data integrity ensures the data is consistent, complete, accurate, and has been validated. | Yes |
| Data is available to individuals authorized to access it. | Yes |

## Recommendations
To reduce the elevated risk score and align with industry compliance frameworks (PCI DSS, GDPR, SOC), Botium Toys must prioritize the following initiatives:

*   **Implement Identity and Access Management (IAM):** Immediately enforce the principle of least privilege and separation of duties. Deploy a centralized password management system and update the organizational password policy to enforce complexity and length requirements.
*   **Secure Sensitive Data:** Implement encryption protocols for data at rest and in transit to protect customers' credit card information, PII, and SPII, bringing the organization into compliance with PCI DSS and GDPR.
*   **Establish Asset Management and Classification:** Dedicate resources to inventory, classify, and track all IT assets (both physical and digital) to understand business continuity impacts and eliminate blind spots.
*   **Deploy Business Continuity and Disaster Recovery (BCDR) Controls:** Establish a formal disaster recovery plan and initiate automated, routine backups of all critical company data. 
*   **Enhance Network Security Monitoring:** Install and configure an Intrusion Detection System (IDS) to actively monitor internal network traffic and complement the existing firewall and antivirus solutions.
