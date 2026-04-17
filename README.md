# 📋 IT GRC Policy Library
> **Enterprise-grade IT Governance, Risk & Compliance policy templates — battle-tested across BFSI, US T1 Banking, Defence, Energy, Healthcare, and Technology sectors.**

[![ISO 27001](https://img.shields.io/badge/ISO_27001-Aligned-green?style=flat-square)](https://www.iso.org/isoiec-27001-information-security.html)
[![NIST CSF](https://img.shields.io/badge/NIST_CSF-2.0_Aligned-blue?style=flat-square)](https://www.nist.gov/cyberframework)
[![COBIT](https://img.shields.io/badge/COBIT-2019_Mapped-orange?style=flat-square)](https://www.isaca.org/resources/cobit)
[![PCI DSS](https://img.shields.io/badge/PCI_DSS-v4.0_Referenced-red?style=flat-square)](https://www.pcisecuritystandards.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)
[![Maintained](https://img.shields.io/badge/Maintained-Yes-brightgreen?style=flat-square)]()

---

## 🎯 About This Repository

This library contains **production-ready IT GRC policy templates** developed from real-world engagements across:

- 🏦 **US Tier 1 Banking** — FFIEC, OCC, SOX ITGC compliant
- 🏗️ **BFSI** — RBI, SEBI, IRDAI regulatory alignment
- 🛡️ **Defence** — DRDO/MoD, CMMC, NIST 800-171 alignment
- ⚡ **Energy/OT** — NERC CIP, IEC 62443 considerations
- 🏥 **Healthcare** — HIPAA Security Rule aligned
- 💻 **Technology/Cloud** — CSA CCM, FedRAMP, SOC 2 ready

**What makes this library different:**
- Templates are written from *actual audit and implementation experience*, not theoretical frameworks
- Every policy includes **sector-specific applicability notes**
- **Control mapping tables** link each policy to 5+ major frameworks
- **Gap analysis checklists** included for immediate use

---

## 📁 Repository Structure

```
itgrc-policy-library/
├── policies/                    # Core policy templates (8 domains)
│   ├── information-security-policy.md
│   ├── acceptable-use-policy.md
│   ├── access-control-policy.md
│   ├── incident-response-policy.md
│   ├── change-management-policy.md
│   ├── business-continuity-policy.md
│   ├── vendor-risk-management-policy.md
│   └── data-classification-policy.md
├── frameworks/                  # Control mapping & framework guides
│   ├── iso27001-annex-a-mapping.md
│   ├── nist-csf-2.0-mapping.md
│   ├── cobit-2019-mapping.md
│   └── sector-regulatory-matrix.md
├── templates/                   # Supporting document templates
│   ├── policy-review-log.md
│   ├── policy-exception-request.md
│   └── policy-acknowledgement-form.md
└── README.md
```

---

## 🏦 Sector Coverage Matrix

| Policy | BFSI/Banking | Defence | Energy | Healthcare | Tech/Cloud |
|--------|:---:|:---:|:---:|:---:|:---:|
| Information Security | ✅ RBI/SEBI/OCC | ✅ DRDO/CMMC | ✅ NERC CIP | ✅ HIPAA | ✅ SOC 2 |
| Access Control | ✅ FFIEC | ✅ NIST 800-171 | ✅ IEC 62443 | ✅ HIPAA §164 | ✅ CSA CCM |
| Incident Response | ✅ FFIEC IR | ✅ NIST 800-61 | ✅ NERC CIP-008 | ✅ HIPAA Breach | ✅ FedRAMP |
| Change Management | ✅ SOX ITGC | ✅ CM-3 NIST | ✅ IEC 62443-2 | ✅ HITRUST | ✅ ITIL |
| Vendor Risk | ✅ OCC 2023-17 | ✅ DFARS | ✅ NERC CIP-013 | ✅ BAA | ✅ ISO 27036 |
| BCP/DR | ✅ FFIEC BCP | ✅ COOP Plans | ✅ Grid Resilience | ✅ HIPAA §164.308 | ✅ ISO 22301 |
| Data Classification | ✅ PCI DSS | ✅ CUI/SBU | ✅ OT Data | ✅ PHI/ePHI | ✅ GDPR/CCPA |

---

## 🚀 How to Use These Templates

### For Organisations Starting from Scratch
1. Start with `information-security-policy.md` — the parent policy
2. Customize the `[ORGANIZATION NAME]`, `[DATE]`, `[VERSION]` placeholders
3. Review the **Applicability** section for your sector
4. Use the **Control Mapping** table at the bottom to demonstrate compliance

### For Audit/Assessment Purposes
1. Use `frameworks/iso27001-annex-a-mapping.md` to map your controls
2. Check `frameworks/sector-regulatory-matrix.md` for your regulatory obligations
3. Run gap analysis using the checklists in each policy document

### For Consultants
- All templates are designed to be client-ready with minimal customization
- Sector notes are clearly marked — remove inapplicable sections
- Version control fields are included for change management

---

## 📊 Framework Alignment Summary

| Framework | Coverage | Key Policies |
|-----------|----------|--------------|
| ISO/IEC 27001:2022 | **Full Annex A** (93 controls) | All 8 policies |
| NIST CSF 2.0 | **6 Functions** (Govern, Identify, Protect, Detect, Respond, Recover) | All 8 policies |
| COBIT 2019 | **40 Objectives** mapped | All 8 policies |
| PCI DSS v4.0 | **12 Requirements** | Access, Incident, Data Classification |
| FFIEC IT Handbook | **Operations, Audit, Management** | BCP, Change Mgmt, Vendor Risk |
| NIST SP 800-171 | **110 Controls** | Access Control, Incident Response |
| HIPAA Security Rule | **Administrative, Physical, Technical** | All policies + HIPAA notes |
| GDPR/CCPA/DPDPA | **Data Protection** obligations | Data Classification, Vendor Risk |

---

## ✍️ About the Author

**Akshaya** | Sr. Manager, Risk & Compliance | Appointed DPO | ISO 27001 & 27701 Lead Auditor | CIAP (DRDO/MoD)

These templates are derived from real GRC implementations across BFSI, IT consulting, software engineering, data science, and technology staffing verticals. Every control mapping has been validated in live audit environments including US Tier 1 Banking engagements.

> *"I don't just audit programs — I build them from zero. These templates represent what actually works in regulated environments, not what looks good on paper."*

---

## 📬 Connect

- 🌐 Portfolio: [Akshaya-grc.netlify.app](https://Akshaya-grc.netlify.app)
- 💼 LinkedIn: [linkedin.com/in/Akshaya-grc](https://linkedin.com/in/Akshaya-grc)
- 📧 Consulting: akshayshrm39@gmail.com

---

## ⚠️ Disclaimer

These templates are provided for educational and reference purposes. They should be reviewed and customized by qualified professionals before deployment. The author assumes no liability for direct implementation without professional assessment.

---

*⭐ If this library is useful, please star the repository — it helps other GRC practitioners find it.*
