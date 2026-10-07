# Customer Segmentation & Prediction

## 📌 Project Overview

This project focuses on customer segmentation and churn prediction using machine learning techniques.

The project uses clustering algorithms to identify meaningful customer segments and then builds separate Random Forest classification models for each segment to analyze and predict customer churn.

The analysis combines:

- Customer segmentation
- Clustering analysis
- Churn prediction
- Hyperparameter tuning
- Model evaluation
- Feature importance
- Business recommendations

---

## 🎯 Project Objectives

The main objectives of this project are:

1. Analyze customer characteristics and behavior.
2. Prepare numerical and categorical data for machine learning.
3. Segment customers using multiple clustering algorithms.
4. Compare K-Means, Hierarchical Clustering, and DBSCAN.
5. Create at least five meaningful customer segments.
6. Build separate prediction models for each customer segment.
7. Evaluate models using multiple classification metrics.
8. Perform hyperparameter tuning using GridSearchCV.
9. Identify important features influencing model predictions.
10. Generate actionable business recommendations.

---

## 📂 Dataset

The dataset contains **500 customer records** with 9 original features.

### Original Features

| Feature | Description |
|---|---|
| CustomerID | Unique customer identifier |
| Tenure | Number of months the customer has stayed |
| MonthlyCharges | Customer's monthly charges |
| TotalCharges | Total amount charged to the customer |
| SeniorCitizen | Indicates whether the customer is a senior citizen |
| Contract | Customer contract type |
| PaymentMethod | Customer payment method |
| PaperlessBilling | Whether paperless billing is enabled |
| Churn | Indicates whether the customer churned |

### Dataset Shape

Rows: 500
Columns: 9
Missing Values: None
🛠️ Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
SciPy
ReportLab
Jupyter Notebook

### 📁 Project Structure
 Customer-Segmentation-Prediction/
│
├── customer_segmentation.ipynb

├── customer_segmentation.csv

├── segmentation_data.csv

├── segment_profiles.md

├── model_evaluation_results.csv

├── business_recommendations.pdf

├── README.md
│
├── models/
│
└── visualizations/

    ├── elbow_method.png
    
    ├── customer_segment_distribution.png
    
    ├── kmeans_clusters_pca.png
    
    ├── hierarchical_clusters_pca.png
    
    ├── dbscan_clusters_pca.png
    
    ├── churn_rate_by_segment.png
    
    ├── baseline_confusion_matrices.png
    
    └── feature_importance_by_segment.png

### 🔄 Project Workflow
Dataset
   ↓
Data Inspection
   ↓
Data Preprocessing
   ↓
Feature Encoding & Scaling
   ↓
K-Means Clustering
   ↓
Hierarchical Clustering
   ↓
DBSCAN
   ↓
Cluster Comparison
   ↓
Customer Segment Analysis
   ↓
Segment-Specific Prediction Models
   ↓
Model Evaluation
   ↓
Hyperparameter Tuning
   ↓
Feature Importance
   ↓
Business Recommendations

### 1. 🔍 Data Exploration & Preprocessing

The dataset was first inspected for:

Dataset dimensions
Data types
Missing values
Duplicate records
Numerical features
Categorical features

CustomerID and Churn were excluded from the clustering process.

Categorical variables were converted into numerical form using one-hot encoding.

Numerical and encoded features were standardized using StandardScaler.

2. 📊 Customer Segmentation
K-Means Clustering

The Elbow Method was used to determine an appropriate number of clusters.

The analysis evaluated cluster counts from 2 to 10.

Based on the elbow analysis and business interpretability, 5 clusters were selected for the primary customer segmentation.

K-Means Result
Cluster	Customers
0	97
1	101
2	116
3	62
4	124

### 3. 🔬 Additional Clustering Algorithms

Two additional clustering approaches were evaluated to satisfy the clustering comparison requirement.

Hierarchical Clustering

Agglomerative Hierarchical Clustering was evaluated using:

5 clusters
Ward linkage

Silhouette Score:

0.1309
DBSCAN

DBSCAN was also evaluated as a density-based clustering method.

Selected configuration:

eps = 2.0
min_samples = 5

Result:

Clusters: 35
Noise observations: 32
Noise percentage: 6.4%

DBSCAN produced a higher silhouette score but generated many small clusters. Therefore, K-Means was retained as the primary segmentation method because its five-segment structure was more suitable for business interpretation.

### 4. 👥 Customer Segments

The five K-Means clusters were interpreted and given business-oriented names.

Segment	Customers	Percentage	Churn Rate
Low-Churn One-Year Customers	124	24.8%	3.23%
Month-to-Month At-Risk Customers	116	23.2%	20.69%
High-Charge Electronic Check Customers	101	20.2%	13.86%
Long-Term Customers	97	19.4%	7.22%
One-Year Electronic Check Customers	62	12.4%	6.45%

### 5. 📈 Segment Analysis

Long-Term Customers

Customers: 97

Average Tenure: 34.88 months

Average Monthly Charges: ₹110.90

Churn Rate: 7.22%

Contract profile: Two-year

Payment methods: Bank Transfer and Credit Card

Business Recommendations

Maintain loyalty programs.

Encourage contract renewals.

Provide personalized account support.

Continue monitoring customer satisfaction.

High-Charge Electronic Check Customers

Customers: 101

Average Tenure: 36.28 months

Average Monthly Charges: ₹121.08

Churn Rate: 13.86%

Electronic Check usage: 100%

Business Recommendations

Monitor high-value customers.

Provide targeted retention offers.

Promote convenient payment alternatives.

Encourage longer-term contracts where appropriate.

Low-Churn One-Year Customers

Customers: 124

Average Tenure: 38.39 months

Average Monthly Charges: ₹115.25

Churn Rate: 3.23%

Contract profile: One-year

Business Recommendations

Maintain the existing customer experience.

Encourage contract renewals.

Develop loyalty initiatives.

Explore referral opportunities.

Month-to-Month At-Risk Customers

Customers: 116

Average Tenure: 36.35 months

Average Monthly Charges: ₹108.85

Churn Rate: 20.69%

Contract profile: Month-to-month

Business Recommendations

Use targeted retention campaigns.

Communicate the benefits of longer-term contracts.

Provide personalized offers.

Monitor changes in customer behavior.

One-Year Electronic Check Customers

Customers: 62

Average Tenure: 36.16 months

Average Monthly Charges: ₹111.52

Churn Rate: 6.45%

Contract profile: One-year

Payment method: Electronic Check

Business Recommendations

Promote convenient payment alternatives.

Maintain proactive renewal communication.

Monitor customer engagement.

Provide personalized account support.


### 6. 🤖 Segment-Specific Prediction Models

Separate Random Forest classification models were developed for each of the five customer segments.

Model Configuration
Algorithm: Random Forest Classifier
n_estimators: 100
random_state: 42
class_weight: balanced
Train/Test Split: 70/30
Stratification: Applied

The models were evaluated using:

Accuracy
Precision
Recall
F1 Score
ROC-AUC
Confusion Matrix

### 7. 📊 Model Evaluation

The tuned models produced the following results:

Segment	Accuracy	Precision	Recall	F1 Score	ROC-AUC
Long-Term Customers	0.9000	0.0000	0.0000	0.0000	0.9643
High-Charge Electronic Check	0.9677	0.8000	1.0000	0.8889	0.9722
Month-to-Month At-Risk	1.0000	1.0000	1.0000	1.0000	1.0000
One-Year Electronic Check	1.0000	1.0000	1.0000	1.0000	1.0000
Low-Churn One-Year	0.9737	0.0000	0.0000	0.0000	1.0000
Important Evaluation Note

Some segments contain only a small number of churned customers.

Because of this class imbalance, accuracy alone does not fully describe model performance. Precision, recall, F1-score, ROC-AUC, and confusion matrices were therefore considered together.

### 8. ⚙️ Hyperparameter Tuning

GridSearchCV was used to tune the Random Forest models.

The following parameters were evaluated:

param_grid = {
    "n_estimators": [100, 200],
    "max_depth": [None, 5, 10],
    "min_samples_split": [2, 5],
    "min_samples_leaf": [1, 2],
    "max_features": ["sqrt", "log2"]
}
Cross-Validation
Method: Stratified K-Fold
Folds: 3
Scoring Metric: F1 Score

This tuning process was used to identify suitable model configurations while considering the imbalance between churn and non-churn customers.

### 9. 🔎 Feature Importance

Feature importance was extracted from the tuned Random Forest models.

Across the customer segments, the most frequently important features included:

Tenure
MonthlyCharges
TotalCharges
SeniorCitizen
PaperlessBilling
Contract-related features
Payment method features

Tenure was the most important feature across the segment-specific Random Forest models in this analysis.

Feature importance describes how the trained model used the variables for prediction. It does not establish a causal relationship between a feature and customer churn.

### 10. 📉 PCA Visualization

Principal Component Analysis was used to visualize the customer clusters in two dimensions.

The first two principal components explained approximately:

PC1: 17.73%
PC2: 16.37%

Total: 34.10%

The PCA visualization provides a two-dimensional representation of the clustering structure, but it does not represent all variance in the original feature space.

### 11. 🧪 Testing & Validation

The project was validated using:

Dataset shape checks
Missing-value checks
Duplicate checks
Cluster distribution checks
Silhouette score evaluation
Classification metrics
Confusion matrices
Hyperparameter tuning
Feature importance analysis

The final project contains visual outputs for:

Elbow Method
Customer Segment Distribution
K-Means PCA Clusters
Hierarchical Clusters
DBSCAN Clusters
Churn Rate by Segment
Confusion Matrices
Feature Importance

### 12. 💡 Business Insights

The segmentation analysis demonstrates that customer groups can have different churn patterns.

The Month-to-Month At-Risk Customers segment had a churn rate of 20.69%, while the Low-Churn One-Year Customers segment had a churn rate of 3.23%.

The analysis therefore supports segment-specific customer management rather than applying the same strategy to every customer.

Potential business actions include:

Targeted retention campaigns
Contract renewal programs
Payment-method optimization
Loyalty initiatives
Personalized customer communication
Monitoring high-value customers

These recommendations should be validated against additional operational and customer-level information before being implemented.

### 13. ⚠️ Limitations

Some segments contain relatively few churned customers.
Small positive-class counts can make precision, recall, and F1-score unstable.
The dataset contains only 500 customer records.
PCA's first two components represent 34.10% of total variance.
Feature importance should not be interpreted as causation.
Model performance on this dataset may not generalize to other customer populations.
Business recommendations should be validated using additional business data.

### 14. 📄 Project Files

File	Purpose
customer_segmentation.ipynb	Complete analysis and machine learning workflow
customer_segmentation.csv	Original project dataset
segmentation_data.csv	Dataset prepared for submission
segment_profiles.md	Detailed customer segment profiles
model_evaluation_results.csv	Segment-specific model evaluation results
business_recommendations.pdf	Business recommendations report
visualizations/	Project charts and visual outputs
models/	Model-related files

## 15. 🚀 How to Run

Step 1: Clone the repository
git clone <repository-url>
cd Week11-Customer-Segmentation-Prediction
Step 2: Create a virtual environment
python -m venv .venv
Step 3: Activate the environment

Windows PowerShell:

.venv\Scripts\Activate.ps1
Step 4: Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter reportlab
Step 5: Start Jupyter Notebook
jupyter notebook
Step 6: Open
customer_segmentation.ipynb

Run the notebook cells from top to bottom.

## 📌 Conclusion

This project demonstrates an end-to-end machine learning workflow for customer segmentation and churn prediction.

Multiple clustering algorithms were compared, customer groups were analyzed using business-oriented profiles, and separate Random Forest models were developed for each segment.

The project combines unsupervised learning, supervised learning, model evaluation, hyperparameter tuning, feature interpretation, and business analysis into a single customer analytics pipeline.

## 👨‍💻 Author
Viren Wankhade
Aspiring Data Analyst | Data Science Enthusiast
- GitHub: https://github.com/viren689
- Portfolio: https://viren-portfolio-gamma.vercel.app/
- Email: viren19271@gmail.com
