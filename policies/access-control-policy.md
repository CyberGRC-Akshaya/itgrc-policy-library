# Access Control Policy

| Field | Detail |
|-------|--------|
| **Document ID** | POL-ACP-003 |
| **Version** | 2.4 |
| **Classification** | Internal |
| **Owner** | CISO / Information Security Manager |
| **Effective Date** | [DATE] |
| **Review Date** | Annual |

---

## 1. Purpose & Scope

This policy establishes requirements for controlling access to **[ORGANIZATION NAME]** information systems, applications, data, and physical facilities. It implements the principle of **least privilege** and **need-to-know** across all access types.

**Applies to:** All employees, contractors, vendors, and systems. All environments: on-premise, cloud, hybrid, OT/SCADA.

---

## 2. Access Control Principles

| Principle | Definition | Implementation |
|-----------|-----------|----------------|
| **Least Privilege** | Grant minimum access required | Role-based access; no standing privileged access |
| **Need-to-Know** | Access only to data required for job | Data classification-driven access |
| **Segregation of Duties** | No individual controls entire process | Dual-control for critical transactions |
| **Zero Trust** | Verify every request, trust nothing implicitly | MFA + continuous verification |
| **Fail-Safe Defaults** | Default is deny; must request access explicitly | Deny-all baseline, permit-by-exception |

---

## 3. Access Request & Provisioning

### 3.1 Standard Access
1. Line manager submits access request via [ITSM System]
2. Information Owner approves within 2 business days
3. IT provisions access and notifies user
4. Access logged in Identity & Access Management (IAM) system

### 3.2 Privileged Access (Admin/Root/Super User)
1. **Dual approval required**: Line manager + CISO/Security Manager
2. **Justification documented**: Business need, duration, scope
3. **Time-limited**: Maximum 90 days; renewable with re-approval
4. **Enhanced monitoring**: All privileged sessions logged
5. **Privileged Access Workstation (PAW)**: Mandatory for production access

### 3.3 Emergency Access (Break-Glass)
- Break-glass accounts for emergency use only
- Dual-key activation: Requires two senior personnel
- All usage logged with post-event review within 24 hours
- Quarterly review of break-glass account inventory

---

## 4. Authentication Standards

### 4.1 Password Requirements
| Account Type | Minimum Length | Complexity | MFA Required | Max Age |
|-------------|---------------|------------|--------------|---------|
| Standard User | 12 characters | Yes | Recommended | 90 days |
| Privileged/Admin | 16 characters | Yes | **Mandatory** | 30 days |
| Service Account | 20 characters | Yes | N/A (keys) | 180 days |
| Emergency/Break-Glass | 20 characters | Yes | **Mandatory** | 90 days |

### 4.2 Multi-Factor Authentication
MFA is **mandatory** for:
- All remote access (VPN, Remote Desktop, Citrix)
- All privileged account access
- All cloud administration portals (AWS, Azure, GCP)
- All email access from external networks
- All financial systems and payment platforms
- Banking sector: All customer-facing and internal systems

Approved MFA methods (in order of preference):
1. Hardware security key (FIDO2/WebAuthn) — **Required for privileged users**
2. Authenticator app (TOTP) — Standard users
3. Push notification (Duo, MS Authenticator) — Standard users
4. SMS OTP — **Not recommended**; use only where above unavailable

### 4.3 Single Sign-On (SSO)
- SSO implemented for all enterprise applications where supported
- SSO provider: [Okta / Azure AD / etc.]
- Applications not supporting SSO require compensating controls

---

## 5. Access Review & Recertification

| Review Type | Frequency | Scope | Approver |
|------------|-----------|-------|----------|
| User Access Review | **Quarterly** | All standard users | Line Managers |
| Privileged Access Review | **Monthly** | All privileged/admin accounts | CISO |
| Service Account Review | **Quarterly** | All non-human accounts | IT Manager |
| Vendor/Third-Party Review | **Quarterly** | All third-party access | IT + Procurement |
| Full Recertification | **Annual** | All accounts across all systems | Department Heads |

**Recertification process:**
- IT generates access report per system
- Managers certify or revoke within 5 business days
- Unreviewed access automatically suspended at deadline
- Results logged for audit evidence

---

## 6. Account Lifecycle Management

### 6.1 Joiner Process
- [ ] HR notifies IT of new hire ≥3 business days before start date
- [ ] Role-based access template applied
- [ ] Credentials issued on Day 1 (not before)
- [ ] User completes access training before account activation
- [ ] Initial login forces password change

### 6.2 Mover Process (Role Change)
- [ ] HR notifies IT of role change on effective date
- [ ] Old role access removed within 24 hours
- [ ] New role access provisioned; documented approval
- [ ] Review completed within 5 business days

### 6.3 Leaver Process (Termination)
| Timeframe | Action |
|-----------|--------|
| **Immediate** (involuntary termination) | All access revoked before employee escorted off premises |
| **Within 4 hours** (voluntary resignation) | All system access revoked |
| **Within 24 hours** | Email forwarding disabled; accounts suspended |
| **Within 30 days** | Accounts permanently deleted; access logged for audit |
| **Within 90 days** | Data retention and handover completed |

---

## 7. Privileged Identity Management

### 7.1 Privileged Account Types
- **Domain Admin**: Active Directory domain-level administration
- **Local Admin**: Endpoint local administrator rights
- **Database Admin (DBA)**: Production database access
- **Cloud Admin**: IaaS/PaaS/SaaS administrative access
- **Network Admin**: Firewall, router, switch management
- **Security Admin**: SIEM, EDR, security tool administration

### 7.2 Privileged Access Management (PAM) Controls
- All privileged credentials stored in PAM vault (e.g., CyberArk, BeyondTrust, Delinea)
- No shared privileged accounts (each admin has named personal privileged account)
- Privileged sessions recorded (video/keystroke logging)
- **Just-in-Time (JIT)** provisioning where technically feasible
- Privileged accounts cannot be used for email or internet browsing

---

## 8. Remote Access

### 8.1 VPN Requirements
- All remote access via approved VPN with MFA
- Split-tunnelling: **Disabled** for privileged users; conditional for standard users
- VPN client on managed, endpoint-protected devices only
- Concurrent VPN sessions: Maximum 1 per user

### 8.2 BYOD (Bring Your Own Device)
- Personal devices require Mobile Device Management (MDM) enrollment
- Corporate data must not reside on personal device storage unencrypted
- Remote wipe capability required for all BYOD devices with corporate access

---

## 9. Sector-Specific Requirements

### 🏦 US T1 Banking / FFIEC
- **FFIEC Authentication Guidance**: Layered security for online banking
- **OCC Heightened Standards**: Enhanced access controls for systemically important banks
- All access to core banking systems requires dedicated **named accounts** (no shared/generic)
- **Separation of duties** mandatory: No single individual can approve AND execute wire transfers
- Monthly **privileged account inventory** submitted to CISO and Risk Committee
- Real-time alerting on privileged access anomalies to SOC

### 🛡️ Defence / NIST 800-171 (CUI)
- **AC.1.001**: Limit system access to authorised users and processes
- **AC.1.002**: Limit access to types of transactions and functions authorised users are permitted to execute
- **AC.2.006**: Use non-privileged accounts when accessing non-security functions
- **AC.2.007**: Prevent non-privileged users from executing privileged functions
- Visitor access logs retained for **3 years minimum**
- All CUI system access requires **need-to-know documentation**

### ⚡ Energy / NERC CIP
- **CIP-004-6**: Personnel & training — access management requirements
- **CIP-007-6**: System security management — account management
- **Electronic Access Control** (EAC) for all BES Cyber Systems
- **Interactive Remote Access** (IRA) controls: Encrypted session with intermediate system
- Quarterly review of all BES Cyber System accounts

### 🏥 Healthcare / HIPAA
- **§164.312(a)(1)**: Access control — unique user identification mandatory
- **§164.312(a)(2)(i)**: Emergency access procedure required
- **§164.312(d)**: Person authentication required for all ePHI access
- Automatic session timeout after maximum **15 minutes** of inactivity for ePHI systems
- All ePHI access logged with user, timestamp, and action for minimum **6 years**

---

## 10. Monitoring & Logging

### 10.1 Mandatory Log Events
| Event | Log Retention | Alert Threshold |
|-------|--------------|-----------------|
| Successful login | 1 year | — |
| Failed login | 1 year | 5 failures in 10 minutes |
| Privileged access | 3 years | Every event → SOC review |
| Account creation/deletion | 7 years | Immediate notification to CISO |
| Access policy change | 7 years | Immediate notification to CISO |
| After-hours access | 1 year | Alert if not pre-approved |

### 10.2 SIEM Correlation Rules
- Impossible travel: Login from two geographically separated locations within short time
- Privilege escalation: Standard user gaining admin rights
- Mass data access: User accessing 10x their normal data volume
- Dormant account activity: Login from account inactive for >60 days

---

## 11. Control Mapping

| This Section | ISO 27001:2022 | NIST CSF 2.0 | NIST 800-53 r5 |
|-------------|---------------|--------------|----------------|
| §3 – Provisioning | A.5.15, A.5.16 | PR.AA-01 | AC-2, AC-3 |
| §4 – Authentication | A.8.5 | PR.AA-02 | IA-2, IA-5 |
| §5 – Access Review | A.5.18 | PR.AA-05 | AC-2(j) |
| §6 – Lifecycle | A.5.17, A.5.19 | PR.AA-01 | AC-2 |
| §7 – PAM | A.8.2 | PR.AA-05 | AC-6, AC-17 |
| §10 – Monitoring | A.8.15, A.8.16 | DE.CM-03 | AU-2, AU-3 |

---

*Review Schedule: Annual or upon significant change | Owner: CISO / Information Security Manager*
