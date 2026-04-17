# Data Classification Policy

| Field | Detail |
|-------|--------|
| **Document ID** | POL-DC-008 |
| **Version** | 1.8 |
| **Owner** | DPO / Information Security Manager |
| **Effective Date** | [DATE] |

---

## 1. Purpose
This policy establishes a framework for classifying **[ORGANIZATION NAME]** information assets to ensure appropriate protection controls are applied proportionate to the value and sensitivity of information.

---

## 2. Classification Levels

| Level | Label | Description | Examples |
|-------|-------|-------------|----------|
| **Level 4** | 🔴 RESTRICTED / SECRET | Highest sensitivity; disclosure causes severe harm | Cryptographic keys, Board M&A plans, national security data, ePHI/PII of special categories |
| **Level 3** | 🟠 CONFIDENTIAL | Sensitive; limited distribution; regulatory obligations apply | PII, financial records, audit reports, system architecture, employee records |
| **Level 2** | 🟡 INTERNAL** | For internal use; not for public disclosure | Policies, procedures, internal communications, project plans |
| **Level 1** | 🟢 PUBLIC | Approved for public distribution | Marketing materials, published reports, job postings |

---

## 3. Handling Requirements by Classification

| Control | RESTRICTED | CONFIDENTIAL | INTERNAL | PUBLIC |
|---------|-----------|--------------|----------|--------|
| **Storage – at rest** | AES-256 encrypted; access-controlled vault | AES-256 encrypted | Standard ACL | Unrestricted |
| **Storage – cloud** | Private; dedicated tenant only | Private cloud / tenancy isolation | Standard cloud | Any |
| **Transmission** | TLS 1.3 + end-to-end encryption | TLS 1.2+ | TLS 1.2+ | Any |
| **Email** | Encrypted email (S/MIME) only; no forwarding | Encrypted preferred | Standard email | Standard |
| **Printing** | Prohibited unless formally authorised | Secure print; label required | Standard | Standard |
| **Disposal** | NIST 800-88 DoD 7-pass wipe; witnessed | DoD 3-pass wipe | Standard delete | Any |
| **Sharing** | Need-to-know; approval required | Minimum necessary; NDA | Internal staff | Unrestricted |
| **Labelling** | Mandatory header/footer on all pages | Mandatory | Recommended | Optional |
| **Mobile devices** | Prohibited; no exceptions without CISO approval | MDM enrolled + encrypted | MDM enrolled | Any |
| **Retention** | Per legal/regulatory requirement | Per retention schedule | Per retention schedule | As published |

---

## 4. Sector Data Classification Overlays

### 🏦 Banking (PCI DSS / FFIEC)
| Data Type | Classification | Regulatory Reference |
|-----------|---------------|---------------------|
| Cardholder Data (PAN, CVV, PIN) | **RESTRICTED** | PCI DSS Req. 3 |
| Customer account information | **CONFIDENTIAL** | GLBA, OCC |
| SWIFT/wire transaction data | **RESTRICTED** | SWIFT CSP |
| Internal financial models | **CONFIDENTIAL** | — |

### 🛡️ Defence (CUI / Classified)
| Data Type | Classification | Reference |
|-----------|---------------|-----------|
| Classified National Security Information | **SECRET/TS** *(Govt classification)* | EO 13526 |
| Controlled Unclassified Information (CUI) | **RESTRICTED** (equivalent) | NIST 800-171 |
| Sensitive But Unclassified (SBU) | **CONFIDENTIAL** | — |

### 🏥 Healthcare (HIPAA)
| Data Type | Classification | Reference |
|-----------|---------------|-----------|
| ePHI (Electronic Protected Health Information) | **RESTRICTED** | HIPAA §164.306 |
| De-identified health data | **INTERNAL** | HIPAA §164.514 |

### 🇮🇳 India (DPDPA 2023)
| Data Type | Classification | Reference |
|-----------|---------------|-----------|
| Personal Data | **CONFIDENTIAL** minimum | DPDPA §2(t) |
| Sensitive Personal Data | **RESTRICTED** | DPDPA §2(t) + Rules |

---

## 5. Data Labelling Format

```
Document Header/Footer Format:
[ORGANISATION NAME] | CLASSIFICATION: [LEVEL] | DOC-ID: [ID] | v[VERSION]
RESTRICTED — Authorised Recipients Only: [Names/Roles]
```

---

## 6. Control Mapping

| ISO 27001:2022 | NIST CSF | PCI DSS |
|---------------|----------|---------|
| A.5.9, A.5.10, A.5.11, A.5.12, A.8.10 | PR.DS-01, PR.DS-02 | Req 3, 4, 9 |

---
*Owner: DPO / Information Security Manager | Review: Annual*
