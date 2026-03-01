# 🔍 Customer Churn Analysis
### Python · Pandas · NumPy · Matplotlib · EDA

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> > Exploratory data analysis on 1,000 customer records to identify the key behavioural drivers of churn and provide actionable retention insights.

---

## 📌 Problem Statement

Monthly recurring revenue was declining due to customer churn. The business knew churn was happening but had no data on **who** was churning or **why**.

**Goal:** Identify the top churn drivers using behavioural data, and surface clear, actionable segments for the CRM team to target.

---

## 📊 Dataset

| Feature | Description |
|---|---|
| `age_segment` | Customer age bracket (18–25, 26–35, etc.) |
| `plan_type` | Starter / SMB / Enterprise |
| `tenure_months` | Months since account creation |
| `monthly_charges` | Monthly billing amount (€) |
| `support_calls_6m` | Support tickets raised in last 6 months |
| `monthly_logins` | Average logins per month |
| `satisfaction_score` | Last NPS survey score (1–5) |
| `churned` | Target variable — 1 = churned, 0 = retained |


---

## 🔧 Analysis Pipeline

```
Raw CSV (1,000 rows)
    │
    ▼
Data Cleaning & Type Casting
    │
    ▼
Feature Engineering
  ├── revenue_per_login
  ├── support_intensity (calls / tenure)
  ├── is_low_engagement (logins < 3)
  └── is_high_support (calls > 8)
    │
    ▼
Exploratory Data Analysis
  ├── Churn by segment / plan / region
  ├── Tenure & charges distribution
  └── Feature correlation heatmap
    │
    ▼
Findings & Recommendations Report
```

---

## 📈 Key Findings

### Overall churn rate: ~29%

| Segment | Churn Rate | vs. Average |
|---|---|---|
| Starter plan, 18–25, <3 logins/month | ~48% | +19pp |
| >8 support calls in 6 months | ~52% | +23pp |
| Enterprise plan, 36–45 | ~9% | −20pp |
| 15+ logins/month | ~11% | −18pp |

**Top 3 churn predictors:**
1. High support call volume (>8 in 6 months)
2. Low login frequency (<3/month)
3. Starter plan + age 18–25 combination

---

## ✅ Business Impact

Findings were handed to the CRM team who ran a targeted retention campaign on the Starter + 18–25 segment with low login frequency.

**Result: 12% reduction in churn rate over the following quarter.**

---

## 📁 Repository Structure

```
churn-analysis/
├── notebooks/
│   └── churn_analysis.ipynb    # Full analysis — run top to bottom
├── data/
│   └── customer_churn.csv      # Sample dataset (1,000 rows)
├── outputs/
│   ├── churn_by_segment.png
│   ├── tenure_charges.png
│   └── correlation_matrix.png
└── README.md
```

---

## 🚀 How to Run

```bash
git clone https://github.com/charanpasupuleti/churn-analysis
cd churn-analysis
pip install pandas numpy matplotlib jupyter
jupyter notebook notebooks/churn_analysis.ipynb
```

All charts are automatically saved to `/outputs/` when you run the notebook.

---

## 🔑 Key Technical Decisions

- **Custom feature engineering** over raw features — `support_intensity` (calls ÷ tenure) was a stronger predictor than raw call count alone
- **Matplotlib over Seaborn** — gave full control over dark-theme styling for presentation-ready charts
- **Segment profiling before modelling** — EDA findings alone were sufficient for actionable recommendations without needing a full ML model

---

## 👤 Author

**Charan Pasupuleti** — Data Analyst  
📧 nagapasupuleti98@outlook.com · 🌍 [LinkedIn](#)
