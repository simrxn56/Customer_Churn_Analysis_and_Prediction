# Customer Churn Analysis & Prediction

This project analyzes customer churn behavior using interactive Tableau dashboards and a machine learning model built with CatBoost.  
The goal is to identify key drivers of churn, segment customer behavior, and demonstrate how predictive modeling can support retention strategies.

The project combines business intelligence visualization with supervised machine learning to move from descriptive insights to actionable prediction.

---

## 📊 Dataset

The dataset contains customer-level information including:

- Demographics (gender, senior citizen)
- Account information (contract type, tenure, payment method, billing)
- Service subscriptions (internet service, security, streaming, support)
- Charges (monthly charges, total charges)
- Churn label (Yes / No)

The dataset represents a telecom-style customer churn problem commonly used for analytics and modeling practice.

---

## 📈 Tableau Dashboard

The dashboard explores churn patterns across multiple dimensions:

### Key Views
- Total customers, active customers, churned customers, average revenue per customer
- Churn rate by payment method and contract type
- Customer segmentation by gender and senior citizen status
- Customer lifetime value distribution
- Relationship between tenure and total charges

### Interactivity
- Filters for:
  - Payment Method
  - Contract
  - Churn Label
  - Average Churn Rate
- Clicking on segments dynamically updates all visuals for focused analysis.

### Sample Screenshots
- Full dashboard overview  
- Filtered segment view (example: Credit Card customers)  
- Insight-focused zoom

Dashboard files and screenshots are located in the `tableau_dashboard/` folder.

---

## 🤖 Machine Learning Model

A CatBoostClassifier was trained to predict customer churn.

### Why CatBoost?
- Handles categorical features natively
- Requires minimal encoding
- Performs well on tabular business data
- Robust to mixed feature types

### Target Variable
- Churn Value (binary 0 = No, 1 = Yes)

### Feature Selection
Feature importance was extracted from the trained model to identify the most influential predictors.  
Top drivers included:

- Contract type
- Monthly charges
- Tenure months
- Total charges
- Payment method
- Online security
- Tech support
- Paperless billing

Low-impact features were removed to improve interpretability while maintaining performance.

---

## 📏 Model Evaluation

Evaluation focuses on both predictive performance and business relevance.

### Metrics
- Accuracy
- Confusion Matrix
- ROC-AUC Score

ROC-AUC measures the model’s ability to rank churners higher than non-churners independent of classification threshold.

### Threshold Tuning
The default classification threshold (0.5) was adjusted to improve recall for churn customers.  
Lowering the threshold increases the number of detected churners at the cost of higher false positives, which aligns with real-world retention strategies where missing a churner is more costly than contacting a loyal customer.

### Visual Results
- Confusion matrix visualization
- ROC curve with baseline comparison

ML result images are available in the `ml_results/` folder.

---

## 🔍 Key Business Insights

- Month-to-month contracts show significantly higher churn than long-term contracts.
- Customers using electronic check payment methods exhibit higher churn risk.
- Longer tenure strongly reduces churn probability.
- Higher monthly charges correlate with increased churn.
- Certain service features (online security, tech support) are associated with lower churn.

Machine learning feature importance confirms these dashboard-driven insights.

---

## 🧪 Optional Interactive Prediction

The notebook includes an optional interactive section that allows users to manually input customer features and receive a churn risk prediction locally.  
This is intended for experimentation and demonstration purposes.

---

## ▶️ How to Run

1. Clone the repository.
2. Install required Python libraries:
   - pandas
   - scikit-learn
   - catboost
   - matplotlib
3. Open the notebook in Jupyter or VS Code.
4. Run cells sequentially.

Tableau dashboard can be opened using Tableau Public or Tableau Desktop.

---

## 🚀 Future Improvements

- Hyperparameter tuning and cross-validation
- Additional models for comparison
- Feature engineering experimentation
- Deployment of prediction interface as a web app
- Automated reporting pipeline

---

## 👤 Author

Simranjit Singh - **mr.ramgharia2054@gmail.com**
