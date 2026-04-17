# Vendor & Third-Party Risk Management Policy

| Field | Detail |
|-------|--------|
| **Document ID** | POL-VRM-007 |
| **Version** | 2.1 |
| **Classification** | Internal |
| **Owner** | Risk & Compliance Manager / Procurement |
| **Effective Date** | [DATE] |
| **Review Date** | Annual |

---

## 1. Purpose

This policy establishes requirements for identifying, assessing, managing, and monitoring risks associated with third-party vendors, suppliers, and service providers who have access to **[ORGANIZATION NAME]** information, systems, facilities, or who provide critical business services.

Third-party risk is one of the **top-5 cybersecurity risks** facing regulated organisations globally. A single compromised vendor can expose an entire supply chain — as demonstrated by SolarWinds (2020), Kaseya (2021), and MOVEit (2023).

---

## 2. Scope

This policy applies to all third parties including:
- IT and technology service providers
- Cloud service providers (IaaS, PaaS, SaaS)
- Managed security service providers (MSSPs)
- Professional services firms (legal, audit, consulting)
- Payroll and HR service providers
- Data processors and data sub-processors
- Physical security and facilities vendors
- Supply chain and logistics partners

---

## 3. Vendor Tiering Model

All vendors shall be classified based on risk profile:

| Tier | Criteria | Assessment Frequency | Due Diligence Level |
|------|----------|---------------------|---------------------|
| **Tier 1 – Critical** | Accesses sensitive/regulated data; provides critical services; single point of failure | **Annual onsite/detailed** | Full assessment + contract review + ongoing monitoring |
| **Tier 2 – High** | Accesses internal data; provides important (non-critical) services | **Annual questionnaire** | Detailed questionnaire + contract review |
| **Tier 3 – Medium** | Limited data access; standard commercial services | **Bi-annual questionnaire** | Standard questionnaire |
| **Tier 4 – Low** | No data access; commodity services | **Upon onboarding only** | Basic verification |

### Automatic Tier 1 Classification Triggers
- Access to PII of >1,000 data subjects
- Access to financial transaction systems
- Cloud providers storing regulated data (PHI, PCI, CUI)
- Vendors with remote access to production environments
- Critical infrastructure dependencies (single vendor, no alternative)

---

## 4. Vendor Onboarding Process

### Phase 1: Pre-Engagement (Before Contract Signing)
- [ ] **Vendor Tiering Assessment** completed
- [ ] **Security questionnaire** sent and responses reviewed
- [ ] **Financial stability check** (Tier 1 vendors)
- [ ] **Regulatory compliance verification** (relevant certifications: ISO 27001, SOC 2, PCI DSS)
- [ ] **Sanctions screening** (OFAC, UK HMT, EU sanctions lists)
- [ ] **Business continuity capability** assessed
- [ ] **Sub-contractor disclosure** obtained

### Phase 2: Contract & Legal (Before Go-Live)
- [ ] **Data Processing Agreement (DPA)** / Data Processing Addendum executed
- [ ] **Confidentiality/NDA** signed
- [ ] **Right-to-audit clause** included (Tier 1 and 2)
- [ ] **Security requirements** appended to contract
- [ ] **Incident notification SLA** defined (≤72 hours for personal data breaches)
- [ ] **Data return/deletion obligations** upon termination
- [ ] **Business Associate Agreement (BAA)** — Healthcare only

### Phase 3: Technical Onboarding
- [ ] Access provisioned per Access Control Policy (POL-ACP-003)
- [ ] VPN/secure access configured (if applicable)
- [ ] Monitoring enabled for vendor access sessions
- [ ] Vendor contacts registered in Third-Party Register

---

## 5. Ongoing Monitoring

### 5.1 Continuous Monitoring Controls
| Control | Method | Frequency |
|---------|--------|-----------|
| Security rating monitoring | BitSight / SecurityScorecard / UpGuard | Continuous |
| Vendor access log review | SIEM correlation | Weekly |
| Certification validity | Automated expiry tracking | Ongoing |
| Dark web monitoring | Threat intelligence feeds | Continuous |
| News/incident monitoring | OSINT / threat intel | Weekly |

### 5.2 Periodic Reviews
| Review Type | Tier 1 | Tier 2 | Tier 3 |
|-------------|--------|--------|--------|
| Security questionnaire | Annual | Annual | Bi-annual |
| Onsite assessment | Annual | As needed | — |
| Contract review | Annual | At renewal | At renewal |
| Access review | Quarterly | Quarterly | Annual |
| Financial health review | Annual | At renewal | — |

---

## 6. Incident & Breach Response — Third Party

### 6.1 Vendor Incident Notification Requirements
Vendors must notify **[ORGANIZATION NAME]** within:
- **4 hours**: Confirmed breach of personal data or regulated information
- **24 hours**: Suspected breach or security incident affecting shared systems
- **72 hours**: Any security event affecting service availability

### 6.2 Internal Response on Third-Party Incident
1. Validate notification and assess impact on organisation
2. Invoke Incident Response Plan (POL-IRP-004) if organisational data affected
3. Isolate vendor access if containment required
4. Notify DPO/Legal within 2 hours if personal data potentially affected
5. Regulatory notification per applicable framework (GDPR: 72 hours to supervisory authority)

---

## 7. Sector-Specific Requirements

### 🏦 US T1 Banking — OCC Guidance (OCC 2023-17, SR 13-19)
- **Heightened Standards** apply to all critical activities outsourced by large national banks
- **Board-level oversight** of critical third-party relationships required
- **Concentration risk assessment**: Identify vendors providing services to multiple banks
- **Exit/contingency planning** for all Tier 1 vendors mandatory
- **OCC examination readiness**: Third-party risk programme subject to examiner review
- Document: Business case, due diligence, contract, ongoing monitoring, termination plan

### 🛡️ Defence — DFARS/CMMC Supply Chain
- All vendors processing **CUI** must meet NIST SP 800-171 requirements
- **CMMC Level 2** minimum for vendors in the DIB (Defence Industrial Base)
- **Flow-down requirements**: Prime contractors must flow CMMC requirements to sub-contractors
- **Supply chain risk management (SCRM)** per NIST SP 800-161r1
- Foreign ownership, control, or influence (**FOCI**) assessment required

### ⚡ Energy — NERC CIP-013 (Supply Chain Risk)
- **CIP-013-2** Supply Chain Cyber Security Risk Management Plan mandatory for BES
- Identify and assess cyber security risks from vendor equipment and services
- Controls for: Software integrity, vendor remote access, notification of vendor incidents
- Annual review of supply chain risk management plan

### 🏥 Healthcare — HIPAA Business Associates
- **BAA mandatory** for all vendors accessing, storing, or transmitting PHI
- BAA must include: Permitted uses, safeguards, breach notification, sub-contractor requirements
- Vendor must comply with HIPAA Security Rule independently
- Annual vendor HIPAA compliance attestation recommended

---

## 8. Third-Party Register

All vendors shall be recorded in the **Third-Party Vendor Register** with:

| Field | Description |
|-------|-------------|
| Vendor ID | Unique identifier (VND-XXXX) |
| Vendor Name | Legal entity name |
| Service Category | Type of service provided |
| Tier Classification | 1 / 2 / 3 / 4 |
| Data Access | Types of data accessed |
| Certifications | ISO 27001, SOC 2, PCI DSS, etc. |
| Contract Expiry | Next renewal date |
| Assessment Due | Next assessment date |
| Account Manager | Internal relationship owner |
| Risk Score | Current risk rating |
| Watch Status | Any active concerns |

---

## 9. Vendor Offboarding

Upon termination or non-renewal:
- [ ] All access revoked on termination date
- [ ] Data return / deletion confirmed in writing within 30 days
- [ ] Confidentiality obligations confirmed as surviving termination
- [ ] Keys and credentials rotated
- [ ] Vendor removed from Third-Party Register (archived with termination date)
- [ ] Post-termination monitoring period: 90 days for Tier 1 vendors

---

## 10. Control Mapping

| This Section | ISO 27001:2022 | NIST CSF 2.0 | OCC |
|-------------|---------------|--------------|-----|
| §3 – Tiering | A.5.19 | GV.SC-06 | Third-Party Risk Mgmt |
| §4 – Onboarding | A.5.20, A.5.21 | GV.SC-04, GV.SC-05 | Due Diligence |
| §5 – Monitoring | A.5.22 | GV.SC-07, GV.SC-08 | Ongoing Monitoring |
| §6 – Incident | A.5.23, A.5.26 | RS.MA-04 | Incident Response |
| §9 – Offboarding | A.5.20 | GV.SC-09 | Contract Termination |

---

*Review Schedule: Annual | Owner: Risk & Compliance Manager*
