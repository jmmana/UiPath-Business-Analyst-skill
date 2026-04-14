# PDD Guidelines Reference

> **Source**: [UiPath Task Capture - Process Definition Document](https://docs.uipath.com/task-capture/)
> **Purpose**: Reference guide for PDD structure, content requirements, and best practices
> **Alignment**: UiPath Automation Business Analyst certification objectives

---

## What is a PDD?

A Process Definition Document (PDD) is the foundational document that captures the complete As-Is process and defines the To-Be automated process. It serves as:

- The basis for solution design and development
- A communication tool for stakeholders
- An audit trail for compliance
- A reference for testing and validation

---

## PDD Structure (Official UiPath Task Capture Format)

### Section 1: Introduction

**Purpose**: Define the document's scope and objectives.

| Sub-Section | Content | Auto-Populated? |
|-------------|---------|-----------------|
| Document Purpose | Why this PDD exists | No |
| Objectives | What the automation should achieve | No |
| Process Key Contacts | Stakeholders and roles | No |
| Minimum Pre-requisites | Automation readiness checklist | Partial |

**Best Practices:**
- Clearly state what is IN and OUT of scope
- Identify all key contacts with contact information
- Confirm pre-requisites before proceeding to detailed analysis

---

### Section 2: Process Overview

**Purpose**: High-level summary of the process.

| Sub-Section | Content | Auto-Populated? |
|-------------|---------|-----------------|
| Process Summary | Name, type, trigger, frequency, volume, FTEs | Partial |
| Process Scope | In-scope and out-of-scope activities | No |
| Business Criticality | Impact, regulatory drivers, SLAs | No |

**Key Fields:**
- **Process Type**: Transactional, Reporting, Data Entry, Validation, etc.
- **Trigger**: What initiates the process (email, schedule, event, user)
- **Frequency**: How often the process runs
- **Volume**: Number of transactions (monthly/annual)
- **FTEs**: Current effort allocation

---

### Section 3: Applications Used in the Process

**Purpose**: Document all systems and tools involved.

| Field | Description |
|-------|-------------|
| Application Name | Official name of the application |
| Version | Version number (if relevant) |
| Type | Web, Desktop, Mainframe, SAP, Citrix, API |
| Access Method | Direct, VDI, Citrix, RDP |
| Authentication | SSO, credentials, MFA |
| Notes | Known limitations, licensing constraints |

**Best Practices:**
- Verify application accessibility for automation
- Flag Citrix/VDI environments (require Computer Vision)
- Note any applications with anti-automation measures

---

### Section 4: As-Is Process Map

**Purpose**: Visual representation of the current process flow.

**Auto-Populated**: Yes (from Task Capture process capture)

**If creating manually:**
- Use BPMN notation or simple flowchart
- Show start, end, decision points, and key activities
- Keep at high level (10-20 steps maximum for overview)

---

### Section 5: Process Statistics

**Purpose**: Quantitative analysis of the process.

| Sub-Section | Content |
|-------------|---------|
| High-Level Statistics | Total steps, manual steps, decision points, systems |
| Detailed Statistics | Per-step metrics (time, frequency, error rate, rework) |

**Key Metrics to Capture:**
- Total processing time (touch time + wait time)
- Error rate per step
- Rework time per error
- Bottleneck identification

---

### Section 6: Detailed As-Is Process Steps

**Purpose**: Step-by-step breakdown of every action in the process.

| Field | Description |
|-------|-------------|
| Action Title | Brief name for the action |
| Description | Detailed explanation of what is done |
| Estimated Time | How long the action takes |
| Action Type | Click, Keystroke, Navigation, Data Entry, Decision |
| Screenshot | Visual reference (if applicable) |

**Best Practices:**
- Capture every step (no assumptions about "obvious" steps)
- Note decision points and their logic
- Document all applications used at each step
- Include exception paths, not just the happy path

---

### Section 7: To-Be Process Description

**Purpose**: Define how the process will work after automation.

| Sub-Section | Content |
|-------------|---------|
| To-Be Process Map | Workflow showing automated flow |
| To-Be Detailed Steps | Step-by-step with robot/human assignment |
| Out of Scope of RPA | Sub-processes not being automated |
| Business Exception Handling | How business exceptions are managed |
| Application Error Handling | How system errors are managed |

**Best Practices:**
- Clearly distinguish robot actions from human actions
- Define approval points (use Action Center if human approval needed)
- Document all exception scenarios and handling approaches
- Specify reporting requirements

---

### Section 8: Reporting Requirements

**Purpose**: Define what reports and metrics the automation must produce.

| Report Type | Frequency | Audience | Format | Delivery |
|-------------|-----------|----------|--------|----------|
| Transaction Summary | Daily | Process Owner | Email | Automated |
| Exception Report | Real-time | Support Team | Dashboard | Alert |
| Performance Metrics | Weekly | Management | Dashboard | Scheduled |

---

## PDD Quality Checklist

Before finalizing a PDD, verify:

- [ ] All mandatory sections are complete
- [ ] Process statistics are based on data (not estimates)
- [ ] As-Is steps capture every action
- [ ] To-Be clearly distinguishes robot vs. human actions
- [ ] Exception handling covers business AND system exceptions
- [ ] Reporting requirements are defined
- [ ] Risks and mitigations are documented
- [ ] Assumptions and dependencies are listed
- [ ] Stakeholders have reviewed and signed off

---

## Common PDD Pitfalls

| Pitfall | Symptom | How to Avoid |
|---------|---------|-------------|
| **Incomplete As-Is** | Developer discovers undocumented steps | Shadow multiple SMEs; observe real execution |
| **Vague To-Be** | "Robot processes data" without specifics | Define exact steps, systems, decision logic |
| **Missing exceptions** | Robot fails on edge cases | Ask "What could go wrong?" for every step |
| **Unrealistic volume estimates** | ROI doesn't materialize | Get 12 months of historical data |
| **No stakeholder sign-off** | Rework after development | Require formal sign-off before development starts |

---

## PDD and Downstream Artifacts

| Artifact | Relationship to PDD |
|----------|-------------------|
| **Solution Design Document (SDD)** | SDD is derived from the PDD's To-Be section |
| **Test Cases** | Test cases validate PDD requirements |
| **ROI Calculation** | Uses PDD baseline metrics |
| **Process Assessment** | Precedes PDD; determines if PDD should be created |

---

## References

- [UiPath Task Capture Documentation](https://docs.uipath.com/task-capture/)
- [UiPath Task Capture - PDD Details](https://docs.uipath.com/task-capture/standalone/latest/user-guide/details-about-the-pdd)
- [UiPath Automation Business Analyst Learning Plan](https://academy.uipath.com/)

---

> **Document Version**: 1.0
> **Last Updated**: [YYYY-MM-DD]
> **Maintained By**: UiPath Business Analyst Skill
