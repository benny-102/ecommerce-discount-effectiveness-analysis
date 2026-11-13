# 📊 E-commerce First-Purchase Discount Effectiveness Analysis

<p align="center">
  <strong>Evaluating customer retention, repeat-purchase revenue, and promotional economics</strong>
</p>

---

## 🚀 Executive Summary

This project examined whether offering customers a discount on their first purchase was associated with stronger customer retention and whether the resulting customer revenue justified the promotion.

Discounted customers recorded slightly higher repeat-purchase and Day-90 retention rates. However, neither difference was statistically significant. They also generated slightly lower average total revenue and repeat revenue per acquired customer than customers who did not receive a first-purchase discount.

The analysis therefore did not establish that blanket first-purchase discounts improved customer outcomes or delivered a measurable financial benefit. It recommended testing more targeted promotions through a controlled experiment before making wider investment decisions.

## 🎯 Project Overview

This project presents a business-focused analysis of first-purchase discount effectiveness using customer transaction data from a Turkish online retail platform.

The investigation combined **Python-based data preparation, customer-level analysis, retention measurement, cohort analysis, statistical testing, and customer economics** to develop an evidence-based business recommendation.

Rather than focusing on a dashboard, the project focused on answering a specific commercial question: **were first-purchase discounts associated with better customer retention and revenue outcomes?**

## ❓ Business Questions

1. Were customers who received a first-purchase discount more likely to make a subsequent purchase?
2. Did the observed retention relationship vary across customer segments and acquisition cohorts?
3. Did discounted customers generate more revenue from repeat purchases?
4. What did the available revenue and discount-cost data suggest about the economics of the promotion?

## 🗂️ Dataset

The supplied dataset describes transactions from a Turkish online retail platform. The accompanying source README describes 5,000 customers/transactions over a period spanning January 2023 to March 2024 and identifies monetary fields as **Turkish lira (TRY)**.

The actual CSV used in this project contained:

- **17,049** transaction rows
- **5,000** unique customers
- **17,049** unique order IDs
- Transaction dates from **1 January 2023 to 25 March 2024**

The dataset includes order and customer identifiers, transaction dates, demographics, product categories, unit prices, quantities, discounts, final transaction amounts, device and session attributes, returning-customer status, delivery time, and customer ratings.

> **Dataset provenance:** The file was found online as a practice dataset and was supplied with an accompanying README. No verified original download URL was available, so this repository does not attribute it to Kaggle.

## 🛠️ Tools & Technologies

- 🐍 **Python** — pandas, NumPy, SciPy, statsmodels
- 📊 **Data analysis** — customer-level aggregation, feature engineering, and exploratory analysis
- 📈 **Statistical analysis** — hypothesis testing, confidence intervals, and logistic regression
- 📓 **Jupyter Notebook** — analysis workflow and documentation
- 💾 **Git & GitHub** — version control and project hosting

## 🔍 Analytical Approach

The analysis covered the following stages:

1. **Inspecting and preparing the data** — reviewing data structure, parsing dates, and preparing customer- and transaction-level fields.
2. **Classifying first-purchase discount status** — separating customers according to whether their first purchase included a discount.
3. **Measuring customer retention** — comparing repeat-purchase rates and Day-90 retention between the two groups.
4. **Segmenting customers** — examining retention patterns by device, gender, age group, and product category.
5. **Analysing acquisition cohorts** — comparing monthly cohorts and examining Month 1 retention patterns.
6. **Testing statistical differences** — applying two-proportion z-tests, Fisher's exact tests, Mann–Whitney U tests, and Holm correction for multiple comparisons.
7. **Evaluating customer economics** — comparing customer revenue and discount expenditure.
8. **Estimating financial sensitivity** — applying hypothetical gross-margin assumptions to assess illustrative financial scenarios.

## 📌 Key Findings

### 1. Comparing Repeat-Purchase Rates

| Metric | Discounted customers | Non-discounted customers |
|---|---:|---:|
| Number of customers | 1,908 | 3,092 |
| Repeat-purchase rate | **83.23%** | **81.50%** |

The discounted group recorded a **1.73 percentage-point** higher repeat-purchase rate. However, the difference was not statistically significant (two-proportion z-test, *p* = **0.1211**).

### 2. Comparing Day-90 Retention

Among customers eligible for the Day-90 observation window:

| Metric | Discounted customers | Non-discounted customers |
|---|---:|---:|
| Day-90 retention rate | **74.48%** | **72.16%** |

The observed difference was approximately **2.32 percentage points** in favour of the discounted group, but it was not statistically significant (*p* ≈ **0.0806**). The eligible population was smaller than the full customer population because customers needed sufficient follow-up time to be included.

### 3. Comparing Customer Revenue

| Revenue metric | Discounted customers | Non-discounted customers |
|---|---:|---:|
| Average total revenue per acquired customer | ₺4,198.08 | ₺4,453.14 |
| Average repeat revenue per acquired customer | ₺3,050.93 | ₺3,123.55 |

- The total-revenue Mann–Whitney U comparison did not show a statistically significant difference (*p* = **0.2005**).
- Among repeat purchasers only, the repeat-revenue comparison was also not statistically significant (*p* = **0.2538**).
- Total first-purchase discount expenditure for the discounted group was approximately **₺346,822.75**.

### 4. Evaluating Financial Sensitivity

A hypothetical gross-margin sensitivity analysis applied margins from 20% to 60% to discounted-customer repeat revenue, then subtracted the initial discount expenditure of **₺346,822.75**.

| Assumed gross margin | Estimated gross profit after discount expenditure |
|---:|---:|
| 20% | ₺817,412.51 |
| 40% | ₺1,981,647.76 |
| 60% | ₺3,145,883.02 |

These figures represent illustrative scenario estimates, not measured incremental profit or return on investment. The calculation does not establish how much repeat revenue was caused by the discounts; actual product costs, operating costs, and the counterfactual revenue that would have occurred without discounts were unavailable.

## 💡 Business Recommendation

The analysis did not provide sufficient evidence to justify blanket first-purchase discounts as a proven retention strategy. Although discounted customers recorded slightly higher observed repeat-purchase and Day-90 retention rates, neither difference was statistically significant. They also did not demonstrate stronger average customer or repeat revenue.

The recommended next step is to **test a more targeted promotional strategy through a controlled experiment**. A properly designed A/B test would help establish whether discounts caused improvements in retention, revenue, and contribution profit, rather than merely being associated with customer behaviour.

## ⚠️ Limitations

- The dataset was observational, not the result of a randomized experiment; therefore, the analysis could not establish that discounts caused repeat purchases.
- Product-level cost of goods sold and actual contribution margins were unavailable, so actual gross profit and discount ROI could not be calculated.
- Marketing and acquisition expenses were unavailable, preventing calculation of a complete customer acquisition cost.
- The observation window limited the assessment of long-term customer lifetime value.
- The financial sensitivity analysis used hypothetical gross margins and should not be interpreted as actual profitability.
- The dataset's original public download location could not be verified.

## 📁 Repository Structure

```text
.
├── README.md
├── data/
│   └── ecommerce_customer_behavior_dataset_v2.csv
├── notebooks/
│   └── discount_effectiveness_analysis.ipynb
├── reports/
│   └── business_recommendation.md
├── requirements.txt
└── .gitignore
```

## ▶️ Running the Notebook

1. Clone or download this repository.
2. Create and activate a Python environment.
3. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Open `notebooks/discount_effectiveness_analysis.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.
5. Run all cells from top to bottom.

The notebook reads the CSV file from the repository's `data/` directory using a relative path.

---

*This project demonstrates an end-to-end analytical workflow, from defining a business question and preparing customer-level data to evaluating statistical evidence, interpreting financial implications, and recommending a business action.*
