# Name - Ajay Singh
# id - Bitsom_Ba_2511011


# Campaign Experiment Analysis

## 1. Business Context

A subscription-based digital product company launched a new onboarding and activation campaign with the objective of improving user conversion and early engagement.

Users were divided into two groups:
- Control group: Existing onboarding experience
- Treatment group: New campaign experience

Leadership needs to decide whether the Treatment campaign should be launched to all users based on experiment results.

The business problem has 5 key components:
1. Decision: Should the new campaign replace the existing onboarding experience for all users?
2. Impacts: New users, product team, revenue team, support team, and leadership
3. Metric to improve: Paid conversion rate
4. Risks to monitor: Support ticket rate, refund rate, revenue quality, segment performance
5. Evidence required: Statistical significance at p < 0.05 on primary metric with guardrails stable

---

## 2. Dataset Description

**Source File:** campaign_experiment_data.xlsm
**Sheet:** experiment_data

| Property | Value |
|----------|-------|
| Original rows | 1,408 |
| Rows after cleaning | 1,400 |
| Control users | 690 |
| Treatment users | 710 |

**Columns Available:**
- user_id: Unique user identifier
- experiment_group: Control or Treatment
- region: North, South, East, West
- device_type: Mobile, Desktop, Tablet
- traffic_source: Organic, Paid Search, Social,
  Email, Referral
- plan_type: Free, Basic, Premium
- visited_landing_page: Binary (0/1)
- started_trial: Binary (0/1)
- completed_onboarding: Binary (0/1)
- converted_to_paid: Binary (0/1)
- revenue_30d: Revenue in 30 days
- refund_requested: Binary (0/1)
- support_tickets_30d: Number of tickets
- engagement_score: User engagement score
- days_to_convert: Days taken to convert

**Data Cleaning Actions:**

| Issue | Count | Action |
|-------|-------|--------|
| Duplicate user IDs | 8 rows | Removed, kept first |
| Missing device_type | 18 rows | Filled with Unknown |
| Missing traffic_source | 24 rows | Filled with Unknown |
| Missing engagement_score | 14 rows | Excluded from avg |

- Revenue outliers  Winsorized at $1,496


**Segment Distribution Check:**

| Segment | Issue | Impact |
|---------|-------|--------|
| Region | North overrepresented in Control | Minor |
| Device Type | Well balanced | None |
| Traffic Source | Email gap ~2.8pp | Minor |
| Plan Type | Well balanced | None |

---

## 3. North Star Metric Selected

**Metric: Paid Conversion Rate**
Definition: Users converted to paid / Total users

| Group | Rate |
|-------|------|
| Control | 3.19% |
| Treatment | 7.04% |

**Why This is the North Star:**
Paid conversion rate is the only metric that directly confirms the campaign achieved its core business objective — a user paying for the product.All other metrics are intermediate funnel steps.

**Why Other Metrics Are Supporting:**
- Landing page visit rate: Measures awareness only
- Trial start rate: Measures intent, not payment
- Onboarding completion: Measures activation only
- Engagement score: Measures activity, not revenue
- Revenue per user: Depends on conversion first

**Business Growth Connection:**
At 10,000 users — Treatment generates 385 more paying customers and $210,686 more revenue than
Control.

**Risk of Blind Optimization:**
- Support tickets increased +67.7%
- Revenue per converted user dropped -21.2%
- Social traffic conversion declined -22%
- Basic plan users show only +7% lift

---

## 4. KPI Tree Summary

```
NORTH STAR: Paid Conversion Rate (3.19% → 7.04%)
│
├── DRIVER 1: Funnel Progression
│   ├── Landing Page Visit Rate (+13.8%, p=0.000432)
│   ├── Trial Start Rate (+15.7%, p=0.048514)
│   └── Onboarding Completion Rate (+35%, p=0.004129)
│
├── DRIVER 2: User Engagement
│   ├── Engagement Score (+10.4%, p<0.000001)
│   └── Avg Days to Convert (8.9 → 6.4 days)
│
├── DRIVER 3: Revenue Impact
│   ├── Avg Revenue Per User (+74%, p=0.023)
│   └── Avg Revenue Per Converted User (-21.2%)
│
└── GUARDRAIL METRICS
    ├── Support Ticket Rate (+67.7%)  BREACHED
    ├── Refund Rate (0% → 0.42%)  Monitor
    └── Revenue Per Converted User (-21.2%)  Investigate
```

---

## 5. Experiment Analysis Approach

**Tool Used:** Microsoft Excel
**Analysis File:** analysis/experiment_analysis.xlsx

**Sheets Created:**
- Clean_Data: Cleaned dataset with new columns
- Summary: Control vs Treatment comparison
- AB_Test: Statistical hypothesis test results
- Seg_Conversion: Conversion rate by 4 segments
- Seg_Support: Support ticket rate by 4 segments
- Seg_Revenue: Revenue by 4 segments

**New Columns Added to Clean_Data:**
- revenue_30d_wins: Revenue capped at $1,496
- has_support_ticket: Binary (1 if tickets > 0)

**Segment Analysis Performed:**
- By Region (North, South, East, West)
- By Device Type (Mobile, Desktop, Tablet)
- By Traffic Source (Organic, Paid, Social, Email,
  Referral)
- By Plan Type (Free, Basic, Premium)

**Metrics Analyzed by Segment (minimum 3):**
1. Paid Conversion Rate
2. Support Ticket Rate
3. Average Revenue Per User

---

## 6. Hypothesis Test Summary

**Test 1: Paid Conversion Rate (Primary)**
- Type: One-tailed Z-test
- H0: p_treatment = p_control
- H1: p_treatment > p_control
- Z-Score: 3.264 | P-Value: 0.00055
- Alpha: 0.05
- Result: Reject H0  Significant

---

## 7. Guardrail Metrics Considered

| Metric | Control | Treatment | Status |
|--------|---------|-----------|--------|
| Support Ticket Rate | 14.78% | 24.79% |  BREACHED |
| Refund Rate | 0.00% | 0.42%  |  Monitor |
| Revenue Per Converted | $894.60 | $704.72 |  Investigate |

**Support Ticket Rate:** Critically breached at p=0.0000027. Indicates widespread user confusion with new onboarding experience. Must be resolved
before launch.

**Refund Rate:** Small absolute increase (3 users). Not statistically significant (p=0.087) but directionally concerning. Monitor post-launch.

**Revenue Per Converted User:** Significant decline in revenue quality per converted user. However otal revenue still increases due to volume gains. Requires investigation into plan mix of converts.

---

## 8. Final Recommendation

**CONDITIONAL LAUNCH ⚠️**

**Data Supporting Launch:**
- Paid conversion: +121% (p=0.00055) 
- Revenue per user: +74% (p=0.023) 
- Engagement score: +10.4% (p<0.000001) 
- All funnel metrics statistically significant 

**Data Against Immediate Launch:**
- Support tickets: +67.7% (p=0.0000027) 
- Social traffic conversion: -22% 
- Basic plan lift: only +7% 
- West region lift: only +51% 

**Decision:** Fix support ticket issue and social traffic performance first. Then proceed with full rollout. Campaign has strong business case once UX issues are resolved.

---

## 9. Assumptions and Limitations

**Assumptions:**
- Users were randomly assigned to groups
- Experiment ran for sufficient duration
- No external events affected one group only
- Revenue outliers (>$3,503) treated as valid data and winsorized at 99th percentile

**Limitations:**
- Experiment duration unknown — long term retention and churn cannot be assessed
- No demographic data available for deeper user segmentation analysis
- Social creative content not evaluated — cannot determine if decline is UX or creative
- Minor group size imbalance (690 vs 710)
- North region overrepresented in Control
- Revenue per converted user decline not fully explained by available data

---

## 10. Screenshots Included

| Screenshot File | Contents |
|-----------------|----------|
| screenshots/hypothesis_test_output.png | AB Test results in Excel |
| screenshots/kpi_tree_preview.png | KPI Tree diagram |

**Output Files:**
| File | Description |
|------|-------------|
| outputs/experiment_summary.xlsx | Full metrics summary |
| outputs/kpi_tree.png | KPI Tree image |
| outputs/recommendation_memo.md | Full recommendation |
| outputs/north_star_metric.md | North Star explanation |
| outputs/guardrail_metrics.md | Guardrail evaluation |
| analysis/experiment_analysis.xlsx | Full analysis workbook |
| analysis/hypothesis_test_notes.md | Hypothesis test notes |