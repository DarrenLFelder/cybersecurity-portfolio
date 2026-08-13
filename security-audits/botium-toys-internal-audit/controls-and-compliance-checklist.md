# Controls and Compliance Checklist

## Botium Toys Internal Security Audit

This checklist documents my assessment of the security controls and compliance practices currently implemented at Botium Toys based on the provided scope, asset inventory, and risk assessment.

---

## Controls Assessment

| Control | Implemented |
|---|---|
| Least Privilege | No |
| Disaster recovery plans | No |
| Password policies | No |
| Separation of duties | No |
| Firewall | Yes |
| Intrusion detection system (IDS) | No |
| Backups | No |
| Antivirus software | Yes |
| Manual monitoring, maintenance, and intervention for legacy systems | Yes |
| Encryption | No |
| Password management system | No |
| Locks (offices, storefront, warehouse) | Yes |
| Closed-circuit television (CCTV) surveillance | Yes |
| Fire detection/prevention | Yes |

### Controls Assessment Summary

Botium Toys has several technical and physical security controls in place, including a firewall, antivirus software, physical locks, CCTV surveillance, and fire detection and prevention systems.

However, significant security gaps remain. Least privilege and separation of duties have not been implemented, sensitive payment information is not encrypted, an IDS is not present, and the organization lacks backups and a disaster recovery plan.

Existing password requirements are insufficient and should be strengthened to meet appropriate password complexity standards. Legacy-system monitoring is performed, but it also requires improvement through regular scheduling and clearly defined intervention procedures.

---

## PCI DSS Assessment

| Best Practice | Meets Practice |
|---|---|
| Only authorized users have access to customers' credit card information | No |
| Credit card information is stored, accepted, processed, and transmitted in a secure environment | No |
| Data encryption procedures protect credit card transaction data | No |
| Secure password management policies are implemented | No |

### PCI DSS Findings

The assessment identified significant weaknesses involving cardholder data. Employees may have excessive access to payment information, encryption is not currently used to protect cardholder data, and password-management controls are inadequate.

These weaknesses should receive high remediation priority because Botium Toys accepts, processes, transmits, and stores payment-card information.

---

## GDPR Assessment

| Best Practice | Meets Practice |
|---|---|
| E.U. customers' data is kept private and secured | No |
| A plan exists to notify E.U. customers within 72 hours of a breach | Yes |
| Data is properly classified and inventoried | No |
| Privacy policies, procedures, and processes are documented and enforced | Yes |

### GDPR Findings

Botium Toys has established a 72-hour breach-notification plan and has privacy policies, procedures, and processes in place.

However, additional work is needed to properly classify and inventory data and strengthen the confidentiality and protection of E.U. customer information.

---

## SOC Assessment

| Best Practice | Meets Practice |
|---|---|
| User access policies are established | No |
| Sensitive data (PII/SPII) is confidential/private | No |
| Data integrity is maintained | Yes |
| Data is available to authorized individuals | No |

### SOC Findings

Botium Toys has controls supporting data integrity. However, weaknesses in user access controls and the protection of PII/SPII create confidentiality concerns. Although data is available to employees, access is not appropriately restricted to individuals who require it for their job responsibilities.
---

## Recommendations

Based on my assessment, I would prioritize remediation according to the potential risk to Botium Toys and its customers.

### Priority 1: Protect Cardholder and Sensitive Data

Botium Toys should restrict access to sensitive information, implement least privilege and separation of duties, strengthen password management, and encrypt sensitive payment information.

### Priority 2: Strengthen Identity and Access Management

User access policies should be established so employees only have access to systems and information necessary for their job responsibilities.

### Priority 3: Improve Detection Capabilities

An intrusion detection system (IDS) should be implemented to improve the organization's ability to identify suspicious or anomalous network activity.

### Priority 4: Establish Business Continuity and Recovery

Botium Toys should establish reliable backups of critical data and develop a documented and tested disaster recovery plan.

### Priority 5: Improve Data Governance and Compliance

Customer information should be properly inventoried and classified. Botium Toys should also continue strengthening controls supporting PCI DSS and GDPR requirements.

---

## Overall Assessment

Botium Toys' risk assessment identified an overall risk score of **8/10**.

The organization has several existing security controls, but significant weaknesses involving access control, cardholder data protection, detection, recovery, and compliance increase its overall exposure.

The highest-priority remediation efforts should focus on protecting sensitive and payment information while reducing the likelihood and potential impact of unauthorized access, data compromise, and business disruption.
