# Hypothesis Test Notes

### Task 6: Frame Hypotheses :

## Business Context
A subscription-based digital product company launcheda new onboarding and activation campaign to improveuser conversion and early engagement.

Leadership needs to decide whether to launch theTreatment campaign to all users based on experimentresults from 1,400 users (Control: 690, Treatment: 710).

---

# Paid Conversion Rate (Primary Metric)

### 1. Null Hypothesis (H0)
The new campaign has no effect on paid conversion rate.Any observed difference between Control and Treatmentis due to random chance.
H0: p_treatment = p_control

### 2. Alternate Hypothesis (H1)
The new campaign increases the paid conversion ratecompared to the existing onboarding experience.
H1: p_treatment > p_control

### 3. One-Tailed or Two-Tailed
One-tailed test.

The business question is directional — leadershiponly wants to launch if conversion rate increases.A decrease or no change both lead to the samedecision: do not launch.

### 4. Significance Level
Alpha (α) = 0.05

This is the standard threshold for business decisions,meaning we accept a 5% risk of incorrectly rejectingthe null hypothesis.

### 5. Metric Being Tested
Paid Conversion Rate = Users converted to paid / Total users

- Control: 22 / 690 = 3.19%
- Treatment: 50 / 710 = 7.04%


### 6. Reason for Choosing This Metric
Paid conversion rate is the North Star metric forthis experiment. It is the only metric that directlyconfirms the campaign achieved its core businessobjective — turning free or trial users into payingcustomers. All other metrics are intermediate stepsin the funnel and do not confirm actual revenue impact.

### 7. Interpretation Logic
- Pooled Proportion: 0.0514
- Standard Error: 0.01181
- Z-Score: 3.264
- P-Value (one-tailed): 0.00055
- Critical Value (α = 0.05): 1.6449

Since Z-Score (3.264) > Critical Value (1.6449)
and P-Value (0.00055) < Alpha (0.05):

**Decision: Reject H0**

The campaign significantly improves paid conversionrate. This result is statistically significant andsupports launching the campaign from a conversion standpoint.

---

