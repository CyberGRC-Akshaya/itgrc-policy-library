# Incident Response Policy

| Field | Detail |
|-------|--------|
| **Document ID** | POL-IRP-004 |
| **Version** | 2.2 |
| **Classification** | Internal – Restricted |
| **Owner** | CISO / Security Operations Manager |
| **Effective Date** | [DATE] |
| **Review Date** | Annual + post-incident |

---

## 1. Purpose & Philosophy

This policy establishes the framework for **detecting, containing, eradicating, and recovering** from information security incidents. Speed and precision are paramount — the average cost of a data breach in 2024 is **$4.88 million** (IBM Cost of Data Breach Report). Every hour of delayed response multiplies that cost.

**Core principle**: Assume breach. Prepare for it. Respond faster than the attacker can pivot.

---

## 2. Incident Classification

### Severity Matrix

| Severity | Definition | Initial Response SLA | Examples |
|----------|-----------|---------------------|----------|
| **P1 – Critical** | Major breach; significant operational disruption; regulatory impact | **15 minutes** | Ransomware active; confirmed data exfiltration; core banking system down |
| **P2 – High** | Significant threat; potential data exposure; active attacker | **1 hour** | Malware detected; privileged account compromised; DDoS underway |
| **P3 – Medium** | Contained incident; limited impact; potential escalation | **4 hours** | Phishing email clicked (no payload); policy violation; unauthorised device |
| **P4 – Low** | Minor violation; no immediate risk | **24 hours** | Lost unencrypted USB; suspicious email (unclicked); access anomaly |

### Regulatory Classification Overlay
| Incident Type | Regulatory Notification Required |
|---------------|----------------------------------|
| Personal data breach (EU/UK) | GDPR Supervisory Authority within **72 hours** |
| Personal data breach (India) | CERT-In within **6 hours**; DPDPA Board TBD |
| Healthcare data breach (US) | OCR within **60 days**; if >500 records → media notification |
| Financial system breach | OCC / Federal Reserve / FDIC — per examination guidance |
| Critical infrastructure | CISA within **72 hours** (CIRCIA, USA) |
| Cybersecurity incident | CERT-In within **6 hours** (India) |

---

## 3. Incident Response Team

### 3.1 Core IR Team (Always Activated for P1/P2)
| Role | Responsibility |
|------|---------------|
| **Incident Commander** | Overall coordination; stakeholder communication; escalation decisions |
| **Lead Analyst** | Technical investigation; forensic analysis; containment execution |
| **Security Operations** | SIEM monitoring; log analysis; IOC extraction |
| **IT Infrastructure** | System isolation; backup activation; recovery |
| **Legal/Compliance** | Regulatory notification; legal holds; evidence preservation |
| **DPO** | Personal data breach assessment; supervisory authority notification |
| **Communications** | Internal communications; external statement management |

### 3.2 Extended Team (Activated as Required)
- HR: Employee-related incidents
- Finance: Financial fraud; BEC incidents
- Executive Leadership: P1 incidents; incidents with media implications
- External Forensics: Third-party IR support (pre-contracted retainer recommended)
- Law Enforcement Liaison: Criminal incidents

---

## 4. Incident Response Lifecycle

### Phase 1: PREPARATION
*Before an incident occurs*

- [ ] Maintain up-to-date asset inventory (critical systems identified)
- [ ] IR playbooks for top-5 threat scenarios maintained
- [ ] IR team contacts list updated quarterly
- [ ] Forensic tools available and tested (disk imaging, memory acquisition, log collection)
- [ ] Secure communications channel established (Signal / encrypted email for IR team)
- [ ] Legal holds procedure documented
- [ ] External IR retainer in place (Tier 1 banking: mandatory)
- [ ] Tabletop exercises: Minimum annual; quarterly for financial services

### Phase 2: IDENTIFICATION
*Detecting and validating an incident*

**Detection Sources:**
- SIEM alerts (log correlation, behavioural analytics)
- EDR/antivirus alerts
- User reports (phishing, suspicious activity)
- Threat intelligence feeds
- Third-party notification
- Dark web monitoring alerts

**Identification Checklist:**
- [ ] Validate alert — distinguish incident from false positive
- [ ] Collect initial evidence (screenshots, log exports) without altering
- [ ] Assign severity (P1/P2/P3/P4) per Section 2
- [ ] Activate appropriate IR team
- [ ] Open incident ticket; assign unique ID: INC-YYYY-NNNN
- [ ] Notify Incident Commander within classification SLA

### Phase 3: CONTAINMENT
*Stop the bleeding*

**Short-Term Containment (Within 1 Hour for P1):**
- Isolate affected systems (network quarantine / VLAN isolation)
- Disable compromised accounts
- Block attacker IP/domain at firewall/proxy
- Preserve volatile evidence before isolation (memory dump, running processes)

**Long-Term Containment (P1 within 4 hours):**
- Segment affected network zones
- Deploy enhanced monitoring on neighbouring systems
- Implement emergency access controls
- Activate backup/failover systems if primary compromised

**⚠️ Evidence Preservation Rules:**
- Do NOT wipe systems before forensic imaging
- Do NOT delete logs or modify any file timestamps
- Capture: Running processes, network connections, memory, disk image
- Chain of custody documentation mandatory for P1/P2

### Phase 4: ERADICATION
*Remove the threat*

- [ ] Root cause identified and documented
- [ ] All malware/implants removed (confirmed by forensic analysis, not just AV scan)
- [ ] All attacker persistence mechanisms removed (scheduled tasks, registry keys, backdoors)
- [ ] Compromised credentials reset across all systems
- [ ] Vulnerability exploited is patched or mitigated
- [ ] Verify no lateral movement to other systems (threat hunter review)

### Phase 5: RECOVERY
*Restore operations safely*

- [ ] Restore from clean, verified backups (not from potentially compromised backup sets)
- [ ] Validate system integrity before returning to production
- [ ] Implement additional monitoring for minimum **30 days** post-incident
- [ ] Phased restoration — critical systems first, per BCP priority order
- [ ] Stakeholder sign-off before full production restoration
- [ ] Post-recovery security scan completed

### Phase 6: POST-INCIDENT REVIEW (PIR)
*Learn and improve*

**Timing:** Within 5 business days (P1), 10 business days (P2/P3)

**PIR Report Must Include:**
- Incident timeline (minute-by-minute for P1)
- Root cause analysis (5-whys or fishbone)
- What worked well in the response
- What needs improvement
- Recommended improvements with owners and deadlines
- Updated threat intelligence based on attacker TTPs
- Lessons learned shared with sector ISAC (if applicable)

---

## 5. Ransomware Response Playbook

*Given the frequency and severity of ransomware attacks on all sectors*

### Immediate Actions (First 30 Minutes)
```
DETECT ransomware indicators:
  - Mass file encryption (unusual I/O spike)
  - Ransom note files appearing
  - Shadow copy deletion attempts (vssadmin.exe)
  - LOLBin execution (PowerShell, WMI, certutil anomalies)

CONTAIN immediately:
  1. Isolate affected host(s) — pull network cable / disable NIC
  2. Do NOT power off (preserve volatile evidence)
  3. Notify Incident Commander: P1 escalation
  4. Block C2 IPs/domains at perimeter (from threat intel feeds)
  5. Identify and isolate all systems with active file shares to affected host

PRESERVE:
  1. Memory dump of affected system(s)
  2. Export SIEM logs for past 72 hours
  3. Screenshot ransom note (do not interact)
  4. Note exact encryption extension used (identifies ransomware family)
```

### Do NOT:
- Pay ransom without legal/executive/law enforcement consultation
- Restore from backup until all attacker persistence is confirmed removed
- Rebuild systems in the same environment without isolation

---

## 6. Sector-Specific IR Requirements

### 🏦 US T1 Banking
- **Cyber incident notification**: OCC/Federal Reserve/FDIC within **36 hours** of determining an incident that materially disrupts or degrades operations or impairs the ability to deliver services (12 CFR 53, 12 CFR 225)
- **FFIEC Cybersecurity Assessment Tool**: IR capability maturity assessed annually
- **Business continuity activation**: Automatic trigger for P1 incidents affecting core systems
- Maintain **pre-approved communication templates** for customer, regulator, media
- **SWIFT CSP** requirements if connected to SWIFT network

### 🛡️ Defence
- **DFARS 252.204-7012**: Report cyber incidents to DoD within **72 hours**
- Submit **malware samples** to DIBNet portal
- Preserve images of all compromised systems for minimum **90 days**
- **CMMC** incident response requirements per domain IR (3.6.1, 3.6.2)
- Coordinate with **CISA** and relevant CERT for nation-state attribution

### ⚡ Energy / NERC CIP
- **CIP-008-6**: Cybersecurity Incident Response Plan mandatory for BES
- **E-ISAC notification** for cybersecurity incidents affecting BES
- **NERC reportable incident criteria**: Impact on BES reliability
- OT/ICS incident handling: Separate playbook required (air-gapped environments)

### 🏥 Healthcare / HIPAA
- **Breach notification rule**: 60 days from discovery to notify individuals
- If breach affects ≥500 residents of a state: Notify prominent media outlets
- **Annual HHS OCR reporting** of breaches affecting <500 individuals
- Maintain breach documentation for **6 years**

---

## 7. Communication Templates

### Internal P1 Alert (Send within 15 minutes)
```
SUBJECT: [P1 SECURITY INCIDENT] INC-[YEAR]-[ID] — [Brief Description]

INCIDENT COMMANDER: [Name]
SEVERITY: P1 – Critical
DETECTED: [Time/Date]
SYSTEMS AFFECTED: [Preliminary list]
CURRENT STATUS: [Containment underway / Investigating / Contained]

IMMEDIATE ACTIONS TAKEN:
- [Action 1]
- [Action 2]

NEXT UPDATE: [Time] (every 30 minutes until contained)

JOIN BRIDGE: [Conference bridge / Slack war room details]
```

### Regulatory Notification Template (GDPR — 72 Hour)
```
To: [Supervisory Authority]
Subject: Personal Data Breach Notification — Article 33 GDPR

1. Nature of breach: [Description]
2. Categories and approximate number of data subjects concerned: [Detail]
3. Categories and approximate number of records concerned: [Detail]
4. Name and contact details of DPO: [DPO Name, email, phone]
5. Likely consequences of the breach: [Assessment]
6. Measures taken or proposed: [Remediation actions]

[Organisation Name] | [Date/Time of notification]
```

---

## 8. Control Mapping

| Phase | ISO 27001:2022 | NIST CSF 2.0 | NIST 800-53 r5 |
|-------|---------------|--------------|----------------|
| Preparation | A.5.24, A.5.25 | DE.CM, RS.MA | IR-1, IR-2 |
| Identification | A.5.25, A.8.16 | DE.AE | IR-5, IR-6 |
| Containment | A.5.26 | RS.MI | IR-4 |
| Eradication | A.5.26 | RS.MI-02 | IR-4 |
| Recovery | A.5.29, A.5.30 | RC.RP | CP-10 |
| PIR | A.5.27 | RS.IM | IR-4(2) |

---

*This policy must be reviewed after every P1/P2 incident and updated with lessons learned.*
