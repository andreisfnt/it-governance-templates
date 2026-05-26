# Service Level Agreement

**Document reference:** [SLA-XXXX]  
**Version:** 1.0  
**Effective date:** [Date]  
**Review date:** [Date - typically annual]  
**Service provider:** [IT Department / Managed Service Provider name]  
**Customer:** [Business unit / organization name]  
**Owner:** [IT Manager / Service Delivery Manager]

---

## 1. Purpose

This Service Level Agreement defines the performance standards, responsibilities, and terms governing the delivery of [service name] by [service provider] to [customer].

This document is intended to set clear expectations, provide a basis for measuring service quality, and define the process for resolving disputes about service performance.

---

## 2. Services Covered

This agreement covers the following services:

| Service | Description | In scope | Out of scope |
|---------|-------------|----------|-------------|
| [Service 1] | [Brief description] | [What is included] | [What is explicitly excluded] |
| [Service 2] | [Brief description] | | |

**Services not listed above are not covered by this agreement.** Requests for services outside this scope should be raised through [change request / service request process].

---

## 3. Hours of Service

| Service | Hours of operation | On-call / out-of-hours |
|---------|-------------------|----------------------|
| [Service 1] | [e.g. Monday-Friday, 08:00-18:00 CET] | [e.g. Critical incidents only, via [contact method]] |
| [Service 2] | | |

**Public holidays:** [Define whether services are available on public holidays and which calendar applies.]

---

## 4. Service Level Targets

### 4.1 Availability

| Service | Availability target | Measurement period | Planned maintenance exclusion |
|---------|--------------------|--------------------|-------------------------------|
| [Service 1] | [e.g. 99.5%] | Monthly | Yes |
| [Service 2] | | | |

**Availability formula:** (Total minutes in period - Unplanned downtime minutes) / Total minutes in period x 100

### 4.2 Incident Response and Resolution

Incidents are classified by impact and urgency.

| Priority | Definition | Response time target | Resolution time target |
|----------|-----------|---------------------|----------------------|
| P1 - Critical | Complete service outage or critical business process unavailable | [e.g. 15 minutes] | [e.g. 4 hours] |
| P2 - High | Significant degradation or major feature unavailable, workaround possible | [e.g. 1 hour] | [e.g. 8 business hours] |
| P3 - Medium | Partial impact, workaround available, business can continue | [e.g. 4 business hours] | [e.g. 3 business days] |
| P4 - Low | Minimal impact, cosmetic or informational | [e.g. 1 business day] | [e.g. 10 business days] |

**Response time** = time from ticket creation to first meaningful update from the service provider.  
**Resolution time** = time from ticket creation to confirmed resolution and ticket closure.

### 4.3 Service Request Fulfillment

| Request type | Fulfillment time target | Notes |
|-------------|------------------------|-------|
| [e.g. New user account] | [e.g. 1 business day] | Subject to manager approval received |
| [e.g. Software installation] | [e.g. 2 business days] | Standard software catalog only |
| [e.g. Access change] | [e.g. 1 business day] | Subject to approval workflow |

---

## 5. Responsibilities

### Service provider responsibilities

- Deliver services to the standards defined in this agreement
- Maintain and monitor services during agreed hours of operation
- Communicate planned maintenance with [minimum X days] advance notice
- Report monthly on SLA performance
- Escalate incidents according to the escalation matrix in Section 6
- Maintain documentation sufficient to support service continuity

### Customer responsibilities

- Report incidents and service requests through [agreed channel] with sufficient detail to enable triage
- Provide timely responses when information is required to progress an incident
- Assign an accountable contact for service-related communication
- Provide advance notice of planned changes that may affect the service
- Not attempt workarounds that could worsen an incident without IT coordination

---

## 6. Escalation Matrix

| Level | When to escalate | Escalate to | Contact |
|-------|-----------------|-------------|---------|
| L1 | P1 incident not resolved within [2 hours] | IT Team Lead | [Contact] |
| L2 | P1 incident not resolved within [4 hours] | IT Manager | [Contact] |
| L3 | P1 incident not resolved within [8 hours] | Head of IT / CTO | [Contact] |
| Relationship | Recurring SLA breach or service concern | IT Manager + Business Owner | [Contact] |

---

## 7. Planned Maintenance

- Planned maintenance windows: [e.g. Saturdays 22:00-02:00 CET]
- Minimum notice for planned maintenance: [e.g. 5 business days]
- Emergency maintenance (security-driven): [e.g. 2 hours notice where operationally possible]
- Planned maintenance does not count against availability targets when notice requirements are met.

---

## 8. Measurement and Reporting

| Metric | Measurement method | Reported by | Frequency |
|--------|-------------------|-------------|-----------|
| Availability | [Monitoring platform / ticket data] | IT | Monthly |
| Incident resolution within SLA | Ticket system data | IT | Monthly |
| Request fulfillment within SLA | Ticket system data | IT | Monthly |
| Customer satisfaction | [Survey / periodic review] | IT | Quarterly |

Monthly reports will be shared with [customer contact] by [e.g. the 5th business day of the following month].

---

## 9. SLA Credits and Remedies

[Optional section - include if this is a commercial or formal internal agreement with consequences for breach.]

| Availability in month | Credit applied |
|-----------------------|----------------|
| Below target but above [X]% | [e.g. 5% of monthly fee] |
| Below [X]% | [e.g. 10% of monthly fee] |
| Below [X]% | [e.g. 20% of monthly fee] |

Credits are the sole remedy for SLA underperformance and do not constitute acknowledgment of liability beyond this agreement.

---

## 10. Exclusions

This SLA does not apply to, and performance targets are suspended during:

- Incidents caused by changes made by the customer without IT authorization
- Third-party service outages outside the control of the service provider
- Incidents resulting from force majeure events
- Periods of planned maintenance notified in accordance with Section 7
- Incidents where the customer has not provided information reasonably requested by IT within [X hours]

---

## 11. Review and Amendment

This agreement will be reviewed [annually / every 6 months] or when a material change to the service occurs. Either party may request a review by notifying the other party in writing.

Amendments require written agreement from both parties and are appended to this document with a new version number.

---

## 12. Signatures

| | Name | Title | Date | Signature |
|-|------|-------|------|-----------|
| Service provider | | | | |
| Customer | | | | |

---

## Revision History

| Version | Date | Author | Summary |
|---------|------|--------|---------|
| 1.0 | | | Initial version |
