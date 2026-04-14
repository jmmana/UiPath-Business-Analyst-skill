# Process Assessment Checklist

> **Purpose**: Evaluate a process's suitability for UiPath automation
> **Based on**: UiPath Automation Business Analyst certification objectives and official methodology
> **Reference**: [UiPath Documentation](https://docs.uipath.com/)

---

## Process Information

| Field | Value |
|-------|-------|
| **Process Name** | [Process Name] |
| **Department** | [Department] |
| **Process Owner** | [Name, Title] |
| **Assessment Date** | [YYYY-MM-DD] |
| **Assessed By** | [Business Analyst Name] |
| **Assessment Status** | [Complete / Incomplete — Missing Data] |

---

## 1. Rule-Based Assessment

> Can the process be described as a set of deterministic rules?

| Question | Yes | No | Partial | Evidence/Notes |
|----------|-----|----|---------|----------------|
| Are decisions based on clear business rules (not subjective judgment)? | [ ] | [ ] | [ ] | [Details] |
| Can every decision path be documented as IF-THEN logic? | [ ] | [ ] | [ ] | [Details] |
| Are exceptions handled by predefined escalation rules? | [ ] | [ ] | [ ] | [Details] |
| Does the process avoid requiring human intuition or creativity? | [ ] | [ ] | [ ] | [Details] |

**Rule-Based Score: [X/4]** — [Interpretation]

---

## 2. Process Stability

> Is the process stable and predictable over time?

| Question | Yes | No | Partial | Evidence/Notes |
|----------|-----|----|---------|----------------|
| Has the process remained unchanged for at least 6 months? | [ ] | [ ] | [ ] | [Details] |
| Are there documented SOPs or work instructions? | [ ] | [ ] | [ ] | [Details] |
| Is the process performed consistently across different operators? | [ ] | [ ] | [ ] | [Details] |
| Are process changes governed by a formal change management process? | [ ] | [ ] | [ ] | [Details] |

**Stability Score: [X/4]** — [Interpretation]

---

## 3. Digital Input Assessment

> Are process inputs available in digital, structured form?

| Question | Yes | No | Partial | Evidence/Notes |
|----------|-----|----|---------|----------------|
| Are input files in structured formats (Excel, CSV, XML, JSON, database)? | [ ] | [ ] | [ ] | [Details] |
| Is data received via email in parseable format (not scanned images)? | [ ] | [ ] | [ ] | [Details] |
| Are there paper-based inputs that would require OCR/scanning? | [ ] | [ ] | [ ] | [Details] |
| Can all required data be accessed programmatically (APIs, databases, UIs)? | [ ] | [ ] | [ ] | [Details] |

**Digital Input Score: [X/4]** — [Interpretation]

---

## 4. Standardization Assessment

> Is the process performed the same way each time?

| Question | Yes | No | Partial | Evidence/Notes |
|----------|-----|----|---------|----------------|
| Is there a single, documented standard process? | [ ] | [ ] | [ ] | [Details] |
| Do all variations follow the same core workflow? | [ ] | [ ] | [ ] | [Details] |
| Are exceptions handled through documented escalation paths? | [ ] | [ ] | [ ] | [Details] |
| Is there minimal variation between operators or locations? | [ ] | [ ] | [ ] | [Details] |

**Standardization Score: [X/4]** — [Interpretation]

---

## 5. Volume & FTE Justification

> Is there sufficient volume to justify automation investment?

| Metric | Value | Threshold | Meets Threshold? | Notes |
|--------|-------|-----------|------------------|-------|
| Monthly transaction volume | [X,XXX] | [>500/month recommended] | [Yes/No] | [Details] |
| Current FTE allocation | [X.X FTEs] | [>0.5 FTE recommended] | [Yes/No] | [Details] |
| Annual processing cost | [$XXX,XXX] | [Compare to automation cost] | [Yes/No] | [Details] |
| Peak vs. average volume ratio | [X.Xx] | [<3x recommended] | [Yes/No] | [Details] |

**Volume Score: [X/4]** — [Interpretation]

---

## 6. System Accessibility & Technical Feasibility

> Can the systems involved be automated?

| Question | Yes | No | Partial | Evidence/Notes |
|----------|-----|----|---------|----------------|
| Are all applications accessible via standard UiPath activities? | [ ] | [ ] | [ ] | [Details] |
| Are applications running on supported platforms (Windows, Web, Mainframe, SAP, etc.)? | [ ] | [ ] | [ ] | [Details] |
| Are there Citrix/VDI environments that require Computer Vision? | [ ] | [ ] | [ ] | [Details] |
| Do any systems have anti-automation measures (CAPTCHAs, security tools)? | [ ] | [ ] | [ ] | [Details] |

**System Accessibility Score: [X/4]** — [Interpretation]

---

## 7. Exception Handling Feasibility

> Can exceptions be handled reliably?

| Question | Yes | No | Partial | Evidence/Notes |
|----------|-----|----|---------|----------------|
| Are business exceptions clearly defined and documentable? | [ ] | [ ] | [ ] | [Details] |
| Can the robot detect and log all exception types? | [ ] | [ ] | [ ] | [Details] |
| Is there a clear escalation path for exceptions requiring human intervention? | [ ] | [ ] | [ ] | [Details] |
| Can the process continue after an exception (graceful degradation)? | [ ] | [ ] | [ ] | [Details] |

**Exception Handling Score: [X/4]** — [Interpretation]

---

## 8. Regulatory & Compliance Assessment

> Does the process have compliance requirements that affect automation design?

| Requirement | Applicable? | Impact on Automation | Notes |
|-------------|-------------|---------------------|-------|
| **GDPR** (EU data protection) | [Yes/No] | [Data masking, audit trails, right to erasure] | [Details] |
| **SOX** (Financial reporting) | [Yes/No] | [Segregation of duties, audit logs] | [Details] |
| **HIPAA** (Healthcare data) | [Yes/No] | [PHI handling, encryption] | [Details] |
| **PCI-DSS** (Payment card data) | [Yes/No] | [No card data in logs, encryption] | [Details] |
| **Industry-specific** | [Specify] | [Details] | [Details] |

---

## 9. Risk Assessment

| Risk | Probability (H/M/L) | Impact (H/M/L) | Mitigation Strategy |
|------|---------------------|----------------|---------------------|
| Application UI changes break selectors | [H/M/L] | [H/M/L] | [Use stable selectors, version control] |
| Volume exceeds robot capacity | [H/M/L] | [H/M/L] | [Queue-based processing, horizontal scaling] |
| Data quality issues cause errors | [H/M/L] | [H/M/L] | [Validation rules, exception queues] |
| System downtime disrupts automation | [H/M/L] | [H/M/L] | [Retry logic, alerting, failover] |
| Security/access issues | [H/M/L] | [H/M/L] | [Credential management, least privilege] |

---

## 10. Overall Automation Suitability Score

| Criteria | Score (0-10) | Weight | Weighted Score |
|----------|--------------|--------|----------------|
| Rule-based decisions | [0-10] | 20% | [X.X] |
| Process stability | [0-10] | 15% | [X.X] |
| Digital inputs | [0-10] | 15% | [X.X] |
| Standardization | [0-10] | 15% | [X.X] |
| Volume/FTE justification | [0-10] | 15% | [X.X] |
| System accessibility | [0-10] | 10% | [X.X] |
| Exception handling feasibility | [0-10] | 10% | [X.X] |
| **TOTAL** | | **100%** | **[X.X / 10]** |

### Suitability Rating

| Score Range | Rating | Recommendation |
|-------------|--------|----------------|
| **8.0 - 10.0** | Excellent | Proceed with full automation |
| **6.0 - 7.9** | Good | Proceed with identified risk mitigations |
| **4.0 - 5.9** | Moderate | Pilot recommended before full rollout |
| **0.0 - 3.9** | Low | Consider alternative approaches (API, process redesign) |

---

## 11. Automation Approach Recommendation

Based on the assessment above, recommend the appropriate approach:

| Approach | Recommended? | Rationale |
|----------|--------------|-----------|
| **Unattended Automation** | [Yes/No] | [High volume, rule-based, no human intervention needed] |
| **Attended Automation** | [Yes/No] | [Requires human triggering, approval, or supervision] |
| **Hybrid (Attended + Unattended)** | [Yes/No] | [Mixed requirements] |
| **Process Redesign First** | [Yes/No] | [Process is too unstable/variable to automate as-is] |
| **API Integration (not RPA)** | [Yes/No] | [Systems have APIs available; more reliable than UI automation] |
| **Not Recommended** | [Yes/No] | [Process fails key criteria; document reasons] |

---

## 12. Next Steps

- [ ] Complete PDD using `templates/PDD-Template.md` (if score ≥ 6.0)
- [ ] Calculate ROI using `templates/ROI-Calculator.md`
- [ ] Schedule stakeholder review meeting
- [ ] Gather missing data items: [List items]
- [ ] Conduct proof of concept for high-risk areas
- [ ] Present assessment to automation steering committee

---

## Assessment Sign-Off

| Role | Name | Date | Signature |
|------|------|------|-----------|
| Business Analyst | [Name] | [Date] | [Signature] |
| Process Owner | [Name] | [Date] | [Signature] |

---

> **Assessment Date**: [YYYY-MM-DD]
> **Next Review Date**: [YYYY-MM-DD] (recommended: 90 days if proceeding to development)
