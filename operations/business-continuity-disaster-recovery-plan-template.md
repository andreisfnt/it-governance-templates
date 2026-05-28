# Business Continuity and Disaster Recovery Plan

**Document reference:** [PLAN-OPS-BCDR-001]  
**Version:** 1.0  
**Effective date:** [Date]  
**Review date:** [Date - recommend annual + after each test or invocation]  
**Owner:** [IT Manager / Business Continuity Manager]  
**Approved by:** [Name and title]  
**Classification:** Confidential  
**ISO 27001 reference:** Annex A 5.29 (Information security during disruption), A 5.30 (ICT readiness for business continuity)

---

## 1. Purpose

This plan defines how [Organization name] will maintain critical business operations and recover IT services following a significant disruption. It covers both the continuity of business processes (BC) and the technical recovery of IT systems and infrastructure (DR).

A plan that exists only on paper fails in a crisis. This document is a working reference - it must be tested, kept current, and known to the people who need to act on it.

---

## 2. Scope

This plan covers:

- Critical business processes identified in the Business Impact Analysis (Section 4)
- IT systems and infrastructure supporting those processes
- Response to disruption scenarios including system failures, data loss, cyberattacks, facility unavailability, and key personnel loss

---

## 3. Objectives

| Objective | Definition |
|-----------|-----------|
| Recovery Time Objective (RTO) | Maximum acceptable downtime before a system or process must be restored |
| Recovery Point Objective (RPO) | Maximum acceptable data loss, measured in time (how old can restored data be?) |
| Maximum Tolerable Downtime (MTD) | The absolute maximum time a process can be unavailable before causing irreversible business harm |

---

## 4. Business Impact Analysis

### 4.1 Critical processes

| Process | Supporting systems | RTO | RPO | MTD | Impact of failure |
|---------|-------------------|-----|-----|-----|------------------|
| [e.g. Customer order processing] | [ERP, email] | [4 hours] | [1 hour] | [24 hours] | [Revenue loss, contractual breach] |
| [e.g. Financial reporting] | [Finance system, ERP] | [8 hours] | [24 hours] | [72 hours] | [Regulatory risk] |
| [e.g. Employee access / identity] | [Active Directory / Entra ID] | [2 hours] | [4 hours] | [8 hours] | [Organization-wide work stoppage] |
| [e.g. Email and communication] | [Microsoft 365 / Exchange] | [4 hours] | [1 hour] | [24 hours] | [Internal and external communication failure] |
| [e.g. Customer data access] | [CRM] | [8 hours] | [4 hours] | [48 hours] | [Customer service failure] |

### 4.2 Single points of failure

Identify and document any single points of failure in infrastructure, personnel, or third-party dependencies:

| Single point of failure | Risk | Mitigation |
|------------------------|------|-----------|
| [e.g. Primary internet connection] | [Loss of connectivity] | [Failover SIM / secondary ISP] |
| [e.g. Key administrator - [Name]] | [Knowledge / access loss] | [Document procedures, cross-train] |
| [e.g. Primary SaaS vendor] | [Service unavailability] | [Data export, fallback process] |

---

## 5. Crisis response team

| Role | Responsibility | Primary contact | Backup contact |
|------|---------------|----------------|---------------|
| Incident Commander | Overall crisis decision-making | [Name / title] | [Name / title] |
| IT Recovery Lead | Technical recovery execution | [Name / title] | [Name / title] |
| Communications Lead | Internal and external communications | [Name / title] | [Name / title] |
| Business Process Lead | Business continuity decisions | [Name / title] | [Name / title] |
| HR Lead | Personnel and welfare issues | [Name / title] | [Name / title] |

All team members must have this plan accessible offline (printed copy or local device storage).

---

## 6. Disruption scenarios and response

### 6.1 Scenario: IT system failure (hardware / software)

**Trigger:** Critical server, storage, or application failure affecting business operations.

**Immediate actions (0 - 1 hour):**
1. IT on-call notified and incident opened in ticketing system
2. Assess scope - which systems affected, how many users impacted
3. Notify Incident Commander if RTO threshold is at risk
4. Attempt standard recovery procedures (restart, failover)
5. Escalate to vendor support if internal recovery fails

**Recovery actions (1 hour onwards):**
1. Activate backup systems or failover infrastructure
2. Restore from most recent clean backup if required
3. Validate data integrity post-restore
4. Communicate status to affected users every [30 minutes]
5. Document timeline and actions taken

**Resolution:**
1. Confirm full service restoration and user validation
2. Root cause analysis within [5 business days]
3. Update this plan if process gaps were identified

---

### 6.2 Scenario: Ransomware or destructive cyberattack

**Trigger:** Ransomware detected, widespread encryption of files, or evidence of destructive malware.

**Immediate actions (0 - 1 hour):**
1. Isolate affected systems from the network immediately - disconnect cables, disable Wi-Fi
2. Do NOT power off affected systems (preserves forensic evidence)
3. Notify Incident Commander and [CISO / IT Manager]
4. Activate incident response - refer to [Incident Response Playbook]
5. Assess blast radius - what is encrypted, what backup systems remain clean

**Recovery actions:**
1. Do not pay ransom without legal and executive approval - payment does not guarantee recovery
2. Recover from clean, offline backups that pre-date the infection
3. Rebuild compromised systems from scratch rather than restoring potentially infected images
4. Reset all credentials organization-wide before restoring access
5. Engage forensic support if the attack vector is unknown

**Communication:**
- Notify DPA (Autoriteit Persoonsgegevens) within 72 hours if personal data is involved
- Notify affected individuals if there is high risk to their rights and freedoms
- Prepare holding statement for external inquiries

---

### 6.3 Scenario: Facility unavailability (fire, flood, building access denied)

**Trigger:** Primary office premises are unavailable for an extended period.

**Immediate actions:**
1. Confirm employee safety - people before systems
2. Incident Commander activates remote working procedures
3. IT confirms remote access capacity (VPN, M365, cloud systems)
4. Communications Lead notifies all staff of the situation and working arrangements
5. Activate alternative workspace if required (see Section 7)

**Recovery actions:**
1. Assess expected duration of unavailability
2. If extended (more than [5] days), identify temporary workspace
3. Prioritize staff with critical process responsibilities for remote access setup
4. Maintain regular status updates to all staff

---

### 6.4 Scenario: Key personnel unavailability

**Trigger:** Critical staff member is suddenly unavailable (illness, resignation, accident).

**Immediate actions:**
1. Line manager identifies impact on critical processes
2. IT Manager assesses impact on system access and administration
3. Activate documented runbooks and procedures for affected responsibilities
4. Assign temporary coverage from backup contacts (see Section 5)

**Prevention (ongoing):**
- All critical procedures must be documented as runbooks
- At least two people must have knowledge of and access credentials for each critical system
- Knowledge transfer must be completed before planned departures

---

## 7. Alternative working arrangements

| Scenario | Primary alternative | Backup alternative |
|----------|--------------------|--------------------|
| Office unavailable | Remote working from home | [Co-working space / secondary location] |
| Internet failure | Mobile data tethering (staff laptops) | [Secondary ISP circuit at office] |
| Microsoft 365 outage | [Defined offline procedures] | [Alternative communication channel] |

Remote working requirements:
- All staff must be able to work remotely within [2 hours] of notification
- Remote access must be tested as part of the annual BCDR test

---

## 8. Data backup and recovery

### 8.1 Backup requirements

| System | Backup frequency | Retention | Storage location | Recovery tested |
|--------|-----------------|-----------|-----------------|----------------|
| [File server / SharePoint] | [Daily] | [30 days] | [Cloud + offsite] | [Quarterly] |
| [ERP / business system] | [Daily] | [90 days] | [Cloud + offsite] | [Quarterly] |
| [Email (Exchange Online)] | [Continuous] | [Per M365 policy] | [Microsoft data centres] | [Annually] |
| [Configuration backups] | [Weekly] | [12 months] | [Offsite] | [Annually] |

### 8.2 Backup principles

- At least one backup copy must be stored offsite or in a separate cloud region
- Backups must be encrypted at rest
- Backup integrity must be verified by test restoration [quarterly]
- The most recent backup must not be connected to production systems (air-gap or immutable storage)
- Refer to [Backup and Recovery Procedure Template] for detailed procedures

---

## 9. Communication plan

### 9.1 Internal communication

| Audience | Channel | Frequency during incident | Responsible |
|---------|---------|--------------------------|-------------|
| All staff | Email + [Teams/Slack] | Every [2 hours] or on status change | Communications Lead |
| Management | Direct call | Immediately + every [1 hour] | Incident Commander |
| Crisis response team | [Teams/WhatsApp group] | Continuous | Incident Commander |

### 9.2 External communication

| Audience | Trigger | Channel | Responsible |
|---------|---------|---------|-------------|
| Customers (affected) | Service disruption confirmed | Email + [status page if available] | Communications Lead |
| Regulators (AP) | Personal data breach suspected | Official notification | [DPO / Legal / IT Manager] |
| Press / media | Significant incident becoming public | Prepared statement only | [CEO / Communications Lead] |
| Suppliers / partners | Dependency impact | Direct contact | Business Process Lead |

**Rule:** No external communication about an active incident without Incident Commander approval.

---

## 10. Plan invocation

The plan is invoked when:

- An incident is assessed as likely to exceed the RTO of one or more critical processes
- A cyberattack is confirmed or strongly suspected
- Facilities become unavailable
- The Incident Commander declares a major incident

**Invocation authority:** [Incident Commander / IT Manager / CEO]

---

## 11. Testing and exercises

The plan must be tested to be trusted.

| Test type | Frequency | Participants | What is tested |
|-----------|-----------|-------------|----------------|
| Tabletop exercise | Annual | Crisis response team | Decision-making, communication, roles |
| Backup restoration test | Quarterly | IT team | Recovery from backup, RTO/RPO validation |
| Remote working test | Annual | All staff | Remote access, VPN capacity |
| Full DR exercise | Every 2 years | IT team + key users | End-to-end system recovery |

Test results must be documented, including identified gaps. This plan must be updated within [30] days of each test.

---

## 12. Plan maintenance

This plan must be reviewed and updated:

- Annually as a minimum
- Within [30] days of a real invocation
- Following significant changes to IT infrastructure, systems, or organizational structure
- Following any test that identifies material gaps

The plan owner is responsible for ensuring reviews occur and that updated versions are distributed to all crisis response team members.

---

## 13. Document history

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | [Date] | [Author] | Initial version |

---

## Appendix A: Emergency contact list

| Name | Role | Mobile | Email | Backup contact |
|------|------|--------|-------|----------------|
| [Name] | [Role] | [Number] | [Email] | [Name] |

## Appendix B: Critical system access

| System | Location / URL | Admin account location | Vendor support contact |
|--------|---------------|----------------------|----------------------|
| [System name] | [URL / IP] | [Password vault entry] | [Contact / ticket URL] |

## Appendix C: Key vendor contacts

| Vendor | Service | Support contact | Contract / SLA reference |
|--------|---------|----------------|--------------------------|
| [Vendor] | [Service] | [Phone / portal] | [Reference] |
