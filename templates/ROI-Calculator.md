# ROI Calculator Template

> **Purpose**: Calculate Return on Investment for UiPath automation projects
> **Methodology**: Based on official UiPath ROI methodology and industry best practices
> **Reference**: See `references/roi-methodology.md` for complete methodology

---

## Input Parameters

> Fill in the following values based on baseline process data. If data is unavailable, use estimates and flag as assumptions.

### Baseline Metrics (As-Is Process)

| Parameter | Value | Source/Notes |
|-----------|-------|--------------|
| **Number of FTEs** | [X.X FTEs] | [Current headcount performing process] |
| **Fully Loaded Annual Cost per FTE** | [$XX,XXX] | [Salary + benefits + overhead; use regional average if unknown] |
| **Monthly Transaction Volume** | [X,XXX transactions] | [Average monthly volume] |
| **Annual Transaction Volume** | [X,XXX × 12 = XXXX transactions] | [Calculated] |
| **Average Processing Time per Transaction** | [X.X minutes] | [Manual processing time] |
| **Annual Processing Hours** | [(Volume × Time) / 60 = XXXX hours] | [Calculated] |
| **Error Rate** | [X.X%] | [Percentage of transactions requiring rework] |
| **Average Rework Time per Error** | [X.X minutes] | [Time to correct an error] |
| **Cost per Error** | [$XXX] | [Financial impact per error, if applicable] |

---

## ROI Calculations

### 1. Annual Cost of Manual Process

```
Annual Labor Cost = FTE Count × Fully Loaded Cost per FTE
                  = [X.X] × [$XX,XXX]
                  = [$XXX,XXX]
```

```
Annual Error Cost = Annual Volume × Error Rate × Cost per Error
                  = [XXXX] × [X.X%] × [$XXX]
                  = [$XX,XXX]
```

```
Annual Rework Labor Cost = (Annual Volume × Error Rate × Rework Time / 60) × Hourly Rate
                         = [XXXX] × [X.X%] × [X.X min / 60] × [$/hour]
                         = [$XX,XXX]
```

```
Total Annual Cost (As-Is) = Annual Labor Cost + Annual Error Cost + Annual Rework Labor Cost
                          = [$XXX,XXX] + [$XX,XXX] + [$XX,XXX]
                          = [$XXX,XXX]
```

### 2. Implementation Cost (Year 1)

| Cost Component | Amount | Notes |
|----------------|--------|-------|
| **UiPath Licenses** | [$XX,XXX] | [Attended/Unattended robot licenses × quantity × annual cost] |
| **Development Cost** | [$XX,XXX] | [Developer hours × hourly rate] |
| **Infrastructure** | [$X,XXX] | [Server, VM, network costs (if incremental)] |
| **Training & Change Management** | [$X,XXX] | [SME time, training sessions] |
| **Contingency (15%)** | [$X,XXX] | [Standard contingency] |
| **Total Implementation Cost** | **[$XXX,XXX]** | |

### 3. Annual Savings (To-Be)

```
Expected Automation Efficiency Gain = [70-95%] of manual effort
Typical Range: 70% (complex processes) to 95% (rule-based, high volume)

Annual Savings (Labor) = Total Annual Cost × Efficiency Gain
                       = [$XXX,XXX] × [XX%]
                       = [$XXX,XXX]

Annual Savings (Error Reduction) = Annual Error Cost × Error Reduction %
                                 = [$XX,XXX] × [80-95%]
                                 = [$XX,XXX]

Total Annual Savings = Annual Savings (Labor) + Annual Savings (Error Reduction)
                     = [$XXX,XXX] + [$XX,XXX]
                     = [$XXX,XXX]

Annual Maintenance Cost = 15-20% of Development Cost
                        = [Development Cost] × 15%
                        = [$X,XXX]

Net Annual Savings = Total Annual Savings - Annual Maintenance Cost
                   = [$XXX,XXX] - [$X,XXX]
                   = [$XXX,XXX]
```

### 4. Payback Period

```
Payback Period = Total Implementation Cost / Net Monthly Savings
               = [$XXX,XXX] / [Net Annual Savings / 12]
               = [X.X months]
```

### 5. 3-Year Financial Analysis

```
Discount Rate = [X%] (typically 8-12% per organization's cost of capital)

Year 0 (Implementation): -[$XXX,XXX]
Year 1 Net Cash Flow: +[$XXX,XXX] - [$XXX,XXX] (partial year, if applicable)
Year 2 Net Cash Flow: +[$XXX,XXX]
Year 3 Net Cash Flow: +[$XXX,XXX]

NPV = Σ [Net Cash Flow / (1 + discount_rate)^year] - Initial Investment
    = [Year 1 / (1 + r)^1] + [Year 2 / (1 + r)^2] + [Year 3 / (1 + r)^3] - Initial Investment
    = [$XXX,XXX]

ROI (3-Year) = (Total Benefits - Total Costs) / Total Costs × 100
             = [XXX%]

IRR = [X%] (Internal Rate of Return — rate at which NPV = 0)
```

---

## Sensitivity Analysis

> Test the robustness of the ROI under different scenarios.

| Scenario | Volume Change | Efficiency | Net Annual Savings | Payback Period | 3-Year NPV |
|----------|--------------|------------|-------------------|----------------|------------|
| **Base Case** | 0% | [XX%] | [$XXX,XXX] | [X.X mo] | [$XXX,XXX] |
| **Optimistic** | +20% | [XX% + 5%] | [$XXX,XXX] | [X.X mo] | [$XXX,XXX] |
| **Pessimistic** | -20% | [XX% - 10%] | [$XXX,XXX] | [X.X mo] | [$XXX,XXX] |
| **Volume Spike** | +50% | [XX%] | [$XXX,XXX] | [X.X mo] | [$XXX,XXX] |

---

## Intangible Benefits

> Document benefits that are difficult to quantify financially.

| Benefit | Description | Impact Level (H/M/L) |
|---------|-------------|---------------------|
| **Improved Accuracy** | Reduced human error in data processing | [H/M/L] |
| **Faster Processing** | Shorter cycle times for [process] | [H/M/L] |
| **Employee Satisfaction** | Staff reallocated from repetitive to value-add work | [H/M/L] |
| **Scalability** | Ability to handle volume spikes without hiring | [H/M/L] |
| **Compliance** | Consistent, auditable execution | [H/M/L] |
| **24/7 Operation** | Unattended robots can run outside business hours | [H/M/L] |

---

## FTE Reallocation Plan

| FTE | Current Role | Post-Automation Role | Value-Add Activity |
|-----|-------------|---------------------|-------------------|
| [X FTEs] | [Data Entry Clerk] | [Customer Service Representative] | [Handle escalated inquiries] |
| [X FTEs] | [Processor] | [Analyst] | [Exception handling, reporting] |

---

## ROI Summary

| Metric | Value |
|--------|-------|
| **Total Implementation Cost** | [$XXX,XXX] |
| **Net Annual Savings** | [$XXX,XXX] |
| **Payback Period** | [X.X months] |
| **3-Year NPV** | [$XXX,XXX] |
| **3-Year ROI** | [XXX%] |
| **IRR** | [X%] |
| **Recommendation** | [Proceed / Proceed with Pilot / Re-evaluate] |

---

## Automation Suitability Score

> Based on UiPath process assessment criteria.

| Criteria | Score (0-10) | Weight | Weighted Score |
|----------|--------------|--------|----------------|
| Rule-based decisions | [0-10] | 20% | [X.X] |
| Process stability | [0-10] | 15% | [X.X] |
| Digital inputs | [0-10] | 15% | [X.X] |
| Standardization | [0-10] | 15% | [X.X] |
| Volume/FTE justification | [0-10] | 15% | [X.X] |
| System accessibility | [0-10] | 10% | [X.X] |
| Error handling feasibility | [0-10] | 10% | [X.X] |
| **Total** | | **100%** | **[X.X / 10]** |

**Suitability Rating:**
- 8.0-10.0: **Excellent** — Proceed with confidence
- 6.0-7.9: **Good** — Proceed with identified risks
- 4.0-5.9: **Moderate** — Pilot recommended before full rollout
- 0.0-3.9: **Low** — Consider alternative approaches

---

## Assumptions & Limitations

1. [Assumption 1 — e.g., "Volume remains stable for 12 months"]
2. [Assumption 2 — e.g., "Fully loaded FTE cost is based on regional averages"]
3. [Limitation 1 — e.g., "Error rate based on SME estimate, not historical data"]

---

## Next Steps

- [ ] Validate inputs with Process Owner and SME
- [ ] Obtain historical volume data (12 months if available)
- [ ] Confirm license costs with UiPath sales team
- [ ] Review with Finance team for NPV/discount rate alignment
- [ ] Present ROI summary to steering committee
- [ ] If approved: Proceed to PDD and solution design

---

> **Calculation Date**: [YYYY-MM-DD]
> **Prepared By**: [Business Analyst Name]
> **Reviewed By**: [Process Owner / Finance]
