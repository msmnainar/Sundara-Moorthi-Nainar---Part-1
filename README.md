# D2C Customer Churn Intelligence – Part 1

## Objective
This project performs data audit, exploratory data analysis (EDA), and churn-risk hypothesis generation for a D2C personal-care brand.

The goal is to help business teams understand:
- Customer behavior patterns
- Key churn drivers
- Opportunities for targeted retention strategies

---

## Repository Structure

- notebooks/eda_audit.ipynb → Full EDA workflow
- reports/data_quality_report.md → Data issues
- reports/business_memo.md → Business insights
- outputs/ → Charts generated from analysis
- requirements.txt → Dependencies

---

## Dataset Overview

This project uses multiple datasets:

- customers → demographics
- orders → transactions
- support_tickets → customer issues
- web_events_snapshot → engagement data
- churn_labels → churn outcome
- intervention_history → marketing campaigns
- rfm_modeling_snapshot → aggregated features

---

## Key Insights

- Low engagement (sessions, activity) strongly drives churn
- High cart abandonment indicates purchase drop-off
- Negative support experience increases churn risk
- Campaigns are not consistently effective
- Recent inactivity is a critical churn signal

---

## How to Run

### 1. Install dependencies
```bash
pip install -r requirements.txt
