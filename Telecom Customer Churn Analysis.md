# Telecom Customer Churn Analysis

Project Overview

This project aims to predict customer churn for a telecom company using customer usage data across four months (June to September). By understanding and identifying the drivers of churn, the goal is to reduce the churn rate among high-value customers through targeted interventions. The analysis includes data preparation, feature engineering, model building, and recommendations to mitigate churn risk.

## Business Problem

Churn prediction is crucial for telecom companies as acquiring new customers is often more expensive than retaining existing ones. The objectives of this project are:

1. **Churn Prediction**: Predict whether high-value customers will churn in the last month (September) using data from the first three months.
2. **Identify Churn Drivers**: Understand key factors contributing to churn, enabling the company to take proactive measures to retain customers.

## Dataset

The dataset contains customer-level information for four months, with the following key data:

- **Usage Metrics**: Includes total incoming/outgoing call minutes, data usage (2G/3G), and recharge amounts.
- **Target Variable**: Churned (1) or Not Churned (0) in the fourth month (September).
- **High-Value Customers**: Customers filtered based on recharge amount above the 70th percentile in the good phase (first two months).

## Workflow

### 1. Data Preparation and Feature Engineering

- **Handling Missing Values**: Imputed missing values using the median to ensure data consistency.
- **High-Value Customer Filtering**: Selected customers whose average recharge was above the 70th percentile to focus on valuable users.
- **Churn Tagging**: Labeled customers as churned if they had no call or data activity in the fourth month (September).

### 2. Exploratory Data Analysis (EDA)

- **Distribution Analysis**: Visualized customer usage patterns to understand typical behavior.
- **Key Insights**: Found that higher call activity and data usage are linked to lower churn risk.

### 3. Model Building

- **Baseline Model**: Built a **Logistic Regression** model for its simplicity and interpretability.
- **Class Imbalance Handling**: Used `class_weight='balanced'` to address the imbalance between churned and non-churned classes.
- **Hyperparameter Tuning**: Performed **GridSearchCV** to tune parameters (e.g., regularization strength and solver).

### 4. Model Performance Evaluation

- **Metrics Used**: Precision, Recall, F1 Score, and Accuracy.
- **Key Results**:
    - Precision for churn improved slightly from **0.3254** to **0.3261** after tuning.
    - Recall remained consistent at **0.8131**, ensuring a high proportion of actual churners were identified.
    - F1 Score improved from **0.4648** to **0.4655**, indicating a slight improvement in the balance between precision and recall.

### 5. Feature Importance Analysis

- **Top Features**:
    - **Total Incoming Minutes of Usage in August**: Higher incoming call activity decreases churn risk.
    - **Data Volume Charged Beyond Quota**: High data overage charges increase the likelihood of churn.
    - **Total Outgoing Minutes of Usage in August**: Higher outgoing call activity decreases churn risk.

### 6. Business Insights and Recommendations

- **Encourage Engagement**: Customers with higher call activity tend to churn less. Offer incentives to increase incoming/outgoing call frequency.
- **Manage Data Overages**: Customers who exceed their data quota are more likely to churn. Introduce flexible data plans or discounts for overage charges to improve satisfaction.
- **Target Early Warning Signs**: Declining call or data activity should trigger early intervention campaigns to retain customers.

## Conclusion

The analysis helped predict customer churn and identify key indicators contributing to churn. **Hyperparameter tuning** provided slight improvements in model performance, while **feature importance analysis** offered actionable insights to reduce churn risk. Moving forward, deploying a real-time prediction system can help the telecom company proactively target high-risk customers with customized retention plans.

## Future Steps

1. **Advanced Modeling**: Consider building more complex models, such as **Random Forest** or **XGBoost**, to capture non-linear relationships and further improve prediction accuracy.
2. **Real-Time Deployment**: Deploy the model for real-time churn prediction, allowing proactive customer retention measures.
3. **Continuous Monitoring**: Regularly monitor model performance and recalibrate based on changing customer behaviors and market dynamics.

## Repository Contents

- **Telecom Churn Project.ipynb**: Jupyter notebook containing all the analysis, model building, and evaluation steps.
- Presentation (in pdf format)
- [**README.md**](http://readme.md/): Overview and summary of the project.

## How to Run the Project

1. Clone the repository.
2. Install the required packages using `pip install -r requirements.txt`.
3. Open the Jupyter Notebook and run all cells sequentially.

## Author

- Kaldhen Sangay Losel Lepcha