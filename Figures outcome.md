# 📊 Customer Churn Analysis – Visualization Insights

This project focuses on identifying behavioral patterns and key drivers of customer churn using multiple data sources including transactions, support data, website activity, and campaign exposure.

---

## 📌 Objective
- Understand factors influencing customer churn  
- Identify high-risk customer segments  
- Provide insights for retention strategies  

---

## 📊 Exploratory Analysis & Insights

### 1. Distribution of Customer Churn in Next 60 Days
outputs/churn_dist.png

**Interpretation:**  
The plot shows the proportion of customers who churned versus retained. If imbalance exists, modeling techniques should address class imbalance.

---

### 2. Relationship Between Total Orders and Churn
outputs/orders.png

**Interpretation:**  
Customers with fewer orders tend to churn more, indicating lower engagement. High-frequency buyers are more loyal.

---

### 3. Relationship Between Total Spend and Churn
outputs/spend.png

**Interpretation:**  
Lower spending customers are more likely to churn, suggesting high-value customers are more retained.

---

### 4. Impact of Recency on Customer Churn
outputs/recency.png

**Interpretation:**  
Customers with higher recency (long time since last purchase) show a higher probability of churn.

---

### 5. Support Ticket Count vs Customer Churn
outputs/tickets.png

**Interpretation:**  
Higher ticket counts may correlate with churn due to dissatisfaction or unresolved issues.

---

### 6. Average Support Sentiment vs Churn
outputs/sentiment.png

**Interpretation:**  
Lower sentiment scores indicate poor customer experience and higher churn likelihood.

---

### 7. Website Engagement (Sessions) vs Churn
outputs/sessions.png

**Interpretation:**  
Fewer sessions indicate low engagement, which increases churn risk.

---

### 8. Days Since Last Visit vs Churn
outputs/visit.png

**Interpretation:**  
Customers who haven’t visited recently are significantly more likely to churn.

---

### 9. Churn Distribution Across Loyalty Tiers
outputs/loyalty.png

**Interpretation:**  
Higher loyalty tiers generally exhibit lower churn due to stronger engagement and benefits.

---

### 10. Effect of Campaign Exposure on Churn
outputs/campaign.png

**Interpretation:**  
Customers receiving campaigns may show reduced churn, indicating campaign effectiveness.

---

## 🔑 Key Insights

- Customer engagement is a major determinant of churn  
- Recency is one of the strongest predictors  
- Poor support experience increases churn risk  
- Loyalty programs improve retention  
- Campaigns can positively influence customer retention  

---

## 🚀 Next Steps

- Build predictive churn models (Logistic Regression / XGBoost)  
- Perform feature importance analysis  
- Design targeted retention campaigns  
- Optimize customer engagement strategies  

---

## 🛠️ Tech Stack

- **Python**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **Environment**: Jupyter Notebook  

---

## 📁 Repository Structure

```
.
├── outputs/
│   ├── churn_dist.png
│   ├── orders.png
│   ├── spend.png
│   ├── recency.png
│   ├── tickets.png
│   ├── sentiment.png
│   ├── sessions.png
│   ├── visit.png
│   ├── loyalty.png
│   ├── campaign.png
│   └── final_churn_report.docx
│
├── churn_analysis.ipynb
├── README.md
```

---

## ✅ Author

**Nainar M, Sundara Moorthi**  
Director, Pharmacokinetics & Pharmacodynamics  

---
