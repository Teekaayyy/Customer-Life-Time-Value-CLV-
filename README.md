# Project 11: Customer Lifetime Value (CLV) Analysis
### What Is Each Customer Actually Worth to the Business?

---

## Business Brief

Most businesses know how much a customer spent last month. Very few know how much a customer will spend over their entire relationship with the business. CLV is one of the most important metrics in commercial analytics and one of the most commonly miscalculated.

> If I know what a customer is worth over their lifetime, how much should I spend to acquire them, and how much should I spend to keep them?

---

## Dataset

| Property | Detail |
|----------|--------|
| **Name** | E-Commerce Data |
| **Direct Link** | https://www.kaggle.com/datasets/carrie1/ecommerce-data |
| **Records** | 541,909 transactions, 4,300+ UK customers |
| **Period** | December 2010 to December 2011 |

---

## What Makes This Different

- Calculates CLV three ways: historical, formula-based, and predictive
- Builds a four-tier CLV system (Platinum, Gold, Silver, Bronze)
- Introduces the Lorenz curve and Gini coefficient for CLV concentration
- CLV-to-CAC ratio analysis showing which tiers are profitable to acquire
- Predictive model for estimating CLV from early behavioural signals

---

## Project Structure

```
clv-analysis/
├── project_11_clv_analysis.ipynb
└── README.md
```

---

## Kaggle Setup

1. Search **"ecommerce-data"** by *carrie1* on Kaggle and attach it
2. Upload `project_11_clv_analysis.ipynb`
3. Run all cells

---

## Notebook Walkthrough

### Section 1: Setup
Libraries, colour system. Tier colours: Platinum (indigo), Gold (amber), Silver (slate), Bronze (brown).

### Section 2: Load and Prepare
Same cleaning pipeline as Projects 02 and 04. Calculates Revenue per line item.

### Section 3: CLV Calculation with SQL
SQL query calculating per customer: tenure days, recency days, frequency, historical CLV, avg order value, annual revenue rate, unique products. Explains all three CLV approaches (historical, formula, predictive) with the formula documented.

### Section 4: CLV Tier Classification
Four tiers based on percentile thresholds (90th, 70th, 30th). Tier summary with customer count, total CLV, avg CLV, avg frequency, avg recency, CLV share, and customer share.

### Section 5: CLV Distribution and Tier Charts
Three visualisations:
- CLV distribution histogram with mean and median lines
- Customer share vs CLV share grouped bar chart (shows the imbalance)
- Average CLV per tier bar chart

Plus interactive scatter: recency vs CLV coloured by tier, sized by frequency.

Plus Lorenz curve showing CLV concentration with Gini coefficient. Annotates what percentage of total CLV the top 10% of customers generate.

### Section 6: Predictive CLV Model
Linear regression on log-transformed CLV using recency, frequency, avg order value, tenure, unique products, and annual revenue rate. Reports R-squared and MAE. Actual vs predicted scatter chart.

### Section 7: CLV-to-CAC Ratio
Simulated CAC per tier with reasoning documented. Calculates CLV-to-CAC ratio and payback period. Two bar charts: ratio by tier with 3:1 healthy benchmark line, and payback months with 12-month threshold line.

### Section 8: Executive Summary Dashboard
Dark-theme KPI cards: total CLV, avg CLV, median CLV, platinum customer count, Gini coefficient, best CLV-to-CAC tier.

### Section 9: Findings and Recommendations
Five findings with evidence. Four recommendations with specific actions.

---

## Key Findings

| Finding | Evidence |
|---------|----------|
| CLV is highly concentrated in a small percentage of customers | Lorenz curve |
| Mean and median CLV differ significantly, indicating a long right tail | Distribution chart |
| Not all tiers have healthy CLV-to-CAC ratios | CAC analysis |
| Recency and frequency are strong CLV predictors | Model feature importance |
| Platinum payback period is significantly shorter than other tiers | Payback chart |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data manipulation, CLV calculations |
| SQLite3 | Customer-level aggregation queries |
| Scikit-learn | Linear regression, StandardScaler |
| Plotly | Interactive scatter, dashboard |
| Matplotlib | Distribution, Lorenz curve, tier charts |

---

*Built by Jessica Dan-Odhomo - [LinkedIn](https://www.linkedin.com/in/jessica-dan-odhomo) - [GitHub](https://github.com/Teekaayyy)*
