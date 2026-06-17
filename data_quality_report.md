# Data Quality Report – D2C Customer Churn Dataset

## Overview
This report summarizes data quality checks performed on the D2C churn dataset, covering customer profiles, transaction history, support interactions, web/app activity, campaign exposure, and churn labels.

---

## 1. Missing Values

### Observations
- Missing values observed in:
  - `rating` field in orders dataset
  - Support and campaign data (no records for some customers)
  - Web activity fields (inactive users show 0 or nulls)

### Impact
- Affects:
  - customer satisfaction (rating)
  - behavioral insights
  - engagement analysis

### Fix Applied
- Numerical values → filled with `0`
- Categorical values → filled with `"unknown"`

---

## 2. Duplicate Records

### Observations
- No duplicate `customer_id` values
- No duplicate `order_id` or `ticket_id` detected

### Impact
- No redundancy affecting aggregation

### Action
- No cleaning required

---

## 3. Invalid / Unexpected Values

### Observations
- Discount values as high as ~60%
- Ratings missing for some transactions
- Sentiment values range between -1 to 1
- Zero activity in web data (valid for inactive users)

### Impact
- Extreme values may skew averages
- Missing ratings affect satisfaction metrics

### Recommendation
- Handle carefully in modeling stage

---

## 4. Outliers

### Observations
- High spend customers identified
- Some users have very high ticket counts
- Extreme values in:
  - delivery_days
  - resolution_hours

### Impact
- May distort averages and model behavior

### Recommendation
- Use robust statistics or transformations

---

## 5. Join Issues

### Observations
- Base key: `customer_id`
- Some customers:
  - have no orders
  - have no tickets
  - have no campaigns

### Impact
- Missing values after merging

### Fix Applied
- Used LEFT JOIN
- Filled missing values

---

## 6. Date Consistency (CRITICAL)

### Observation
- Orders present after snapshot date (2025-09-30)

### Risk
- Leads to data leakage

### Fix Applied
- Applied filter:
  order_date <= snapshot_date

- Same applied to support ticket data

---

## 7. Data Leakage Risks

### Identified Risks
- Future orders
- Future support tickets
- Future campaign exposure

### Action Taken
- Strict filtering using snapshot_date
- Only historical data retained

---

## 8. Dataset-Specific Observations

### Orders
- Return flag present
- Missing ratings for some entries

### Support
- Multiple tickets per customer
- Reopened tickets indicate unresolved issues

### Web/App
- Low engagement indicates churn risk
- Division features handled for infinity

### Campaign
- Many users not targeted
- Cost ranges from 0 to 40

---

## 9. Risk Summary

| Issue               | Severity | Impact                   |
|--------------------|----------|--------------------------|
| Missing values     | Medium   | Feature bias             |
| Outliers           | Medium   | Skewed metrics           |
| Join gaps          | Low      | Sparse data              |
| Data leakage       | HIGH     | Invalid analysis ❗       |

---

## 10. Final Recommendations

- Apply strict time filtering 
- Handle missing values post-merge 
- Monitor outliers in modeling
- Validate features before ML
- Ensure no future data leakage

---

## Conclusion

The dataset is clean and usable after preprocessing.  
The most critical issue was **time-based data leakage**, which has been resolved.

The dataset is now ready for:
- Exploratory Data Analysis ✅
- Feature Engineering ✅
- Churn Modeling ✅
