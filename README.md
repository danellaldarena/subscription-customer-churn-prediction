# Customer Churn Analysis and Prediction for Digital Subscription Services

## Project Overview

This project focuses on analyzing and predicting customer churn in digital subscription services to support data-driven customer retention strategies.

Customer churn occurs when subscribers discontinue their subscriptions, potentially reducing recurring revenue and long-term business sustainability. By analyzing customer demographics, subscription characteristics, usage behavior, payment history, and promotional engagement, this project aims to identify customers at risk of churn and provide actionable business recommendations.

This project was developed as a Final Project for **Statistical Data Analysis** at the Department of Statistics, Faculty of Science and Data Analytics, Institut Teknologi Sepuluh Nopember (ITS), Surabaya, in 2025.

## Project Objectives

- Explore customer behavior and identify patterns associated with churn through Exploratory Data Analysis (EDA).
- Develop classification models to predict customers at risk of churn.
- Identify factors associated with customer churn.
- Interpret model predictions and evaluate classification performance.
- Provide data-driven recommendations to improve customer retention.

## Dataset Description

The dataset contains structured customer-level information from a digital subscription service, including demographic characteristics, subscription details, user activity, payment failures, promotional engagement, and churn status.

| Variable | Description |
|---|---|
| `Age` | Customer age |
| `Tenure_days` | Subscription duration in days |
| `Plan_type` | Subscription plan: Basic, Standard, or Premium |
| `Auto_renew_enable` | Whether automatic renewal is enabled |
| `Session_count` | Number of sessions in the last 30 days |
| `Avg_session_duration` | Average session duration in minutes |
| `Days_active` | Number of active days in the last 30 days |
| `Last_active_day_ago` | Days since the last activity |
| `Failed_payment_20d` | Number of failed payments |
| `Promo_receive_last_30d` | Whether the customer received a promotion |
| `Churn` | Target variable: 0 = retained, 1 = churned |

## Methodology

### 1. Data Preprocessing
- Missing-value analysis and imputation using Multiple Imputation by Chained Equations (MICE).
- Outlier detection and assessment.
- Encoding of categorical variables.
- Train-test split using an 80:20 ratio.
- SMOTE to address class imbalance.
- Normalization of numerical features.

### 2. Feature Engineering

Additional features were created to capture customer engagement, subscription lifecycle, and payment behavior, including:

- `recency_ratio`
- `activity_rate`
- `session_intensity`
- `avg_session_per_day`
- `failed_payment_rate`
- `is_new_user`
- `high_activity`

### 3. Exploratory Data Analysis (EDA)

EDA was performed to examine churn distribution, compare numerical characteristics between churned and retained customers, analyze categorical variables, and investigate correlations among customer attributes.

### 4. Classification Models

Three classification algorithms were evaluated:

- **Logistic Regression** — baseline classification model.
- **Random Forest** — ensemble model capable of capturing nonlinear relationships.
- **XGBoost** — gradient boosting model used to improve the detection of churn-risk customers.

### 5. Model Evaluation and Interpretation

Model performance was assessed using accuracy, precision, recall, ROC-AUC, classification reports, and confusion matrices. Threshold analysis was also conducted to evaluate the trade-off between false positives and false negatives.

## Key Findings

- Customer engagement indicators, including active days, session frequency, session duration, and time since the last activity, are important signals associated with churn.
- Customers without automatic renewal and customers experiencing repeated payment failures tend to exhibit higher churn risk.
- Logistic Regression and Random Forest performed well in classifying retained customers but failed to identify churn cases in the reported test evaluation.
- XGBoost achieved a churn recall of **1.00**, with a churn precision of **0.29** and an overall accuracy of **75%**.
- A classification threshold of approximately **0.14** was selected using the Youden Index to prioritize the detection of at-risk customers and reduce false negatives.

These results suggest that prioritizing churn detection may be more useful for retention strategies than relying on accuracy alone, particularly when churn cases are underrepresented.

## Business Recommendations

Based on the analysis, digital subscription providers can consider the following actions:

1. **Proactive retention campaigns:** Monitor customers with declining activity and long periods of inactivity.
2. **Automatic renewal engagement:** Encourage customers to enable automatic renewal where appropriate.
3. **Payment assistance:** Identify repeated payment failures and provide timely payment reminders or assistance.
4. **Targeted promotions:** Offer relevant incentives to customers showing signs of disengagement.
5. **Risk-based prioritization:** Use predicted churn probabilities to prioritize retention interventions while monitoring false-positive rates.

## Tools and Technologies

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- XGBoost
- Imbalanced-learn (SMOTE)
- MICE imputation

## Limitations

The results should be interpreted in the context of the available dataset and the selected train-test split. In particular, the small number of churn observations and the trade-off between false positives and false negatives should be considered before deploying the model in a real business environment.

## Authors

**Department of Statistics**  
Faculty of Science and Data Analytics  
Institut Teknologi Sepuluh Nopember (ITS), Surabaya

- Danella Citra Aldarena
- Maria Immaculata Dyah Hita Widowati
