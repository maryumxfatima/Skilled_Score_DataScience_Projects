# A/B Test Analysis: Website Feature Impact on Conversion Rate

## Overview
A complete end-to-end A/B test analysis determining whether a new website 
feature significantly improved user conversion rates. The project covers 
data generation, cleaning, statistical testing, segmentation, and 
visualization.

---

## Business Question
> Did the new website feature meaningfully increase the conversion rate 
> compared to the existing version?

---

## Dataset
| Property | Value |
|---|---|
| Source | Synthetically generated (realistic mock data) |
| Total Users | 10,000 |
| Users per Group | 5,000 |
| Test Duration | 14 days (Nov 1–14, 2023) |
| Groups | Control (A) vs Treatment (B) |
| Key Metric | Conversion Rate |
| Secondary Metrics | Click-through Rate, Page Views |

---

## Methodology

### 1. Data Generation & Cleaning
- Generated 10,000 synthetic users split evenly into Control and Treatment
- Validated no duplicate users, no cross-group contamination, and no 
  missing values
- Confirmed data integrity (clicks never exceeded page views)

### 2. Key Metrics Calculated
- **Conversion Rate** = Conversions / Total Users (primary metric)
- **Click-through Rate** = Clicks / Page Views (secondary metric)
- **Absolute Lift** = Treatment Rate − Control Rate
- **Relative Lift** = Absolute Lift / Control Rate

### 3. Statistical Test
- **Test used:** One-tailed Z-test for proportions
- **Why Z-test:** Binary outcome (converted/not), large sample size 
  (n=5,000 per group), normal approximation valid
- **Significance level:** α = 0.05
- **Hypothesis:**
  - H₀: Treatment conversion rate ≤ Control conversion rate
  - H₁: Treatment conversion rate > Control conversion rate

### 4. Practical Significance
- Defined Minimum Detectable Effect (MDE) = 1.0% absolute lift
- Compared observed lift against MDE threshold
- Calculated Cohen's h effect size and achieved statistical power

### 5. Segmentation
- Segmented users by engagement level (Low / Medium / High page views)
- Analyzed daily conversion trends across the test period

---

## Key Results

| Metric | Control | Treatment |
|---|---|---|
| Users | 5,000 | 5,000 |
| Conversions | 479 | 590 |
| Conversion Rate | 9.58% | 11.80% |
| 95% CI | (8.76%, 10.40%) | (10.91%, 12.69%) |

| Statistical Metric | Value |
|---|---|
| Absolute Lift | +2.22% |
| Relative Lift | +23.17% |
| Z-statistic | 3.5924 |
| P-value | 0.0002 |
| Cohen's h | 0.0719 (Small) |
| Achieved Power | 97.45% |
| Statistically Significant | ✅ Yes |
| Practically Significant | ✅ Yes (exceeds 1% MDE) |

---

## Visualizations

| Plot | Description |
|---|---|
| Plot 1 | Conversion rate bar chart with 95% CI error bars |
| Plot 2 | Confidence interval overlap chart |
| Plot 3 | Daily conversion rate trend over test period |
| Plot 4 | Conversion rate by user engagement segment |
| Plot 5 | Full summary dashboard |

---

## Recommendations
1. **Ship the feature** — both statistical and practical significance 
   thresholds are met with high confidence
2. **Monitor post-launch** — track conversion rates for 2 weeks after 
   full rollout to detect any novelty effect decay
3. **Target high-engagement users first** — segmentation reveals stronger 
   lift in high page-view users
4. **Future experiments** — for detecting smaller lifts (<1%), increase 
   sample size to ~11,200 users per group

---

## Tech Stack
- **Python 3.x**
- `pandas` — data manipulation
- `numpy` — numerical computation
- `scipy` / `statsmodels` — statistical testing & power analysis
- `matplotlib` — visualizations

---

## How to Run
```bash
# Install dependencies
pip install pandas numpy statsmodels matplotlib

# Run the full analysis
python ab_test_analysis.py
```

---

## Skills Demonstrated
- Experimental design & hypothesis formulation
- Statistical hypothesis testing (Z-test for proportions)
- Confidence interval construction
- Effect size & power analysis
- Data segmentation & cohort analysis
- Data visualization & dashboard design
- Business-oriented interpretation of statistical results
