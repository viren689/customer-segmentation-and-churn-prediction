# Customer Segment Profiles

## Overview

The customer segmentation analysis divided 500 customers into five customer segments using K-Means clustering with K = 5.

The segments were analyzed using customer tenure, monthly charges, total charges, senior-citizen status, contract type, payment method, paperless billing, and churn behavior.

---

## 1. Long-Term Customers

**Customers:** 97  
**Percentage:** 19.4%

### Profile

- Average tenure: 34.88 months
- Average monthly charges: 110.90
- Average total charges: 4597.04
- Senior citizens: 54.64%
- Churn rate: 7.22%
- Contract type: 2-year
- Payment methods: Bank Transfer and Credit Card
- Paperless billing: 56%

### Business Interpretation

This segment consists primarily of customers with long-term contracts and relatively high cumulative spending. Their churn rate is 7.22%, indicating a comparatively stable customer group.

### Business Recommendation

- Maintain loyalty and retention programs.
- Offer renewal benefits for long-term customers.
- Provide personalized service and account reviews.
- Encourage continued adoption of convenient digital billing options.

---

## 2. High-Charge Electronic Check Customers

**Customers:** 101  
**Percentage:** 20.2%

### Profile

- Average tenure: 36.28 months
- Average monthly charges: 121.08
- Average total charges: 4165.61
- Senior citizens: 45.54%
- Churn rate: 13.86%
- Contract type: Month-to-month and 2-year
- Payment method: Electronic Check
- Paperless billing: 41%

### Business Interpretation

This segment has the highest average monthly charges among the five segments and uses electronic check as its payment method. Its churn rate is 13.86%.

### Business Recommendation

- Provide personalized retention offers.
- Monitor high-value customers for early churn signals.
- Promote longer-term contract options where appropriate.
- Offer convenient alternative payment methods.

---

## 3. Low-Churn One-Year Customers

**Customers:** 124  
**Percentage:** 24.8%

### Profile

- Average tenure: 38.39 months
- Average monthly charges: 115.25
- Average total charges: 3976.46
- Senior citizens: 45.16%
- Churn rate: 3.23%
- Contract type: 1-year
- Payment methods: Bank Transfer and Credit Card
- Paperless billing: 51%

### Business Interpretation

This is the largest segment and has the lowest observed churn rate in the dataset. Customers have relatively long tenure and one-year contracts.

### Business Recommendation

- Maintain the existing customer experience.
- Encourage contract renewal.
- Develop loyalty and referral programs.
- Use this segment as a reference for identifying stable customer characteristics.

---

## 4. Month-to-Month At-Risk Customers

**Customers:** 116  
**Percentage:** 23.2%

### Profile

- Average tenure: 36.35 months
- Average monthly charges: 108.85
- Average total charges: 4260.77
- Senior citizens: 55.17%
- Churn rate: 20.69%
- Contract type: Month-to-month
- Payment methods: Bank Transfer and Credit Card
- Paperless billing: 44%

### Business Interpretation

This segment has the highest observed churn rate at 20.69%. Customers are exclusively on month-to-month contracts.

### Business Recommendation

- Develop targeted retention campaigns.
- Communicate the benefits of longer-term contracts.
- Provide personalized offers based on customer value.
- Monitor this segment using the prediction models developed in this project.

---

## 5. One-Year Electronic Check Customers

**Customers:** 62  
**Percentage:** 12.4%

### Profile

- Average tenure: 36.16 months
- Average monthly charges: 111.52
- Average total charges: 4273.73
- Senior citizens: 48.39%
- Churn rate: 6.45%
- Contract type: 1-year
- Payment method: Electronic Check
- Paperless billing: 55%

### Business Interpretation

This is the smallest customer segment. Customers generally have one-year contracts and use electronic checks. The observed churn rate is 6.45%.

### Business Recommendation

- Encourage convenient payment alternatives.
- Maintain one-year contract renewal programs.
- Monitor customer engagement and satisfaction.
- Use targeted communication before contract renewal.

---

# Segment Summary

| Segment | Customers | Share | Churn Rate |
|---|---:|---:|---:|
| Long-Term Customers | 97 | 19.4% | 7.22% |
| High-Charge Electronic Check Customers | 101 | 20.2% | 13.86% |
| Low-Churn One-Year Customers | 124 | 24.8% | 3.23% |
| Month-to-Month At-Risk Customers | 116 | 23.2% | 20.69% |
| One-Year Electronic Check Customers | 62 | 12.4% | 6.45% |

---

## Important Modeling Note

The segment-specific prediction models were trained separately for each customer segment.

Some segments contain relatively few churned customers:

- Long-Term Customers: 7 churned customers
- One-Year Electronic Check Customers: 4 churned customers
- Low-Churn One-Year Customers: 4 churned customers

Therefore, precision, recall, and F1-score for these segments should be interpreted cautiously because the positive class is small.

Feature importance from the Random Forest models indicates that **Tenure** was the most influential feature across the segment models, followed by variables such as **MonthlyCharges** and **TotalCharges**. Feature importance represents model behavior and should not be interpreted as causal evidence.

---

## Conclusion

The customer segmentation analysis demonstrates how unsupervised learning can identify distinct customer groups and how segment-specific Random Forest models can be used to analyze churn risk.

The combination of clustering, classification, hyperparameter tuning, evaluation metrics, and feature importance provides a data-driven framework for developing segment-specific customer strategies.