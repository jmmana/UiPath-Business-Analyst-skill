# Stakeholder Requirements Gathering Guide

> **Purpose**: Systematic approach to elicit, document, and validate requirements for UiPath automation projects
> **Based on**: UiPath Automation Business Analyst Professional certification objectives and BABOK best practices
> **Reference**: [UiPath Documentation](https://docs.uipath.com/)

---

## Overview

This guide provides a structured approach to requirements gathering for automation projects. It covers stakeholder identification, elicitation techniques, requirement categorization, prioritization, and validation.

---

## 1. Stakeholder Identification

### 1.1 Stakeholder Categories

| Category | Role | Interest | Influence | Engagement Strategy |
|----------|------|----------|-----------|---------------------|
| **Executive Sponsor** | [VP/Director] | ROI, strategic alignment | High | Monthly steering committee |
| **Process Owner** | [Manager] | Process efficiency, KPIs | High | Weekly reviews, PDD sign-off |
| **Subject Matter Experts (SMEs)** | [Senior Operators] | Process accuracy, job security | Medium | Interviews, walkthroughs |
| **IT/Infrastructure** | [IT Manager, Admins] | System access, security, support | High | Technical requirements sessions |
| **End Users (Affected Staff)** | [Operators] | Job impact, usability, training | Low-Medium | Surveys, demo sessions |
| **Compliance/Legal** | [Compliance Officer] | Regulatory adherence | High | Early engagement, sign-off required |
| **Development Team** | [Developers, Architects] | Technical feasibility, design | Medium | Requirements handoff, Q&A |

### 1.2 Stakeholder Analysis Matrix

| Stakeholder | Name | Department | Availability | Preferred Communication | Decision Authority |
|-------------|------|------------|--------------|------------------------|-------------------|
| [Role] | [Name] | [Dept] | [Schedule] | [Meetings/Email/Docs] | [Approve/Consult/Inform] |

---

## 2. Requirements Elicitation Techniques

### 2.1 Technique Selection

| Technique | When to Use | Strengths | Limitations |
|-----------|-------------|-----------|-------------|
| **Process Walkthrough** | Understanding current process steps | Direct observation, captures tacit knowledge | Time-consuming, observer effect |
| **SME Interviews** | Detailed requirements, exception handling | Rich detail, builds relationship | Scheduling, SME availability |
| **Document Analysis** | SOPs, regulations, existing documentation | Baseline understanding, auditable | May be outdated, incomplete |
| **Workshop** | Cross-functional requirements, conflict resolution | Collaborative, faster consensus | Requires facilitation skills |
| **Survey/Questionnaire** | Volume validation, pain point prioritization | Quantitative data, broad reach | Low response rate, surface-level |
| **Shadowing** | Complex processes, high exception rates | Captures real-world variation | Expensive, disruptive |
| **Prototyping** | Validating To-Be design, user acceptance | Early feedback, reduces rework | Requires development effort |

### 2.2 Interview Guide Template

**Pre-Interview Preparation:**
- [ ] Review existing process documentation
- [ ] Prepare specific questions for known pain points
- [ ] Schedule 60-90 minutes with SME
- [ ] Confirm recording permission (if applicable)

**Interview Structure:**

```
1. Introduction (5 min)
   - Purpose of the interview
   - How requirements will be used
   - Confidentiality and data handling

2. Process Overview (15 min)
   - "Walk me through the process from start to end"
   - "What triggers this process?"
   - "What are the main decision points?"

3. Detailed Requirements (30 min)
   - "What systems/applications do you use?"
   - "What data do you need for each step?"
   - "What are the most common exceptions?"
   - "What takes the most time?"
   - "Where do errors typically occur?"

4. Pain Points & Opportunities (15 min)
   - "What is the most frustrating part of this process?"
   - "What would you most like to see improved?"
   - "What would make your job easier?"

5. Wrap-Up (5 min)
   - "Is there anything I haven't asked that I should know?"
   - "Who else should I talk to?"
   - Schedule follow-up if needed
```

---

## 3. Requirements Categories

### 3.1 Functional Requirements

> What the automation must DO.

| ID | Requirement | Source | Priority (MoSCoW) | Acceptance Criteria | Verification Method |
|----|-------------|--------|-------------------|---------------------|---------------------|
| FR-001 | [The system shall read input data from Excel file] | [SME Interview] | [Must Have] | [All columns mapped, data validated] | [Test with sample file] |
| FR-002 | [The robot shall process X transactions per hour] | [Process Owner] | [Must Have] | [≥X transactions/hour] | [Performance test] |
| FR-003 | [The robot shall log all actions to Orchestrator] | [IT Requirement] | [Must Have] | [All actions visible in logs] | [Log review] |

### 3.2 Non-Functional Requirements

> How well the automation must perform.

| ID | Category | Requirement | Target | Priority | Verification |
|----|----------|-------------|--------|----------|-------------|
| NFR-001 | Performance | Processing time per transaction | [≤X minutes] | [Must Have] | [Performance test] |
| NFR-002 | Availability | Robot uptime | [≥95% business hours] | [Must Have] | [Monitoring dashboard] |
| NFR-003 | Scalability | Peak volume handling | [X transactions/day] | [Should Have] | [Load test] |
| NFR-004 | Security | Credential handling | [UiPath Asset encrypted] | [Must Have] | [Security review] |
| NFR-005 | Maintainability | Code documentation | [All workflows documented] | [Should Have] | [Code review] |

### 3.3 Integration Requirements

> How the automation interacts with other systems.

| ID | System | Integration Type | Data Flow | Frequency | Error Handling |
|----|--------|-----------------|-----------|-----------|---------------|
| INT-001 | [ERP System] | [UI Automation / API] | [Read/Write] | [Per transaction] | [Retry 3x, then alert] |
| INT-002 | [Email System] | [IMAP/SMTP] | [Read emails, send notifications] | [Continuous] | [Log errors, continue] |
| INT-003 | [Database] | [SQL Query] | [Read reference data] | [Per transaction] | [Alert on failure] |

### 3.4 Security & Compliance Requirements

| ID | Requirement | Regulation/Policy | Implementation Approach | Verification |
|----|-------------|-------------------|------------------------|-------------|
| SEC-001 | [No PII in logs] | [GDPR] | [Data masking in log messages] | [Log review] |
| SEC-002 | [Audit trail retained for X years] | [SOX] | [Orchestrator logs + archive] | [Compliance audit] |
| SEC-003 | [Robot uses least-privilege access] | [IT Policy] | [Dedicated service account] | [Access review] |

---

## 4. Requirements Prioritization (MoSCoW)

### 4.1 MoSCoW Categories

| Category | Definition | Allocation Guideline |
|----------|------------|---------------------|
| **Must Have** | Critical for success; automation fails without these | 60% of effort |
| **Should Have** | Important but not critical; workarounds exist | 20% of effort |
| **Could Have** | Desirable; nice to have if time/budget allows | 15% of effort |
| **Won't Have (This Phase)** | Explicitly excluded; may be future phases | 5% (deferred) |

### 4.2 Requirements Prioritization Matrix

| ID | Requirement | Business Value (1-5) | Technical Complexity (1-5) | Risk if Omitted (1-5) | Priority Score | MoSCoW |
|----|-------------|---------------------|---------------------------|----------------------|----------------|--------|
| FR-001 | [Requirement] | [5] | [2] | [5] | [50] | [Must Have] |

**Priority Score = Business Value × Risk if Omitted × (6 - Technical Complexity)**

---

## 5. Requirements Validation

### 5.1 Validation Checklist

- [ ] Every requirement is **testable** (has acceptance criteria)
- [ ] Every requirement is **unambiguous** (single interpretation)
- [ ] Every requirement is **feasible** (technically achievable)
- [ ] Every requirement is **traceable** (source identified)
- [ ] Requirements are **consistent** (no contradictions)
- [ ] Requirements are **complete** (no gaps identified)
- [ ] Stakeholders have **reviewed and approved** requirements
- [ ] Requirements have been **prioritized** (MoSCoW assigned)

### 5.2 Requirements Review Session

**Preparation:**
- [ ] Compile all requirements into BRD format
- [ ] Distribute to stakeholders 48 hours before review
- [ ] Prepare demo/prototype for validation

**Review Agenda (60 min):**
```
1. Walk through each requirement (30 min)
2. Identify gaps, contradictions, ambiguities (15 min)
3. Validate prioritization (10 min)
4. Confirm acceptance criteria (5 min)
```

**Sign-Off:**
| Role | Name | Date | Signature |
|------|------|------|-----------|
| Business Analyst | [Name] | [Date] | [Signature] |
| Process Owner | [Name] | [Date] | [Signature] |
| IT Representative | [Name] | [Date] | [Signature] |

---

## 6. Requirements Traceability Matrix

> Link requirements to PDD sections, test cases, and solution components.

| Req ID | Requirement | PDD Section | Test Case ID | Solution Component | Status |
|--------|-------------|-------------|--------------|-------------------|--------|
| FR-001 | [Requirement] | [Section X.X] | [TC-001] | [Workflow Name] | [Draft/Approved/Implemented] |

---

## 7. Common Pitfalls & How to Avoid Them

| Pitfall | Symptom | Prevention |
|---------|---------|------------|
| **Vague requirements** | "Robot should be fast" | Use measurable targets: "Process ≤2 min/transaction" |
| **Missing exceptions** | Robot fails on edge cases | Ask "What could go wrong?" for every step |
| **Assuming process stability** | Process changes after development | Validate with historical data, not just SME recollection |
| **Overlooking IT requirements** | Access delays, security blocks | Engage IT early; document access, credential, network needs |
| **Ignoring change management** | Users resist automation | Communicate early, involve end users, provide training |
| **Scope creep** | Continuous requirement additions | Freeze requirements after sign-off; use change control |

---

## 8. Requirements Template (Quick Start)

> Use this template for rapid requirements capture.

### Process: [Process Name]

**Functional Requirements:**
1. [The robot shall... ] — Priority: [Must/Should/Could]
2. [The robot shall... ] — Priority: [Must/Should/Could]
3. [The robot shall... ] — Priority: [Must/Should/Could]

**Non-Functional Requirements:**
1. [Performance/Availability/Security] — Target: [X]
2. [Performance/Availability/Security] — Target: [X]

**Integration Requirements:**
1. [System] — [Type] — [Data flow]
2. [System] — [Type] — [Data flow]

**Security & Compliance:**
1. [Requirement] — [Regulation]
2. [Requirement] — [Regulation]

**Out of Scope:**
1. [Explicitly excluded]
2. [Explicitly excluded]

---

> **Guide Version**: 1.0
> **Last Updated**: [YYYY-MM-DD]
> **Maintained By**: [Business Analyst Name]
