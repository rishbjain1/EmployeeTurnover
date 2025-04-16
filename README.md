📊 Employee Turnover Analytics

🏢 Project Overview

Portobello Tech, an innovative app company, is leveraging data to predict employee turnover – the number of workers who leave over time. As part of the HR analytics initiative, this project applies Machine Learning techniques to identify trends, cluster employee profiles, balance class representation, and ultimately predict the likelihood of turnover.

You are assigned as the ML Developer to assist the HR department in building a comprehensive predictive and analytical pipeline using past evaluation data, including:

Employee satisfaction
Project engagement
Evaluation scores
Working hours
Time at the company
Promotions
Salary
📁 Dataset

Source: Kaggle: HR Analytics Dataset
The dataset contains the following features:

Column Name	Description
satisfaction_level	Satisfaction level of an employee
last_evaluation	Last evaluation score (0 to 1)
number_project	Number of projects an employee was involved in
average_montly_hours	Average monthly office hours
time_spend_company	Tenure in the company (years)
Work_accident	0 = No accident, 1 = Had an accident
left	0 = Stayed, 1 = Left
promotion_last_5years	Promotion status in the last 5 years
Department	Employee’s department
salary	Salary level
✅ Tasks & Implementation

1. Data Quality Checks
Handle missing values and ensure data completeness.
2. Exploratory Data Analysis (EDA)
Analyze feature impact on turnover.
Visualizations:
Correlation heatmap
Distribution plots:
satisfaction_level
last_evaluation
average_montly_hours
Bar plot: Project count vs turnover
3. Clustering
Use K-Means Clustering on employees who left using:
satisfaction_level
last_evaluation
left
Create 3 clusters
Interpret clusters to find behavioral patterns
4. Class Imbalance Handling
Use SMOTE (Synthetic Minority Over-sampling Technique)
Steps:
Convert categorical columns using get_dummies()
Merge with numeric data
Split into 80:20 train/test sets (random_state=123)
Upsample minority class in training data using SMOTE
5. Model Training with 5-Fold Cross-Validation
Train and evaluate the following models:

Logistic Regression
Random Forest Classifier
Gradient Boosting Classifier
For each:

Apply 5-fold CV
Generate and analyze classification reports
6. Model Selection & Evaluation
Compare models using:
ROC/AUC scores and curves
Confusion matrices
Determine whether to prioritize Precision or Recall based on business context
7. Retention Strategy Recommendations
Predict turnover probability on the test set using the best model
Categorize employees into risk zones:

Zone	Score Range	Suggested Action
🟢 Safe Zone	< 20%	Maintain current engagement strategies
🟡 Low-Risk Zone	20% – 60%	Monitor & increase involvement
🟠 Medium-Risk	60% – 90%	Initiate engagement and career discussions
🔴 High-Risk	> 90%	Immediate HR intervention needed
💡 Tools & Libraries

Python
Pandas, NumPy
Matplotlib, Seaborn
Scikit-learn
Imbalanced-learn (SMOTE)
📌 Conclusion

This project helps HR identify and retain valuable employees, while reducing unwanted turnover through proactive, data-driven strategies.

