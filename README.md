# Customer Churn Analysis for Telecom Industry

Predicting which telecom customers are likely to leave, and what to do about it.
Built as part of the Elevate Labs internship project phase.

## Dataset
IBM Telco Customer Churn: 7,043 customers, 21 columns (demographics, services, contract, billing, churn).

## What I did
1. Cleaned the data (fixed `TotalCharges`, 11 blank values from zero-tenure customers)
2. SQL aggregation (SQLite) of churn rate by contract, internet service, and payment method
3. Trained a Random Forest classifier (class-balanced, 80/20 stratified split)
4. Explained the model with feature importance
5. Segmented customers into At Risk / Loyal / Dormant

## Key results
- Overall churn: 26.5%
- Month-to-month contracts churn the most; fiber optic (41.9%) and electronic check (45.3%) are high-risk
- Model: ROC-AUC 0.84, recall 0.77 on churners, accuracy 0.77
- Top drivers: Contract, tenure, TotalCharges, MonthlyCharges, OnlineSecurity

## Project structure
```
├── Customer_Churn_Analysis.ipynb   # full analysis notebook
├── data/                           # raw + cleaned dataset
├── outputs/
│   ├── Churn_Analysis_Report.pdf   # 2-page report
│   └── churn_segments.csv          # per-customer churn probability + segment
└── requirements.txt
```

## Run it
```bash
pip install -r requirements.txt
jupyter notebook Customer_Churn_Analysis.ipynb
```

## Tools
Python, Pandas, Scikit-learn, SQL (SQLite), Matplotlib, Seaborn
