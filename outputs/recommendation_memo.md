
### Task 1:  Understand the Business Problem

# 1: What Decision Needs to Be Made
Should the new onboarding and activation campaign be launched to all users?

Leadership needs to decide whether to replace the existing onboarding experience with the new campaign experience for all users.

---
# 2:Who the Decision Impacts
- New users who will go through onboarding
- Product team responsible for user experience
- Revenue and growth teams
- Customer support team
- Leadership and stakeholders

---
# 3: What Metric Should Improve
Primary Metric: Paid Conversion Rate
- Users converted to paid / total users
- Control: 3.19%
- Treatment: 7.04%

Supporting Metrics:
- Trial start rate
- Onboarding completion rate
- Average revenue per user
- Average engagement score

---
# 4:What Risks Must Be Monitored
1. Support Ticket Rate
   - Control: 14.8%
   - Treatment: 24.8%
   - Risk: Campaign confusing users

2. Refund Rate
   - Must not increase significantly

3. Revenue Outliers
   -outliers detected
   - Wins at 99th percentile ($1,496)

4. Segment Imbalance
   - North region overrepresented in Control
   - Email traffic underrepresented in Treatment

---

# 5: What evidence is required before making a recommendation

Before making final recommendation:

1. Paid conversion rate must significantly 
   improve (p < 0.05) CONFIRMED
   
2. Revenue per user must increase  CONFIRMED

3. Support ticket rate must not significantly 
   increase BREACHED

4. Refund rate must remain stable

5. Results must hold across key segments

---





### Task 2: Define the North Star Metric:

## Selected North Star Metric: Paid Conversion Rate

**Definition:** Number of users who converted to paid / Total users in the group

- Control: 3.19%
- Treatment: 7.04%

---

## 1. Why This Metric is the Main Success Metric

The objective of this campaign is to improve userconversion and early engagement for asubscription-based digital product company.
Paid Conversion Rate is the only metric that directlymeasures whether a user has committed financially tothe product. Every other metric in this experimentrepresents a step in the funnel — but only paidconversion confirms that the campaign has achievedits ultimate business goal.
A user can visit the landing page, start a trial,and complete onboarding — yet still never pay.Paid conversion is the definitive signal that thecampaign worked.

---

## 2. Why Other Metrics Are Supporting Metrics



 - Landing Page Visit Rate - Measures awareness, not commitment 
 - Trial Start Rate - Measures intent, not conversion 
 - Onboarding Completion Rate - Measures activation, not revenue 
 - Average Engagement Score -Measures activity, not payment 
 - Average Revenue Per User - Depends on conversion happening first 
 - Average Days to Convert - Measures speed, not whether it happened 
 - Support Ticket Rate - Guardrail metric, not a success metric 
 - Refund Rate - Risk metric, not a success metric 

These metrics are valuable for diagnosing what drivesor blocks conversion, but none of them confirm thatthe business goal has been achieved. They supportthe North Star — they do not replace it.

---

## 3. How This Metric Connects to Business Growth

For a subscription-based company, revenue is drivendirectly by the number of paying users. Paidconversion rate is the bridge between user acquisitionand business revenue.

If paid conversion rate improves:
- More users become paying customers
- Monthly Recurring Revenue (MRR) increases
- Customer Lifetime Value (LTV) grows
- The business can reinvest in acquiring more users

-More paid conversions = more subscribers = more recurring revenue. 

## 4. What Could Go Wrong if this metric Optimized Blindly

- Risk 1 — Support Ticket Rate Increased
Optimizing only for conversion caused a 68% increasein support tickets (14.78% to 24.79%). This meansusers are confused by the new experience. Highersupport volume increases operational costs anddamages user satisfaction, which threatens retention.

- Risk 2 — Revenue Per Converted User Declined
Despite more conversions, revenue per converted userdropped from $894.60 to $704.72 (-21.2%). Thissuggests the campaign may be attracting lower-valueusers or pushing users toward cheaper plans. Blindoptimization of conversion rate can reduce overallrevenue quality.

- Risk 3 — Segment Performance Varies Significantly
- Social traffic: conversion rate decreased -22%
- Basic plan users: only +7% lift
- West region: weakest lift at +51%

Blindly launching to all users ignores these segments
where the campaign underperforms or causes harm.

- Risk 4 — Long Term Retention Risk
A campaign that converts users through confusion orpressure may generate short-term conversion gainsbut lead to higher churn, refund requests, andnegative brand perception over time.

---






### Task 8: Evaluate Guardrail Metrics


Guardrail metrics ensure that conversion improvementdoes not come at the cost of user experience, revenuequality, or business health. 

---

## Guardrail 1: Support Ticket Rate

**Definition:** Users with at least 1 support ticket / Total users



- Control = 102 / 690 = 14.78% 
- Treatment = 176 / 710  = 24.79% 


**Statistical Test:** Two-tailed Z-test
- Z-Score: 4.692
- P-Value: 0.0000027
- Alpha: 0.05
- Result: Statistically significant increase

**Risk Assessment:  HIGH RISK — GUARDRAIL BREACHED**

Support ticket rate increased by 67.7% in theTreatment group. This is statistically significantand indicates that the new onboarding experienceis causing widespread user confusion and friction.

A 10 percentage point increase in support tickets at scale means:
- Significantly higher customer support costs
- Reduced user satisfaction and trust
- Increased risk of churn after conversion
- Potential damage to brand reputation

**Conclusion:** This guardrail is breached. Thecampaign must not be launched to all users untilthe root cause of support ticket increase is identified and resolved.

---

## Guardrail 2: Refund Rate

**Definition:** Users who requested a refund / Total users


 - Control = 0 / 690  =0.00% 
 - Treatment = 3 / 710 = 0.42% 


**Risk Assessment:  LOW RISK — MONITOR CLOSELY**

While the absolute increase is small (0.42%), thefact that Control had zero refunds and Treatmenthad 3 refunds is worth monitoring. This couldindicate that some users are converting underpressure or confusion and then requesting refunds.

At scale with 10,000 users this would meanapproximately 42 refund requests that did notexist before. If refund rate continues to grow,it would directly reduce net revenue.

**Conclusion:** Not a blocker for launch but mustbe actively monitored after rollout. If refundrate exceeds 1% post-launch, immediate investigationis required.

---

## Guardrail 3: Revenue Quality
## (Average Revenue Per Converted User)

**Definition:** Total revenue / Number of converted users

| Group | Converted Users | Avg Revenue | 
|-------|-----------------|-------------|
| Control | 22 | $894.60 |
| Treatment | 50 | $704.72 |


**Risk Assessment: ⚠️ MEDIUM RISK — INVESTIGATE**

Although more users converted in Treatment (+121%),the revenue per converted user dropped by 21.2%.This means Treatment is attracting lower-value customers or pushing users toward cheaper plans.

This is a hidden risk — the conversion rate looksexcellent but the quality of those conversions is lower. If this trend continues at scale:

| Scenario | Conversions | Rev Per User | Total Revenue |
|----------|-------------|--------------|---------------|
| Control (10k users) | 319 | $894.60 | $285,277 |
| Treatment (10k users) | 704 | $704.72 | $495,963 |

Total revenue still increases significantly despitelower revenue per converted user, because volumegain outweighs quality loss. However this gap should be investigated to understand why convertedusers are generating less revenue.

**Conclusion:** Not a blocker for launch but requires investigation. Monitor plan type distribution amongconverted users post-launch.

---

## Guardrail Summary

| Guardrail Metric | Control | Treatment | Risk | Decision |
|-----------------|---------|-----------|------|------|----------|
| Support Ticket Rate | 14.78% | 24.79% |  HIGH | Blocker |
| Refund Rate | 0.00% | 0.42% |   LOW | Monitor |
| Revenue Per Converted User | $894.60 | $704.72 | ⚠️MEDIUM | Investigate |

---

## Overall Guardrail Conclusion

The primary conversion metric strongly supports launching the campaign. However one guardrailmetric creates a significant risk:

**Support ticket rate is breached at a statistically significant level (p = 0.0000027).**

This means the campaign is causing measurable harmto user experience even while improving conversion.Launching to all users in this state would scaleboth the benefit (more conversions) and the harm(more confused users needing support).

**Recommendation:** Do not launch until supportticket issue is resolved. Refund rate and revenuequality should be monitored closely after launch.






### Task 9: Write Recommendation Memo



## 1. Executive Summary

A new onboarding and activation campaign was tested on 1,400 users — Control (n=690) and Treatment(n=710). The campaign produced a statisticallysignificant +121% improvement in paid conversion rate (3.19% → 7.04%, p=0.00055) and a +74% increase in average revenue per user ($28.52 →$49.63, p=0.023).

However, the support ticket guardrail was critically  breached — increasing +67.7% (14.78% → 24.79%, p=0.0000027), indicating the new experience is causing significant user confusion.

**Recommendation: Conditional Launch **
Fix the support ticket issue first. Once resolved,the data strongly supports a full rollout.

---

## 2. North Star Metric

**Selected Metric: Paid Conversion Rate**
Definition: Users converted to paid / Total users

| Group | Conversions | Total Users | Rate |
|-------|-------------|-------------|------|
| Control | 22 | 690 | 3.19% |
| Treatment | 50 | 710 | 7.04% |

**Statistical Validation:**
- Z-Score: 3.264
- P-Value (one-tailed): 0.00055
- Alpha: 0.05
- Result: Statistically significant 

Paid conversion rate is the North Star because it is the only metric that directly confirms real business value — a user paying for the product. All funnel metrics(visits, trials, onboarding) are inputs that lead to conversion but do not confirm it.

---

## 3. KPI Tree Explanation

**North Star: Paid Conversion Rate (3.19% → 7.04%)**

### Driver 1: Funnel Progression
| Sub-Driver | Control | Treatment | P-Value |
|------------|---------|-----------|---------|
| Landing Page Visit Rate | 63.62% | 72.39% | 0.000432  |
| Trial Start Rate | 25.07% | 29.01% | 0.048514  |
| Onboarding Completion | 15.65% | 21.13% | 0.004129 |

All funnel steps improved significantly, showing the campaign successfully guides users through each stage toward conversion.

### Driver 2: User Engagement
| Sub-Driver | Control | Treatment  | P-Value |
|------------|---------|-----------|---------|
| Engagement Score | 57.03 | 62.94 | <0.000001  |
| Avg Days to Convert | 8.9 days | 6.4 days | — |

Users convert faster and engage more deeply with the new campaign experience.

### Driver 3: Revenue Impact
| Sub-Driver | Control | Treatment  | P-Value |
|------------|---------|-----------|---------|
| Avg Revenue Per User | $28.52 | $49.63 | 0.023  |
| Avg Rev Per Converted | $894.60 | $704.72  |  |

### Guardrail Metrics
| Metric | Control | Treatment | Risk |
|--------|---------|-----------|------|
| Support Ticket Rate | 14.78% | 24.79% |  BREACHED |
| Refund Rate | 0.00% | 0.42%  |  Monitor |
| Rev Per Converted User | $894.60 | $704.72 |  Investigate |

---

## 4. Experiment Result Summary

| Metric | Control | Treatment | Significant |
|--------|---------|-----------|-------------|
| Landing Page Visit Rate | 63.62% | 72.39% |  p=0.000432 |
| Trial Start Rate | 25.07% | 29.01% | p=0.048514 |
| Onboarding Completion | 15.65% | 21.13%  |  p=0.004129 |
| Paid Conversion Rate | 3.19% | 7.04%  | p=0.000549 |
| Avg Revenue Per User | $28.52 | $49.63  |  p=0.023063 |
| Avg Rev Per Converted | $894.60 | $704.72  |  |
| Engagement Score | 57.03 | 62.94 |  p<0.000001 |
| Avg Days to Convert | 8.9 days | 6.4 days |  |
| Support Ticket Rate | 14.78% | 24.79%  |  p=0.000003 |
| Refund Rate | 0.00% | 0.42% |  p=0.087 |

9 out of 10 metrics improved in Treatment.
1 critical guardrail was breached.

---

## 5. Hypothesis Test Interpretation

### Test 1: Paid Conversion Rate (Primary)
- H0: p_treatment = p_control
- H1: p_treatment > p_control (one-tailed)
- Z-Score: 3.264 > Critical Value 1.6449
- P-Value: 0.00055 < Alpha 0.05
- **Decision: Reject H0 **

There is a 99.94% confidence that the campaign genuinely improves paid conversion rate. The probability this result occurred by chance isonly 0.055%.


---

## 6. Guardrail Analysis

### Guardrail 1: Support Ticket Rate 🚨 HIGH RISK
- Control: 102/690 = 14.78%
- Treatment: 176/710 = 24.79%
- Absolute increase: +10.01 percentage points
- Z-Score: 4.692 | P-Value: 0.0000027

This is the most critical finding in the experiment.At scale of 100,000 users this means approximately 10,000 additional support tickets that would nothave existed with the old experience. This directly increases operational costs and signals widespread user confusion with the new onboarding flow.

**Status: BLOCKER — Must resolve before launch**

### Guardrail 2: Refund Rate ⚠️ LOW RISK
- Control: 0/690 = 0.00%
- Treatment: 3/710 = 0.42%
- P-Value: 0.087 — not statistically significant

The absolute number is small (3 users) and does not cross the significance threshold. However the irectional increase from zero is worth monitoring post-launch. At 10,000 users this would mean ~42 additional refunds.

**Status: MONITOR after launch**

### Guardrail 3: Revenue Per Converted User ⚠️ MEDIUM RISK
- Control: $894.60 per converted user
- Treatment: $704.72 per converted user
- Decline: -21.2%

Despite more conversions, each converted user generates less revenue. This may indicate the campaign is attracting lower-value users or pushing users toward cheaper subscription plans.

However total revenue still increases significantly:
- Control 10k users: 319 converts × $894.60 = $285,277
- Treatment 10k users: 704 converts × $704.72 = $495,963
- Net gain: +$210,686 per 10,000 users

**Status: INVESTIGATE — does not block launch**

---

## 7. Segment-Level Insights

### By Region
| Region | Control | Treatment | 
|--------|---------|-----------|
| East | 2.55% | 6.47% | 
| North | 3.48% | 8.89% | 
| South | 3.26% | 7.65% | 
| West | 3.38% | 5.08% | 

East, North, South all show strong consistent lift. West is significantly weaker (+51% vs 135-155%). Recommend investigating West separately before full regional rollout.

### By Device Type
| Device | Control | Treatment | 
|--------|---------|-----------|
| Mobile | 2.58% | 7.41% | 
| Tablet | 1.82% | 7.14% |
| Desktop | 4.50% | 6.57% | 

Campaign is highly optimized for mobile and tablet. Desktop lift is significantly lower, suggesting the new onboarding UX may not translate as well to desktop screens.

### By Traffic Source
| Source | Control | Treatment | 
|--------|---------|-----------|
| Paid Search | 1.29% | 6.25% | 
| Referral | 2.47% | 11.00% | 
| Organic | 2.03% | 6.33% | 
| Email | 2.74% | 7.14% | 
| Social | 7.78% | 6.10% | 

Social is the only traffic source where Treatmentperforms worse than Control. This is a critical segment finding — the new campaign may conflict with social user expectations or the social creative is misaligned with the new experience.

### By Plan Type
| Plan | Control | Treatment |
|------|---------|-----------|
| Free | 3.10% | 9.30% | 
| Premium | 2.80% | 6.30% |
| Basic | 3.62% | 3.88% | 

Free and Premium users respond strongly. Basic plan users show almost zero response (+7%). The campaign messaging and onboarding flow appears to have minimal relevance for Basic plan users.

---

## 8. Final Recommendation

**CONDITIONAL LAUNCH ⚠️**

### What the Data Says

FOR launching:
- Paid conversion: +121% (p=0.00055) 
- Revenue per user: +74% (p=0.023) 
- Engagement score: +10.4% (p<0.000001) 
- All funnel metrics improved significantly 
- Faster conversion: 8.9 → 6.4 days 

AGAINST launching now:
- Support tickets: +67.7% (p=0.0000027) 
- Social traffic conversion: -22% 
- Basic plan lift: only +7% 
- West region lift: only +51% 

### Decision

The campaign delivers strong, data-backed improvement in conversion and revenue. However the support ticket guardrail breach is statistically significant and operationally serious.

Launching to all users now would scale the confusion alongside the conversions. The right decision is to fix the UX issues that are driving support tickets, then relaunch with confidence.

**Launch only after support ticket rate is confirmed to be within acceptable limits.**

---

## 9. Risks and Limitations

| Risk | Severity | Data Evidence |
|------|----------|---------------|
| Support ticket breach |  High | +67.7%, p=0.0000027 |
| Social traffic decline |  High | -22% conversion |
| Basic plan non-response |  Medium | Only +7% lift |
| West region weak lift |  Medium | +51% vs 135-155% |
| Revenue per converted -21% |  Medium | $894 → $704 |
| Refund rate increase | Low | 0% → 0.42%, p=0.087 |

**Experiment Limitations:**
- Experiment duration unknown — long term
  retention and churn cannot be assessed
- No demographic data for deeper user analysis
- Social creative content not evaluated
- 3 revenue outliers winsorized at $1,496
- Minor group imbalance (690 vs 710 users)

---

## 10. Next Steps

- Investigate root cause of support ticket increase 
- Fix UX confusion in new onboarding flow 
- Review and fix social traffic campaign creative 
- Redesign campaign messaging for Basic plan  
- Investigate West region performance gaps 
- Re-run experiment after all fixes 
- Evaluate all guardrail metrics again 
- Full rollout if guardrails pass 

**Success Criteria for Full Launch Approval:**
- Support ticket rate increase < 5pp vs Control
- Refund rate stays below 1%
- Paid conversion rate maintains above 6%
- Social traffic conversion lift turns positive
- Basic plan lift improves above 20%
-