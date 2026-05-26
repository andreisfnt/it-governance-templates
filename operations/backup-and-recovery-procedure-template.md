# Data Backup and Recovery Procedure

**Version:** 1.0  
**Owner:** [IT Manager / Infrastructure Lead]  
**Last reviewed:** [Date]  
**Approver:** [Name and title]  
**Classification:** Internal - Restricted

---

## Purpose

This procedure defines the requirements and process for backing up critical organizational data and systems, and for restoring them in the event of data loss, corruption, or system failure. It ensures that recovery capabilities are defined, tested, and reliable before they are needed.

A backup that has never been tested is not a backup - it is an assumption.

---

## Scope

This procedure applies to:

- All servers and systems hosting critical organizational data
- All business-critical applications and databases
- Configuration data for key infrastructure components
- End-user devices where critical data is stored locally (if applicable to organizational policy)

Systems and data hosted by third-party providers under a managed service agreement are subject to that provider's backup obligations, which must be verified contractually and reviewed periodically.

---

## Definitions

| Term | Definition |
|------|-----------|
| Recovery Point Objective (RPO) | Maximum acceptable data loss measured in time. If RPO is 4 hours, the organization can tolerate losing up to 4 hours of data. |
| Recovery Time Objective (RTO) | Maximum acceptable time to restore a system to operational state after a failure. |
| Full backup | Complete copy of all data in scope |
| Incremental backup | Only data changed since the last backup |
| Differential backup | Only data changed since the last full backup |
| Offsite backup | Backup stored at a physically separate location from the primary system |
| Air-gapped backup | Backup isolated from the network, protecting against ransomware and malicious deletion |

---

## Recovery objectives by system tier

Define recovery objectives per system tier. Adjust to your environment.

| System tier | Examples | RPO | RTO |
|-------------|---------|-----|-----|
| Tier 1 - Critical | Core business systems, primary databases, authentication infrastructure | [e.g. 1 hour] | [e.g. 4 hours] |
| Tier 2 - Important | Secondary business applications, file shares, collaboration platforms | [e.g. 4 hours] | [e.g. 8 hours] |
| Tier 3 - Standard | Non-critical internal systems, development environments | [e.g. 24 hours] | [e.g. 48 hours] |

---

## Backup configuration

### Frequency and retention

| Backup type | Frequency | Retention |
|-------------|-----------|----------|
| Full backup | [e.g. Weekly - Sunday] | [e.g. 4 weeks] |
| Incremental / differential | [e.g. Daily - Mon-Sat] | [e.g. 30 days] |
| Monthly archive | [e.g. First Sunday of month] | [e.g. 12 months] |
| Annual archive | [e.g. January] | [e.g. 7 years, or per retention policy] |

Retention periods must align with the organization's data retention policy and any applicable regulatory requirements.

### Backup destinations

Backups must be stored in at least two separate locations to protect against localized failure:

| Copy | Location type | Description |
|------|--------------|-------------|
| Primary backup | On-premises / same data centre | Fast access for routine restores |
| Secondary backup | Offsite or separate cloud region | Protection against site-level failure |
| [Optional: tertiary] | Air-gapped or immutable storage | Protection against ransomware |

### Encryption

- All backup data must be encrypted at rest using current standards
- Encryption keys are managed separately from backup data
- Access to encryption keys is restricted and logged
- Key management procedures are documented and tested as part of recovery testing

### Backup integrity

- Backup jobs are monitored for completion and errors
- Failed backup jobs generate an alert to [IT operations / monitoring system] within [X hours]
- Backup integrity checks (hash verification or test restore) are run [weekly / at each full backup cycle]

---

## Backup procedure

### Pre-backup checks

Before each scheduled backup cycle:

- [ ] Confirm storage destination has adequate capacity
- [ ] Confirm backup service is running and last cycle completed successfully
- [ ] Confirm encryption is active and keys are accessible

### Backup execution

Backups run automatically according to the schedule defined above. Manual backups may be triggered by IT prior to:

- Major system changes or upgrades
- Planned maintenance with significant risk
- On request from system owners before high-risk operations

### Post-backup verification

After each backup cycle:

- [ ] Confirm all scheduled jobs completed without error
- [ ] Log completion status and size of backup
- [ ] Escalate any failed jobs for investigation and re-run
- [ ] Record completion in backup log [link to log location]

---

## Recovery procedure

### Step 1: Assess and authorize

Before initiating any recovery:

- [ ] Document what data or system needs to be recovered and why
- [ ] Identify the most recent clean backup that pre-dates the failure or incident
- [ ] Obtain authorization from [IT Manager / Incident Lead] to proceed
- [ ] Notify affected users and stakeholders of expected recovery timeline based on RTO

### Step 2: Prepare recovery environment

- [ ] Confirm target recovery environment is available (same system rebuilt, or alternative)
- [ ] Confirm encryption keys are accessible
- [ ] Confirm sufficient storage is available at target
- [ ] Confirm backup media or storage is accessible and integrity check is clean

### Step 3: Execute recovery

- [ ] Begin restore from identified backup
- [ ] Monitor restore progress and log start time
- [ ] Do not interrupt the restore process unless a critical error occurs

### Step 4: Verify recovery

After restore completes:

- [ ] Confirm data completeness - spot check key files, records, or database entries
- [ ] Confirm application or system starts and operates correctly
- [ ] Confirm integrations with dependent systems are functional
- [ ] Verify data integrity against known state (checksums, record counts, application-level checks)
- [ ] Log completion time and compare against RTO target

### Step 5: Post-recovery actions

- [ ] Notify stakeholders that the system is restored and operational
- [ ] Document the incident: what failed, what was restored, data loss period (RPO assessment)
- [ ] Identify root cause of the failure that required recovery
- [ ] Update runbooks or procedures if the recovery revealed gaps

---

## Backup testing

### Test types

| Test type | Frequency | Description |
|-----------|-----------|-------------|
| Restore verification | Monthly | Restore a specific file, database record, or configuration item and verify it is intact and correct |
| Application recovery test | [Quarterly / Semi-annual] | Restore a complete application or service to a test environment and confirm it is fully functional |
| Full system recovery test | Annual | Restore a Tier 1 system to a clean environment and bring it to operational state. Measure against RTO target. |
| Ransomware scenario test | Annual | Verify ability to recover from a scenario where primary systems and online backups are compromised. Test air-gapped or immutable backup restore. |

### Test documentation

Each test must be documented:

| Field | Details |
|-------|---------|
| Test date | |
| System / data tested | |
| Backup used (date/version) | |
| Recovery successful | Yes / No |
| Recovery time (for timed tests) | |
| Data integrity confirmed | Yes / No |
| Issues identified | |
| Actions raised | |
| Tester | |

Test results are reviewed by [IT Manager] and retained for [12 months / duration specified in retention policy].

---

## Roles and responsibilities

| Role | Responsibility |
|------|---------------|
| IT Operations | Configure and monitor backup jobs. Respond to backup failures. Execute restores. |
| IT Manager | Define backup scope and recovery objectives. Review test results. Authorize recovery operations. |
| System owners | Confirm recovery objectives for their systems. Participate in recovery testing. Verify data integrity after restore. |
| [CISO / Security] | Ensure backup encryption and offsite storage meets security requirements. Review air-gapped backup posture. |

---

## Exceptions and known limitations

[Document any systems not meeting the standard backup configuration, with justification, compensating controls, and review date.]

| System | Limitation | Reason | Compensating control | Review date |
|--------|-----------|--------|---------------------|------------|
| | | | | |

---

## Revision history

| Version | Date | Author | Summary |
|---------|------|--------|---------|
| 1.0 | | | Initial version |
