# Business Continuity Policy

| Field | Detail |
|-------|--------|
| **Document ID** | POL-BCP-006 |
| **Version** | 2.1 |
| **Owner** | Risk & Compliance Manager / COO |
| **Effective Date** | [DATE] |

---

## 1. Purpose
This policy establishes requirements to ensure **[ORGANIZATION NAME]** can continue critical business operations and recover IT services in the event of a disruption. It aligns with **ISO 22301:2019** (Business Continuity Management) and sector-specific requirements.

---

## 2. Core Objectives

| Objective | Target |
|-----------|--------|
| Recovery Time Objective (RTO) | Critical systems: ≤4 hours |
| Recovery Point Objective (RPO) | Critical systems: ≤1 hour |
| MBCO (Minimum Business Continuity Objective) | 40% normal capacity within 24 hours |
| Maximum Tolerable Period of Disruption (MTPD) | 72 hours |

---

## 3. Business Impact Analysis (BIA)

### Critical Business Functions (Tier 1 — RTO: 4 hours)
| Function | Systems | RTO | RPO |
|----------|---------|-----|-----|
| Core Banking / Payment Processing | Core banking system, payment gateway | 2 hours | 15 minutes |
| Customer Authentication | IAM, MFA platform | 1 hour | 30 minutes |
| Risk & Compliance Reporting | GRC platform, reporting DB | 4 hours | 1 hour |
| Communication Systems | Email, VoIP, collaboration | 2 hours | 1 hour |

### Important Functions (Tier 2 — RTO: 24 hours)
- HR and payroll systems
- Document management
- ERP/finance systems (non-payment)

### Normal Functions (Tier 3 — RTO: 72 hours)
- Development environments
- Non-critical internal portals
- Training systems

---

## 4. Recovery Strategies

### 4.1 IT Disaster Recovery
- **Hot Standby**: Real-time replication to secondary site (Tier 1 systems)
- **Warm Standby**: Near real-time replication; 2-4 hour activation (Tier 2)
- **Cold Standby**: Backup restoration; 24-72 hour activation (Tier 3)
- **Cloud Failover**: Automated failover to cloud region (IaaS DR approach)

### 4.2 Data Backup Standards
| Data Type | Backup Frequency | Retention | Offsite Copy | Encryption |
|-----------|-----------------|-----------|--------------|------------|
| Critical production data | Continuous / every 15 min | 90 days | ✅ | ✅ AES-256 |
| Important business data | Daily | 1 year | ✅ | ✅ |
| Standard business data | Weekly | 3 years | ✅ | ✅ |
| Archive / compliance data | Monthly | Per regulatory req. | ✅ | ✅ |

---

## 5. Testing Requirements

| Test Type | Frequency | Scope | Pass Criteria |
|-----------|-----------|-------|--------------|
| **Tabletop Exercise** | Quarterly | IR team + business leads | Gaps documented; action plans assigned |
| **Technical Failover Test** | Semi-annual | IT infrastructure | RPO/RTO objectives met |
| **Full DR Test** | Annual | All critical systems | Full production failover; customer impact: zero |
| **Communication Test** | Annual | All staff notification | 100% staff reached within 2 hours |

---

## 6. Sector Requirements

### 🏦 Banking (FFIEC BCP Booklet)
- **FFIEC Business Continuity Management**: Comprehensive BCM programme required
- **Interconnection dependencies**: Document and test all third-party dependencies
- **Pandemic/widespread scenario**: Alternate work location or remote work capability
- BCP tested and **results reported to Board** annually
- Regulatory examination readiness: BCP documentation subject to OCC/Fed review

### ⚡ Energy (NERC CIP / Grid Resilience)
- **CIP-009-6**: Recovery Plans for BES Cyber Systems
- Recovery plan for each BES Cyber System category
- Test at least once every 15 calendar months
- Document and address weaknesses found during testing

---
*Owner: Risk & Compliance Manager | Review: Annual*
