# Change Management Policy

| Field | Detail |
|-------|--------|
| **Document ID** | POL-CMP-005 |
| **Version** | 2.3 |
| **Owner** | IT Manager / Change Advisory Board (CAB) |
| **Effective Date** | [DATE] |

---

## 1. Purpose
This policy governs all changes to IT systems, infrastructure, applications, and configurations to minimise risk of disruption, security incidents, and compliance failures. In regulated environments — particularly **SOX ITGC** and **FFIEC** — change management is one of the most heavily tested IT general controls.

**Core rule: No change to production environment without documented approval.**

---

## 2. Change Types & Process

| Type | Definition | Approval Required | Lead Time |
|------|-----------|------------------|-----------|
| **Standard** | Pre-approved, low-risk, repeatable | CAB pre-approval on record | 0 days |
| **Normal – Minor** | Low risk; limited impact | Line Manager + IT Manager | 5 business days |
| **Normal – Major** | Significant change; potential impact | CAB approval | 10 business days |
| **Emergency** | Critical fix; cannot wait normal cycle | CISO + IT Director (post-facto CAB review) | Immediate |

---

## 3. Change Advisory Board (CAB)

- **Members**: CISO, IT Manager, Business Operations, Risk & Compliance, QA
- **Frequency**: Weekly (normal changes); on-demand (emergency)
- **Quorum**: 3 of 5 members minimum
- **Authority**: Approve, reject, or defer change requests

---

## 4. Change Request Requirements

Every change request must document:
- [ ] **Business justification**: Why is this change needed?
- [ ] **Risk assessment**: What could go wrong? What is the impact?
- [ ] **Rollback plan**: How do we revert if it fails?
- [ ] **Test plan**: How was it tested in non-production?
- [ ] **Maintenance window**: When will it be implemented?
- [ ] **Communication plan**: Who needs to be notified?
- [ ] **Security review**: Does this change affect security controls?

---

## 5. SOX ITGC Change Management Controls

Critical for **SOX compliance** (tested by external auditors):

| Control | Requirement | Evidence |
|---------|-------------|---------|
| **CM-01** | All changes require documented authorisation | Approved change tickets |
| **CM-02** | Segregation of duties: Developer cannot deploy to production | Access logs + role matrix |
| **CM-03** | Changes tested in non-production before deployment | Test evidence + sign-off |
| **CM-04** | Emergency changes reviewed post-facto within 48 hours | Emergency change log + CAB minutes |
| **CM-05** | Change log maintained and reviewed monthly | Change register + review sign-off |
| **CM-06** | Unauthorised changes detected and investigated | SIEM alerts + investigation records |

---

## 6. Sector Notes

### 🏦 Banking (SOX / FFIEC)
- Change management is a **primary SOX ITGC domain** — documented, controlled, and auditable at all times
- **Segregation of duties** is non-negotiable: The person who codes a change cannot promote it to production
- Emergency changes require **retroactive CAB review within 48 hours** and are flagged for SOX auditor review
- Maintain change log for minimum **7 years** (SOX retention)

### ⚡ Energy (NERC CIP-010)
- **CIP-010-4** Configuration Change Management for BES Cyber Systems
- Authorise and document changes before implementation
- Monitor for unauthorised changes on BES Cyber Systems
- Quarterly review of transient cyber asset connections

---
*Owner: IT Manager / CAB | Review: Annual*
