# Information Security Policy

| Field | Detail |
|-------|--------|
| **Document ID** | POL-ISP-001 |
| **Version** | 3.0 |
| **Classification** | Internal |
| **Owner** | Chief Information Security Officer / DPO |
| **Approved By** | [Board / CEO Name] |
| **Effective Date** | [DATE] |
| **Review Date** | Annual (or upon material change) |
| **Replaces** | POL-ISP-002 v2.1 |

---

## 1. Purpose

This Information Security Policy establishes the management direction and support for information security in accordance with business requirements and applicable laws and regulations. It provides the overarching governance framework from which all subsidiary security policies, standards, and procedures derive their authority.

This policy applies universally across **[ORGANIZATION NAME]** and is mandatory for compliance. Failure to comply constitutes a disciplinary matter.

---

## 2. Scope

### 2.1 Organisational Scope
This policy applies to:
- All employees (permanent, temporary, contractual, part-time)
- All third-party vendors, contractors, and service providers with access to organisational information or systems
- All Board members, executives, and senior management
- All subsidiaries and affiliated entities of **[ORGANIZATION NAME]**

### 2.2 Asset Scope
All information assets regardless of format (electronic, physical, verbal) including:
- Information systems, networks, and infrastructure
- Cloud services and hosted platforms
- Endpoint devices (laptops, mobiles, removable media)
- Physical premises and records
- Intellectual property and proprietary data

### 2.3 Geographic Scope
All jurisdictions in which **[ORGANIZATION NAME]** operates, including cross-border data transfers.

---

## 3. Information Security Objectives

**[ORGANIZATION NAME]** commits to the following information security objectives:

| Objective | Measure | Target |
|-----------|---------|--------|
| Protect confidentiality of sensitive data | Data breach incidents | Zero confirmed breaches |
| Maintain integrity of business-critical systems | Unauthorised modification incidents | Zero per quarter |
| Ensure availability of critical systems | System uptime | ≥99.5% for critical systems |
| Ensure regulatory compliance | Audit findings | Zero critical findings |
| Foster security-aware culture | Training completion | 100% annually |
| Manage third-party risk | Vendor assessments completed | 100% of critical vendors annually |

---

## 4. Information Security Principles

All information security decisions and activities at **[ORGANIZATION NAME]** shall be guided by:

### 4.1 Confidentiality
Information shall be disclosed only to authorised individuals on a need-to-know basis. Access rights shall reflect the minimum necessary privilege required to perform job functions.

### 4.2 Integrity
Information shall be protected from unauthorised modification, deletion, or corruption. Change control processes shall be enforced for all production systems and critical data.

### 4.3 Availability
Information systems shall be available to authorised users when required. Business continuity and disaster recovery plans shall be maintained and tested.

### 4.4 Accountability
All access to and use of information systems shall be logged and attributable to an identified individual. Non-repudiation controls shall be implemented for critical transactions.

### 4.5 Compliance
All information security activities shall comply with applicable legal, regulatory, and contractual obligations. Non-compliance shall be reported and remediated promptly.

---

## 5. Information Security Management Framework

### 5.1 Governance Structure

```
Board of Directors
    └── Risk & Audit Committee
            └── Chief Information Security Officer (CISO) / DPO
                    ├── Information Security Manager
                    │       ├── Security Operations
                    │       ├── Vulnerability Management
                    │       └── Incident Response
                    ├── Risk & Compliance Manager
                    │       ├── Policy & Standards
                    │       ├── Third-Party Risk
                    │       └── Audit & Assurance
                    └── Data Protection Officer (DPO)
                            ├── Privacy Compliance
                            └── DSAR Management
```

### 5.2 Management Responsibilities
- **Board**: Approve information security strategy; provide adequate resources
- **CISO/DPO**: Develop, implement, and maintain the ISMS; report to Board quarterly
- **Department Heads**: Ensure policy compliance within their functions
- **All Staff**: Comply with this policy and report security incidents promptly

### 5.3 Information Security Management System (ISMS)
**[ORGANIZATION NAME]** operates an ISMS conforming to ISO/IEC 27001:2022. The ISMS encompasses:
- Risk assessment and treatment methodology
- Statement of Applicability (SoA)
- Security control implementation and monitoring
- Internal audit programme
- Management review cycle

---

## 6. Risk Management

### 6.1 Risk Assessment
Information security risks shall be assessed at minimum annually, and upon:
- Significant organisational change
- Introduction of new systems or services
- Post-incident analysis
- Regulatory or threat landscape changes

### 6.2 Risk Acceptance Criteria
Risk treatment decisions shall follow the organisational risk appetite:

| Risk Level | Score | Treatment Required |
|------------|-------|-------------------|
| Critical | 20–25 | Immediate treatment; Board notification |
| High | 15–19 | Treatment within 30 days; CISO approval |
| Medium | 8–14 | Treatment within 90 days; documented plan |
| Low | 1–7 | Accept with monitoring; documented rationale |

### 6.3 Risk Treatment Options
- **Mitigate**: Implement controls to reduce likelihood or impact
- **Transfer**: Insurance or contractual transfer to third party
- **Avoid**: Discontinue the activity generating the risk
- **Accept**: Formal acceptance with CISO/Risk Committee approval

---

## 7. Policy Requirements by Domain

### 7.1 Access Control
- All access to information systems requires prior authorisation
- Privileged access requires additional approval and enhanced monitoring
- Multi-factor authentication (MFA) is mandatory for all remote access and privileged accounts
- Access rights shall be reviewed quarterly; terminated employee access revoked within 4 hours

### 7.2 Asset Management
- All information assets shall be inventoried and assigned an owner
- Assets shall be classified per the Data Classification Policy (POL-DC-008)
- Physical and logical asset inventories shall be maintained and reconciled quarterly

### 7.3 Cryptography
- All sensitive data at rest and in transit shall be encrypted using approved algorithms
- Minimum standards: AES-256 (at rest), TLS 1.2+ (in transit)
- Cryptographic keys shall be managed per a documented key management procedure

### 7.4 Physical Security
- All data processing facilities shall implement physical access controls
- Visitor access shall be logged, escorted, and time-limited
- Clean desk policy is mandatory for all staff handling sensitive information

### 7.5 Operations Security
- Production, test, and development environments shall be segregated
- Change management controls shall be applied to all production changes
- Capacity management reviews shall be conducted quarterly

### 7.6 Network Security
- Network segmentation shall be implemented to separate critical systems
- All network traffic shall be monitored; anomalies reported to SOC
- Remote access shall use approved VPN with MFA enforcement

### 7.7 Supplier Relationships
- All suppliers with access to organisational data or systems shall sign a confidentiality agreement and data processing agreement
- Critical suppliers shall undergo annual security assessments
- Refer to Vendor Risk Management Policy (POL-VRM-007)

### 7.8 Incident Management
- All security incidents shall be reported within 1 hour of detection
- A documented Incident Response Plan shall be maintained and tested annually
- Refer to Incident Response Policy (POL-IRP-004)

### 7.9 Business Continuity
- Business continuity plans shall be maintained for all critical processes
- Recovery Time Objectives (RTO) and Recovery Point Objectives (RPO) shall be defined
- Refer to Business Continuity Policy (POL-BCP-006)

### 7.10 Compliance
- Legal, regulatory, and contractual requirements shall be identified, documented, and complied with
- Internal audits shall be conducted annually
- Results shall be reported to senior management and the Board

---

## 8. Sector-Specific Requirements

### 🏦 Banking & Financial Services (BFSI)
> Applicable to: US T1 Banks, Indian BFSI regulated entities

- Align with **FFIEC IT Handbook** (Operations, Audit, Business Continuity Booklets)
- Comply with **OCC Heightened Standards** (12 CFR Part 30, Appendix D) for large national banks
- **RBI Master Directions** on IT Risk and Cybersecurity Framework (India)
- **SEBI CSCRF** (Cyber Security & Cyber Resilience Framework) for market infrastructure
- Conduct **Technology Risk Assessment** per RBI guidelines annually
- Maintain **Cyber Crisis Management Plan** aligned to CERT-In requirements

### 🛡️ Defence & National Security
> Applicable to: Defence contractors, government agencies, critical infrastructure

- Align with **NIST SP 800-171** (Protecting CUI in Nonfederal Systems)
- **CMMC Level 2+** requirements for DoD supply chain participants
- **DRDO/MoD** information assurance requirements for Indian defence context
- **ITAR/EAR** compliance for defence technology exports
- Implement **Need-to-Know** and **Compartmentalisation** controls for classified information
- Mandatory **background verification** for all personnel with access to sensitive systems

### ⚡ Energy & Critical Infrastructure
> Applicable to: Power generation, transmission, oil & gas, utilities

- Align with **NERC CIP** standards (CIP-002 through CIP-014) for bulk electric systems
- **IEC 62443** (Industrial Cybersecurity) for OT/SCADA environments
- **TSA Security Directives** for pipeline cybersecurity (USA)
- Maintain **IT/OT network segregation** with documented interface controls
- **Consequence-based cyber-informed engineering** (C2E) risk approach
- Critical asset identification and **Electronic Security Perimeter (ESP)** controls

### 🏥 Healthcare
> Applicable to: Hospitals, health insurers, healthcare IT, life sciences

- **HIPAA Security Rule** (45 CFR Parts 160 and 164) mandatory compliance
- **HITRUST CSF** alignment for comprehensive healthcare security
- **FDA 21 CFR Part 11** for electronic records in clinical systems
- **Protected Health Information (PHI)** handling controls
- **Business Associate Agreements (BAA)** required for all PHI-handling vendors

### 💻 Technology & Cloud
> Applicable to: SaaS, cloud providers, IT consulting, software companies

- **SOC 2 Type II** (Trust Service Criteria) alignment
- **CSA CCM v4.0** for cloud security controls
- **FedRAMP** requirements for US Government cloud services
- **ISO/IEC 27017** and **27018** for cloud-specific controls
- **Secure SDLC** requirements per OWASP and NIST SSDF

---

## 9. Human Resource Security

### 9.1 Pre-Employment
- Background checks proportionate to role sensitivity
- Reference verification for all positions
- Security awareness training within first week of employment

### 9.2 During Employment
- Annual mandatory security awareness training (100% completion required)
- Role-based security training for technical and privileged roles
- Security performance KPIs for IT and security staff

### 9.3 Termination
- Access revocation checklist mandatory for all leavers
- Return of assets within final working day
- Exit interviews to identify potential data exfiltration risks

---

## 10. Policy Exceptions

All exceptions to this policy require:
1. Written justification from the requestor
2. Risk assessment by the Information Security team
3. Approval from CISO
4. Time-limited duration (maximum 90 days; renewable with justification)
5. Compensating controls defined and implemented
6. Logging in the Policy Exception Register

*Use form: [templates/policy-exception-request.md](../templates/policy-exception-request.md)*

---

## 11. Violations & Disciplinary Action

| Severity | Examples | Consequence |
|----------|----------|-------------|
| Minor | First-time AUP violation, clean desk failure | Verbal warning + retraining |
| Moderate | Repeated violations, sharing credentials | Written warning + disciplinary review |
| Major | Intentional data exfiltration, sabotage | Immediate termination + legal action |
| Regulatory | Breach leading to regulatory incident | Termination + regulatory reporting + potential prosecution |

---

## 12. Policy Review

This policy shall be reviewed:
- **Annually** (minimum) by the CISO and Risk Committee
- **Immediately** following a significant security incident
- **Upon** major regulatory, legal, or organisational change

All revisions require Board approval for changes to Section 5 (Governance) and Management approval for all other sections.

---

## 13. Related Documents

| Document | Reference |
|----------|-----------|
| Acceptable Use Policy | POL-AUP-002 |
| Access Control Policy | POL-ACP-003 |
| Incident Response Policy | POL-IRP-004 |
| Change Management Policy | POL-CMP-005 |
| Business Continuity Policy | POL-BCP-006 |
| Vendor Risk Management Policy | POL-VRM-007 |
| Data Classification Policy | POL-DC-008 |
| Risk Assessment Methodology | METH-RA-001 |

---

## 14. Control Mapping

### ISO/IEC 27001:2022 Annex A
| This Policy Section | ISO 27001 Controls |
|--------------------|-------------------|
| §5 – Governance | A.5.1, A.5.2, A.5.3, A.5.4 |
| §6 – Risk Management | A.5.5, A.5.6, A.5.7, A.5.8 |
| §7.1 – Access Control | A.5.15–A.5.18, A.8.2–A.8.6 |
| §7.2 – Asset Management | A.5.9, A.5.10, A.5.11, A.5.12 |
| §7.3 – Cryptography | A.8.24, A.8.25 |
| §7.5 – Operations | A.8.8–A.8.22 |
| §7.6 – Network Security | A.8.20, A.8.21, A.8.22 |
| §7.7 – Supplier Relationships | A.5.19–A.5.23 |
| §7.8 – Incident Management | A.5.24–A.5.28 |
| §7.9 – Business Continuity | A.5.29, A.5.30 |
| §7.10 – Compliance | A.5.31–A.5.36 |

### NIST CSF 2.0
| This Policy Section | NIST Function/Category |
|--------------------|----------------------|
| §5 – Governance | GV.OC, GV.RM, GV.RR, GV.PO |
| §6 – Risk Management | ID.RA, GV.RM |
| §7.1 – Access Control | PR.AA |
| §7.5 – Operations | PR.DS, PR.PS |
| §7.8 – Incidents | RS.MA, RS.AN, RS.MI |
| §7.9 – Business Continuity | RC.RP, RC.CO |

---

*Document Classification: Internal | This policy is proprietary to [ORGANIZATION NAME] and must not be distributed externally without authorization.*
