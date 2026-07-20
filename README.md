# Machine Learning Multi-Layer Customer Targeting System For Term Deposits

![Python](https://img.shields.io/badge/Python-3.11-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-blue)
![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualisation-red)
![DuckDB](https://img.shields.io/badge/DuckDB-SQL-yellow)
![License](https://img.shields.io/badge/License-MIT-success)

## Project Overview

Traditional bank marketing campaigns contact every customer, often resulting in thousands of unnecessary phone calls while still missing valuable potential subscribers.

This project develops a **multi-layer machine learning system** that progressively identifies the customers most likely to subscribe to a term deposit while dramatically reducing marketing effort.

Rather than treating every customer equally, the system combines:

- Supervised Machine Learning
- Probability Ranking
- Cumulative Recall Optimisation
- Multi-Layer Decision Making
- Customer Segmentation (K-Means Clustering)

to maximise customer retention while reducing operational costs.

---

# Business Problem

A European bank conducts direct marketing campaigns for term deposits.

The existing strategy involves contacting thousands of customers multiple times regardless of their likelihood of subscribing.

The objective of this project is to answer:

> **How can we retain the majority of subscribers while making substantially fewer phone calls?**

---

# Dataset

The dataset contains **40,000 customers** and includes demographic, financial and campaign information such as:

- Age
- Job
- Education
- Marital Status
- Account Balance
- Housing Loan
- Personal Loan
- Contact Method
- Campaign Information
- Call Duration
- Subscription Outcome

Target Variable:

```
y
```

- Yes
- No

---

# Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn
- DuckDB
- Random Forest
- Hyperparameter Optimisation
- K-Means Clustering

---

# Project Workflow

```
Data Collection
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Feature Engineering
        │
        ▼
Baseline Classification Model
        │
        ▼
Layer 1
Pre-call Customer Selection
        │
        ▼
Cumulative Recall Optimisation
        │
        ▼
Layer 2
Post-call Refinement using Call Duration
        │
        ▼
Customer Segmentation
(K-Means)
        │
        ▼
Business Recommendations
```

---

# Exploratory Data Analysis

The project begins by understanding the customer base through:

- Missing value analysis
- Class imbalance analysis
- Distribution visualisation
- Correlation matrix
- Mutual Information
- Feature importance analysis

Key findings included:

- Strong class imbalance (≈7% subscribers)
- Call duration was the strongest predictor of subscription
- Month and contact type also contained predictive information

---

# Layer 1 – Customer Prioritisation

The first layer predicts customer subscription probability **before any phone call has taken place.**

Only customer information available before contact is used.

Instead of predicting simply Yes/No, customers are ranked according to their predicted probability of subscribing.

This ranking allows the bank to choose exactly how many customers should be contacted.

### Results

- 22,515 recommended initial calls
- 17,485 unnecessary calls avoided
- 80.14% subscriber retention
- 66.2% classification accuracy
- 63.2% recall

Rather than contacting every customer, the bank can retain over 80% of subscribers while reducing initial marketing effort by almost half.

---

# Layer 2 – Intelligent Follow-up

Once customers have been contacted, additional information becomes available, particularly **call duration**.

Layer 2 incorporates this information to determine which customers deserve follow-up calls.

This creates a progressive decision system where:

Layer 1 answers:

> Who should we call?

Layer 2 answers:

> Who is worth calling again?

### Results

- 11,397 recommended follow-up calls
- 94% cumulative recall
- 87.6% accuracy
- 43.4% precision
- 67.7% recall
- 75% customer retention overall

The second layer substantially improves the efficiency of follow-up campaigns by focusing resources on highly engaged customers.

---

# Customer Segmentation

Subscribers were further analysed using **K-Means Clustering**.

Instead of asking:

> Who will subscribe?

the project also asks:

> What types of subscribers exist?

DuckDB SQL was used to isolate subscribers before clustering.

Each cluster was profiled using:

- Average numerical values
- Most frequent categorical attributes
- Cluster visualisations

This provides actionable customer personas that marketing teams can use to tailor future campaigns.

---

# Business Impact

Compared to a traditional campaign:

| Traditional Campaign | Proposed System |
|----------------------|----------------|
| 40,000 initial calls | 22,515 initial calls |
| Contact every customer | Target highest-value customers |
| Generic follow-ups | 11,397 targeted follow-ups |
| Limited customer understanding | Customer segmentation and profiling |
| 115,000 total marketing calls | 43,800 total marketing calls made for 75% customer retention, saving over 200 days of calls alone|

The proposed system enables the bank to:

- Reduce unnecessary marketing costs
- Prioritise high-value customers
- Improve campaign efficiency, saving over 200 days worth of time in calls
- Maintain over 75% of successful subscribers
- Create targeted marketing strategies for different customer segments

---

# Repository Structure

```
.
├── data/
├── notebooks/
├── figures/
├── README.md
└── requirements.txt
```

---

# Future Improvements

Potential future work includes:

- XGBoost and LightGBM models
- Bayesian Hyperparameter Optimisation
- Cost-sensitive learning
- Explainable AI (SHAP)
- Customer Lifetime Value prediction
- Automated marketing recommendation system

---

# Key Skills Demonstrated

- Machine Learning
- Classification
- Feature Engineering
- Model Evaluation
- Hyperparameter Optimisation
- Cross Validation
- Customer Segmentation
- SQL with DuckDB
- Business Analytics
- Data Visualisation
- End-to-End Machine Learning Pipeline

---

# For Recruiters & Hiring Managers

This project demonstrates much more than training a classification model.

It showcases the ability to design an end-to-end machine learning solution around a real business problem, balancing predictive performance with operational efficiency. Rather than optimising for accuracy alone, the solution incorporates cumulative recall analysis, probability-based customer ranking, multi-layer modelling, and unsupervised customer segmentation to support practical business decision-making.

The project highlights experience with feature engineering, model optimisation, cross-validation, supervised and unsupervised learning, SQL integration using DuckDB, and translating analytical findings into actionable business recommendations.

The focus throughout was not simply to build an accurate model, but to design a system capable of reducing marketing costs while maintaining a high proportion of successful customer subscriptions.
