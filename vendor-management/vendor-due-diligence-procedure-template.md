# Vendor Due Diligence Procedure

**Document reference:** [PROC-VEN-DD-001]  
**Version:** 1.0  
**Effective date:** [Date]  
**Review date:** [Date - recommend annual]  
**Owner:** [IT Manager / Procurement Manager]  
**Approved by:** [Name and title]  
**Classification:** Internal  
**ISO 27001 reference:** Annex A 5.19 - 5.22 (Supplier relationships)

---

## 1. Purpose

This procedure defines the due diligence requirements for evaluating, onboarding, and monitoring vendors and suppliers who access, process, or store [Organization name]'s information assets or who provide services critical to business operations.

Vendor risk is organizational risk. A supplier's security failure, financial instability, or service outage becomes your problem the moment you depend on them.

---

## 2. Scope

This procedure applies to:

- All new vendors providing IT services, software, cloud services, or data processing
- Existing vendors at contract renewal or when their scope changes materially
- Any third party with access to [Organization name]'s systems, networks, or data
- Subprocessors engaged by existing vendors who will handle organizational data

This procedure does not apply to:
- One-off purchases of physical goods with no ongoing service relationship
- Publicly available open-source software (separate evaluation applies)

---

## 3. Vendor risk classification

Vendors are classified by the level of risk they represent based on data access, operational dependency, and financial exposure.

| Tier | Description | Examples | Due diligence level |
|------|-------------|----------|---------------------|
| Tier 1 - Critical | Processes sensitive/personal data OR critical operational dependency | Cloud ERP, HRIS, primary cloud provider, M365/Google Workspace | Full due diligence |
| Tier 2 - Significant | Limited data access OR significant but non-critical service | IT support partner, secondary SaaS tools, recruitment platforms | Standard due diligence |
| Tier 3 - Low | No access to organizational data, low operational dependency | Software licenses, commodity hardware, minor SaaS tools | Lightweight review |

Classification must be assigned before engagement begins. When in doubt, classify higher.

---

## 4. Pre-engagement due diligence

### 4.1 Tier 1 (Critical) - Full due diligence checklist

**Company and financial**
- [ ] Legal name, registration number, and registered address confirmed
- [ ] Company financial stability assessed (credit check or published accounts reviewed)
- [ ] Ownership structure reviewed - no undisclosed conflicts of interest
- [ ] Regulatory sanctions and adverse news check completed
- [ ] Key personnel and leadership verified

**Information security**
- [ ] ISO 27001 certification confirmed (or equivalent - SOC 2 Type II, Cyber Essentials Plus)
- [ ] Certificate validity and scope confirmed (not expired, covers the relevant service)
- [ ] Security questionnaire completed and reviewed (see Appendix A)
- [ ] Penetration testing - most recent report date confirmed and executive summary reviewed
- [ ] Vulnerability disclosure and patching policy confirmed
- [ ] Subprocessor list obtained and reviewed
- [ ] Data breach history reviewed (past 3 years)
- [ ] Incident response and notification procedures confirmed

**Data processing and GDPR**
- [ ] Data Processing Agreement (DPA) executed before any personal data is shared
- [ ] Data processing purposes and legal basis confirmed
- [ ] Data storage locations confirmed (EEA or adequacy decision / SCCs in place for non-EEA)
- [ ] Data retention and deletion procedures confirmed
- [ ] Subject access request support procedures confirmed

**Operational resilience**
- [ ] Business continuity and disaster recovery documentation reviewed
- [ ] RTO/RPO commitments confirmed and documented
- [ ] SLA terms reviewed and accepted
- [ ] Uptime history / status page reviewed
- [ ] Exit and data portability procedures confirmed

**Contractual**
- [ ] Confidentiality / NDA executed
- [ ] Data Processing Agreement executed
- [ ] Security obligations included in contract (minimum security standards, breach notification, audit rights)
- [ ] Right to audit or request third-party audit confirmed
- [ ] Liability and indemnity terms reviewed by legal / management
- [ ] Contract term, renewal, and termination clauses confirmed

---

### 4.2 Tier 2 (Significant) - Standard due diligence checklist

- [ ] Legal name and registration confirmed
- [ ] Security posture reviewed (certifications, security questionnaire, or self-attestation)
- [ ] Data Processing Agreement executed if personal data is involved
- [ ] Data storage location confirmed
- [ ] Confidentiality / NDA executed
- [ ] SLA terms reviewed
- [ ] Security obligations included in contract
- [ ] Exit and data portability procedures noted

---

### 4.3 Tier 3 (Low) - Lightweight review

- [ ] Vendor legitimate and established (basic internet / registration check)
- [ ] No personal data shared
- [ ] Standard vendor terms reviewed and accepted or flagged for legal review
- [ ] Purchasing approval obtained per [procurement policy]

---

## 5. Security questionnaire

For Tier 1 vendors without ISO 27001 or equivalent certification, the following minimum questions must be answered in writing before engagement:

1. Describe your information security management program. Do you have a dedicated security function?
2. Are you certified to ISO 27001, SOC 2 Type II, or equivalent? Provide details.
3. How do you handle security patching for systems that process or store our data? What is your target patching timeframe for critical vulnerabilities?
4. Do you conduct annual penetration tests on systems relevant to this service? When was the most recent test and who conducted it?
5. Describe your incident detection and response capabilities. How quickly would you notify us of a security incident affecting our data?
6. Where will our data be stored and processed? List all countries and data centre locations.
7. Who are your subprocessors or significant fourth-party dependencies for this service?
8. Describe your access control practices for staff who can access customer data.
9. How is our data encrypted at rest and in transit?
10. What is your data retention and deletion process at contract end?
11. Have you experienced a data breach or significant security incident in the last 3 years? If yes, describe what happened and how it was resolved.
12. Do you carry cyber liability insurance? What is the coverage amount?

---

## 6. Vendor onboarding

Upon completion of due diligence and contract execution:

1. Register vendor in [vendor register / procurement system] with:
   - Vendor tier classification
   - Contract start and end dates
   - Data types processed (if any)
   - Key contacts (account manager, security contact, incident notification contact)
   - DPA reference (if applicable)
   - Next review date
2. Provision access per the [Access Control Policy] - minimum necessary access only
3. Brief internal stakeholders on vendor scope, limitations, and incident notification procedure
4. Add vendor to monitoring schedule (Section 7)

---

## 7. Ongoing vendor monitoring

Risk does not end at contract signature. Vendors must be monitored throughout the relationship.

| Activity | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Annual security review / questionnaire refresh | Yes | Yes | No |
| Certificate / certification renewal check | Annual | Annual | No |
| Contract and SLA review | Annual | At renewal | At renewal |
| Adverse news and sanctions monitoring | Quarterly | Annual | No |
| Performance review (SLA metrics) | Quarterly | Annual | As needed |
| Subprocessor change notifications | Review within 30 days | Note | No |

Trigger an immediate review for any vendor upon:
- Reported security incident or data breach
- News of significant financial difficulty or ownership change
- SLA performance falling below contracted thresholds for [3] consecutive months
- Material change in the service, data processed, or system access

---

## 8. Vendor offboarding

When a vendor relationship ends (contract termination, expiry, or replacement):

1. Revoke all system access on or before the last day of service
2. Confirm data deletion or return per contract terms - obtain written confirmation
3. Revoke all credentials and API keys associated with the vendor
4. Remove vendor from any network access lists, IP allowlists, or SSO configurations
5. Archive contract and due diligence documentation per [data retention policy]
6. Update vendor register to reflect offboarding date and status
7. Verify no residual access remains within [5] business days of offboarding

---

## 9. Exceptions

Exceptions to this procedure (e.g. engaging a Tier 1 vendor without a signed DPA due to urgent business need) require written approval from [IT Manager / CISO] and must include:

- Business justification
- Risk acceptance statement
- Compensating controls
- A defined deadline to complete outstanding requirements

---

## 10. Vendor register

A vendor register must be maintained and kept current. Minimum fields:

| Field | Description |
|-------|-------------|
| Vendor name | Legal name |
| Service description | What they provide |
| Tier | 1 / 2 / 3 |
| Contract start / end | Dates |
| Data processed | Types of data, if any |
| DPA in place | Yes / No / N/A |
| Certification | ISO 27001 / SOC 2 / None |
| Last review date | Date of most recent due diligence review |
| Next review date | Scheduled next review |
| Internal owner | Person accountable for this vendor relationship |

---

## 11. Roles and responsibilities

| Role | Responsibility |
|------|---------------|
| IT Manager | Procedure ownership, Tier 1 due diligence oversight, exception approval |
| Procurement / Finance | Initiating due diligence for new vendors, contract management |
| Legal | DPA and contract review |
| Business owner (per vendor) | Day-to-day vendor relationship, performance monitoring |
| IT / Security team | Access provisioning/revocation, technical security assessment |

---

## 12. Review

This procedure is reviewed annually or following a vendor-related security incident or significant change in procurement practices.

---

## Appendix A: Due diligence file checklist

For each Tier 1 vendor, the following documents should be retained on file:

- [ ] Signed contract (including security schedule)
- [ ] Signed Data Processing Agreement
- [ ] Signed NDA / confidentiality agreement
- [ ] ISO 27001 certificate (or equivalent) - copy
- [ ] Completed security questionnaire and responses
- [ ] Due diligence approval sign-off
- [ ] Subsequent review records
