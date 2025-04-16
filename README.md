# 📊 Employee Turnover Analytics

## 🏢 Project Overview

**Portobello Tech**, an innovative app company, is leveraging data to predict **employee turnover** – the number of workers who leave over time. As part of the HR analytics initiative, this project applies Machine Learning techniques to identify trends, cluster employee profiles, balance class representation, and ultimately **predict the likelihood of turnover**.

As the **ML Developer**, your responsibility is to support the HR Department with data-driven insights and modeling.

---

## 📁 Dataset

- **Source**: [Kaggle – HR Analytics Dataset](https://www.kaggle.com/liujiaqi/hr-comma-sepcsv)

### 🔹 Column Descriptions

| Column Name              | Description                                                               |
|--------------------------|---------------------------------------------------------------------------|
| `satisfaction_level`     | Satisfaction level of an employee (0 to 1)                                |
| `last_evaluation`        | Last evaluation score (0 to 1)                                            |
| `number_project`         | Number of projects an employee was involved in                           |
| `average_montly_hours`   | Average monthly office hours                                              |
| `time_spend_company`     | Number of years the employee stayed with the company                      |
| `Work_accident`          | 0 = No accident, 1 = Had an accident                                      |
| `left`                   | 0 = Stayed with the company, 1 = Left                                     |
| `promotion_last_5years`  | Whether the employee was promoted in the last 5 years (0/1)               |
| `Department`             | Department the employee belongs to                                       |
| `salary`                 | Employee’s salary level                                                   |

---

## ✅ Project Steps

### 1. Data Quality Checks
- Check for and handle missing or inconsistent values in the dataset.

---

### 2. Exploratory Data Analysis (EDA)

#### 🔍 Identify Factors Influencing Turnover
- Use statistical summaries and visualizations to discover insights.

#### 📊 Visualizations:
- **Heatmap** of the correlation matrix between all numerical features.
- **Distribution Plots**:
  - Employee Satisfaction (`satisfaction_level`)
  - Last Evaluation (`last_evaluation`)
  - Average Monthly Hours (`average_montly_hours`)
- **Bar Plot**:
  - Number of Projects vs Turnover (`number_project`, hue = `left`)
  - Draw insights from the work pattern of employees who stayed vs. those who left.

---

### 3. Clustering Analysis

#### 🎯 Objective:
Cluster employees who left the company based on:
- `satisfaction_level`
- `last_evaluation`

#### 🔹 Tasks:
- Filter rows where `left = 1`
- Apply **K-Means Clustering** with 3 clusters
- Visualize and interpret the clusters:
  - What defines each cluster?
  - What insights can HR use?

---

### 4. Handle Class Imbalance using SMOTE

#### 🔄 Preprocessing:
- Convert categorical columns to numerical using `pd.get_dummies()`
- Merge categorical and numeric data
- Split the dataset:
  - **80:20** stratified train-test split (`random_state=123`)
- Apply **SMOTE** on the training set to balance the class distribution

---

### 5. Model Training with 5-Fold Cross-Validation

Train and evaluate the following models using **5-Fold Cross-Validation**:

| Model                    | Evaluation Method             |
|--------------------------|-------------------------------|
| Logistic Regression      | 5-fold CV, classification report |
| Random Forest Classifier | 5-fold CV, classification report |
| Gradient Boosting Classifier | 5-fold CV, classification report |

---

### 6. Model Evaluation & Selection

#### 📈 Metrics:
- **ROC/AUC**: Plot ROC curves for each model
- **Confusion Matrix**: Evaluate predictions

#### ❓ Metric Choice:
- Decide whether to prioritize **Recall** (e.g. catching likely leavers) or **Precision** (e.g. avoiding false positives)
- Justify choice based on HR use-case

---

### 7. Retention Strategy Recommendations

#### 📊 Prediction:
- Use the best model to predict **probability of turnover** for each employee in the test data

#### 🧭 Risk Zones:

| Zone             | Score Range       | Suggested Strategy                          |
|------------------|-------------------|---------------------------------------------|
| 🟢 Safe Zone     | Score < 20%       | Maintain current engagement strategies      |
| 🟡 Low-Risk Zone | 20% < Score < 60% | Regular feedback and recognition            |
| 🟠 Medium-Risk   | 60% < Score < 90% | Conduct one-on-one check-ins, provide growth opportunities |
| 🔴 High-Risk     | Score > 90%       | Immediate HR intervention & retention plan  |

---

## 🛠 Tools & Libraries Used

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- imbalanced-learn (`SMOTE`)

---

## 📌 Conclusion

This project delivers a full HR analytics solution to help **predict employee turnover**, understand **why employees leave**, and **recommend retention strategies** to improve long-term employee engagement.

---


