---
name: financial-analysis
description: |
  Financial modeling, budgeting, and quantitative analysis for research
  documents. Use this skill for grant budgets, cost-benefit analyses,
  financial projections, feasibility assessments, ROI calculations, and
  economic impact modeling. Trigger on: "budget", "costs", "financial",
  "cost-benefit", "ROI", "projections", "economic analysis", "funding".
---

# Financial Analysis Skill

Quantitative analysis and financial modeling for research documents.

## Quick Start

1. **Define scope** - What financial question needs answering?
2. **Gather inputs** - Collect cost data, assumptions, constraints
3. **Build model** - Structure calculations appropriately
4. **Run scenarios** - Test sensitivity to assumptions
5. **Document clearly** - Show work, state assumptions

## Budget Development

### Grant Budget Structure

```markdown
## Budget Summary

| Category | Year 1 | Year 2 | Year 3 | Total |
|----------|--------|--------|--------|-------|
| Personnel | $X | $X | $X | $X |
| Fringe Benefits | $X | $X | $X | $X |
| Equipment | $X | $X | $X | $X |
| Supplies | $X | $X | $X | $X |
| Travel | $X | $X | $X | $X |
| Other Direct | $X | $X | $X | $X |
| **Total Direct** | $X | $X | $X | $X |
| Indirect Costs | $X | $X | $X | $X |
| **Total Budget** | $X | $X | $X | $X |
```

### Personnel Calculations

```
Annual Salary × % Effort × Project Months/12 = Personnel Cost

Example:
$80,000 salary × 50% effort × 12/12 months = $40,000
```

### Fringe Benefits
Apply institutional rates to personnel costs:
- Full-time employees: typically 25-35%
- Part-time/hourly: typically 8-15%
- Consultants: typically 0% (built into rate)

### Indirect Costs (F&A)
Apply negotiated rate to modified total direct costs:
```
(Total Direct - Equipment - Participant Support - Subcontract >$25K) × F&A Rate
```

## Cost-Benefit Analysis

### Framework

```markdown
## Cost-Benefit Analysis

### Costs (Present Value)

| Cost Category | Year 0 | Year 1 | Year 2 | PV |
|---------------|--------|--------|--------|-----|
| Initial Investment | $X | - | - | $X |
| Operating Costs | - | $X | $X | $X |
| Maintenance | - | $X | $X | $X |
| **Total Costs** | | | | $X |

### Benefits (Present Value)

| Benefit Category | Year 0 | Year 1 | Year 2 | PV |
|------------------|--------|--------|--------|-----|
| Revenue/Savings | - | $X | $X | $X |
| Avoided Costs | - | $X | $X | $X |
| Productivity Gains | - | $X | $X | $X |
| **Total Benefits** | | | | $X |

### Key Metrics
- Net Present Value (NPV): $X
- Benefit-Cost Ratio: X.X
- Internal Rate of Return: X%
- Payback Period: X years
```

### Present Value Calculation
```
PV = FV / (1 + r)^n

Where:
- PV = Present Value
- FV = Future Value
- r = Discount rate
- n = Number of periods
```

### NPV Calculation
```
NPV = Σ [Cash Flow_t / (1 + r)^t] - Initial Investment
```

## Financial Projections

### Revenue Projection Model

```markdown
## Revenue Projections

### Assumptions
- Market size: $X
- Addressable market: X%
- Market share target: X% (Year 1) → X% (Year 5)
- Price point: $X
- Growth rate: X% annually

### Projection

| Metric | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 |
|--------|--------|--------|--------|--------|--------|
| Market Size | $X | $X | $X | $X | $X |
| Market Share | X% | X% | X% | X% | X% |
| Units Sold | X | X | X | X | X |
| Revenue | $X | $X | $X | $X | $X |
```

### Pro Forma Income Statement

```markdown
## Pro Forma Income Statement

| Line Item | Year 1 | Year 2 | Year 3 |
|-----------|--------|--------|--------|
| Revenue | $X | $X | $X |
| COGS | ($X) | ($X) | ($X) |
| **Gross Profit** | $X | $X | $X |
| Operating Expenses | ($X) | ($X) | ($X) |
| **Operating Income** | $X | $X | $X |
| Interest/Taxes | ($X) | ($X) | ($X) |
| **Net Income** | $X | $X | $X |
```

## Feasibility Financial Assessment

### Break-Even Analysis

```
Break-Even Units = Fixed Costs / (Price - Variable Cost per Unit)

Break-Even Revenue = Fixed Costs / Contribution Margin Ratio

Contribution Margin Ratio = (Price - Variable Cost) / Price
```

### Funding Gap Analysis

```markdown
## Funding Gap Analysis

| Phase | Costs | Secured Funding | Gap |
|-------|-------|-----------------|-----|
| Phase 1 | $X | $X | $X |
| Phase 2 | $X | $X | $X |
| Phase 3 | $X | $X | $X |
| **Total** | $X | $X | $X |

### Gap Closure Strategy
- Source 1: $X (probability: X%)
- Source 2: $X (probability: X%)
- Source 3: $X (probability: X%)
```

## Sensitivity Analysis

### Tornado Diagram Data

```markdown
## Sensitivity Analysis

### Base Case NPV: $X

| Variable | Low Value | Base | High Value | NPV Range |
|----------|-----------|------|------------|-----------|
| Price | $X | $X | $X | $X to $X |
| Volume | X | X | X | $X to $X |
| Costs | $X | $X | $X | $X to $X |

### Key Findings
- Most sensitive to: [variable]
- NPV remains positive if: [conditions]
- Break-even threshold: [value]
```

### Scenario Analysis

```markdown
## Scenario Analysis

| Metric | Pessimistic | Base | Optimistic |
|--------|-------------|------|------------|
| Market Growth | X% | X% | X% |
| Market Share | X% | X% | X% |
| Price | $X | $X | $X |
| **NPV** | $X | $X | $X |
| **IRR** | X% | X% | X% |
```

## Budget Narrative Template

```markdown
## Budget Justification

### Personnel ($X)

**[Name], [Title]** - $X
[Name] will serve as [role], dedicating [X]% effort to [activities].
[Name]'s expertise in [area] is essential for [project component].
Salary is based on [institutional rate/market rate/prior funding].

### Fringe Benefits ($X)
Fringe benefits are calculated at [X]% for full-time staff and include
[health insurance, retirement, etc.] per institutional policy.

### Equipment ($X)
[Equipment item] ($X) is required for [purpose]. This [is/is not]
available through other institutional resources because [reason].

### Travel ($X)
- Conference travel: $X for [X] trips to [conferences] for dissemination
- Field work travel: $X for [X] site visits to [locations]

### Other Direct Costs ($X)
- [Item]: $X - [justification]
- [Item]: $X - [justification]

### Indirect Costs ($X)
Indirect costs are calculated at [X]%, the institution's federally
negotiated rate, applied to [MTDC base].
```

## Integration with Other Skills

- **research-analyst**: Receives data for financial modeling
- **content-writer**: Provides budget narratives for documents
- **illustration-design**: Creates financial charts and visualizations
- **report-formatter**: Formats financial tables and figures
