# Sample PDD Excerpt — Invoice Processing

> **Purpose**: Example of a completed PDD section for reference
> **Process**: Accounts Payable — Invoice Processing
> **Note**: This is a partial excerpt demonstrating PDD quality and structure

---

## 2. Process Overview

### 2.1 Process Summary

| Field | Description |
|-------|-------------|
| **Process Name** | Invoice Processing (Accounts Payable) |
| **Process ID** | P-AP-001 |
| **Department** | Finance — Accounts Payable |
| **Process Type** | Transactional — Data Entry & Validation |
| **Trigger** | Invoice received via email (AP inbox) |
| **Frequency** | Daily |
| **Average Processing Time** | 12 minutes per invoice |
| **Monthly Volume** | 3,500 invoices/month |
| **Number of FTEs** | 2.5 FTEs |
| **Error Rate** | 4.2% (primarily data entry errors) |

### 2.2 Process Scope

**In Scope:**
- Invoice receipt and extraction (email attachments: PDF, scanned PDF, Excel)
- 3-way match (PO, Goods Receipt, Invoice)
- Data entry into ERP (SAP)
- Exception handling (mismatches, missing POs)
- Approval routing for exceptions

**Out of Scope:**
- Vendor master data management (separate process)
- Payment execution (handled by Treasury team)
- Non-PO invoice processing (Phase 2)

---

## 3. Applications Used in the Process

| # | Application Name | Version | Type | Access Method | Authentication | Notes |
|---|-----------------|---------|------|---------------|----------------|-------|
| 1 | Microsoft Outlook | O365 | Desktop | Direct | SSO | Invoice inbox: ap@company.com |
| 2 | SAP ECC | 6.0 EHP8 | GUI (Windows) | Direct | SAP credentials | MIRO transaction for invoice posting |
| 3 | Shared Drive (SP) | — | File System | Direct | Windows AD | Vendor invoices archived here |
| 4 | Excel (PO List) | O365 | Desktop | Direct | SSO | Weekly PO extract, updated Mondays |

### 3.1 Application Constraints

| Application | Constraint | Impact on Automation |
|-------------|------------|---------------------|
| SAP ECC | Classic SAP GUI; no API available for MIRO | Requires UI automation; stable selectors confirmed |
| Scanned PDF Invoices | Non-searchable PDFs (images) | Requires OCR (UiPath Document Understanding) |

---

## 6. Detailed As-Is Process Steps

### 6.1 Invoice Receipt and Classification

| # | Action Title | Description | Estimated Time | Action Type | Notes |
|---|-------------|-------------|----------------|-------------|-------|
| 6.1.1 | Check AP Inbox | Open Outlook, navigate to AP inbox folder | 30 sec | Navigation | Performed every 30 minutes |
| 6.1.2 | Open Email & Attachment | Open email, download PDF attachment to local folder | 1 min | Click/Keystroke | Some emails have multiple attachments |
| 6.1.3 | Classify Invoice Type | Determine if PO or non-PO invoice based on content | 2 min | Decision | PO invoices have PO number on first page |
| 6.1.4 | Log in Tracking Sheet | Record invoice details in Excel tracking sheet | 1 min | Data Entry | Manual entry; prone to typos |

### 6.2 3-Way Match (PO Invoices)

| # | Action Title | Description | Estimated Time | Action Type | Notes |
|---|-------------|-------------|----------------|-------------|-------|
| 6.2.1 | Open SAP — MIRO | Launch SAP, navigate to MIRO transaction | 1 min | Navigation | Requires SAP login |
| 6.2.2 | Enter PO Number | Input PO number from invoice into SAP | 30 sec | Data Entry | Copy from invoice |
| 6.2.3 | Verify Goods Receipt | Check if GR has been posted for the PO | 1 min | Navigation/Decision | If no GR, flag for follow-up |
| 6.2.4 | Match Invoice to PO | Compare invoice amount/quantity to PO and GR | 3 min | Decision | Tolerances: $5 or 2% |
| 6.2.5 | Post or Flag | If match: post invoice; if mismatch: flag for approval | 2 min | Decision/Data Entry | ~15% of invoices require approval |

---

## 7. To-Be Process Description

### 7.1 To-Be Process Map

```
[Email Trigger] → [Robot checks AP inbox] → [Downloads attachment]
       → [Document Understanding extracts data]
       → [Classifies as PO/Non-PO]
       → [Robot opens SAP MIRO]
       → [Performs 3-way match]
       → {Match?}
          ├─ YES → [Post invoice] → [Log result] → [Send confirmation email]
          └─ NO  → [Flag for approval] → [Action Center task to AP Manager]
                   → [Manager approves/rejects] → [Robot posts or returns to vendor]
```

### 7.2 To-Be Detailed Process Steps

| Step # | Activity | Actor | System | Expected Time | Notes |
|--------|----------|-------|--------|---------------|-------|
| 1 | Check inbox, download attachment | Robot | Outlook | 15 sec | Every 15 minutes |
| 2 | Extract data via DU | Robot | Document Understanding | 30 sec | ML-based extraction |
| 3 | Classify PO/Non-PO | Robot | Rule engine | 5 sec | PO number present = PO invoice |
| 4 | 3-way match in SAP | Robot | SAP (MIRO) | 2 min | Automated match |
| 5a | Post matching invoice | Robot | SAP (MIRO) | 1 min | Auto-post if within tolerance |
| 5b | Flag mismatch | Robot → Human | Action Center | N/A | Manager reviews within 4 hours |
| 6 | Log and confirm | Robot | Email + Tracking | 10 sec | Confirmation to vendor contact |

### 7.3 Business Exception Handling

| Exception Type | Description | Frequency | Handling Approach | Escalation Path |
|----------------|-------------|-----------|-------------------|-----------------|
| No PO found | Invoice references non-existent PO | ~3% | Flag, email to procurement for investigation | Procurement team resolves within 24h |
| Goods Receipt missing | GR not yet posted in SAP | ~8% | Queue item flagged; retry next day | Auto-escalate after 3 days |
| Amount mismatch >tolerance | Invoice amount differs from PO by >$5 or >2% | ~5% | Route to AP Manager via Action Center | Manager approves or requests vendor revision |
| Unreadable scan | OCR confidence <70% | ~2% | Flag for manual review by AP team | AP team re-types data; feedback to DU model |

---

## 9. Key Performance Indicators (KPIs)

### 9.1 Current (As-Is) KPIs

| KPI | Current Value | Target |
|-----|---------------|--------|
| Processing Time | 12 min/invoice | 2 min/invoice |
| Error Rate | 4.2% | <0.5% |
| Throughput | 28 invoices/hour | 60 invoices/hour |
| Cost per Invoice | $3.50 | $0.50 |

### 9.2 Expected (To-Be) KPIs

| KPI | Expected Value | Improvement |
|-----|----------------|-------------|
| Processing Time | 2 min/invoice | 83% faster |
| Error Rate | 0.3% | 93% reduction |
| Throughput | 60 invoices/hour | 114% increase |
| FTE Reallocation | 2.0 FTEs | Reallocated to exception handling and vendor management |

---

> **This is a sample excerpt for illustration purposes only.**
> **A complete PDD includes all 13 sections plus appendices.**
