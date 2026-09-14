 SmartKart Customer Churn Prediction

 Project Overview

SmartKart is an online retail company facing a customer churn problem. Some customers are no longer purchasing, marketing campaigns have a low response, and customer complaints are increasing.

This project uses Machine Learning to identify customers who are likely to churn so that the retention team can take action before they leave.

The project uses Logistic Regression, a supervised machine learning algorithm suitable for binary classification such as Churn / No Churn.

---

 Business Objective

The main objective is to:

- Identify customers who are likely to churn.
- Understand the factors that may contribute to customer churn.
- Help SmartKart prioritize high-risk customers.
- Provide a business-ready customer churn risk report.

---

Dataset

The project uses:

"SmartKart_dirty_100_rows.csv"

The dataset contains 100 customer records and 5 columns:

Column| Description
"Customer_ID"| Unique customer identifier
"Age"| Customer age
"Monthly_Spend"| Customer's monthly spending
"Complaints"| Number of customer complaints
"Churn"| Target variable: 0 = No Churn, 1 = Churn

The dataset is intentionally made "dirty" to demonstrate real-world data preprocessing, including duplicates, missing values, invalid values, and outliers.

---

 Machine Learning Pipeline

The project follows these 15 steps:

1. Data Collection
2. Data Understanding
3. Data Cleaning
4. Outlier Detection & Treatment
5. Feature Selection
6. Define Target Variable
7. Encode Target Variable
8. Train-Test Split
9. Feature Standardisation
10. Model Building
11. Model Training
12. Prediction
13. Model Evaluation
14. Model Interpretation
15. Final Output

---

🧹 Data Preprocessing

The dataset contains several data-quality issues.

Data Cleaning

The project handles:

- Duplicate records
- Unnecessary whitespace
- Text values in numeric columns
- Invalid age values
- Negative spending values
- Missing values

Missing values are filled using the median, which is less affected by extreme values than the mean.

Outlier Treatment

Outliers are detected using the IQR (Interquartile Range) method.

Instead of deleting customers with extreme values, the project uses capping/winsorization so that the customer's other information is not lost.

---

 Features Used

The following three features are selected for prediction:

- "Age"
- "Monthly_Spend"
- "Complaints"

"Customer_ID" is excluded because it is only an identifier and does not provide meaningful information for predicting churn.

Target Variable

The target variable is:

"Churn"

- "0" → No Churn
- "1" → Churn

The target is already numeric, so additional encoding is not required.

---

 Train-Test Split

The cleaned dataset is divided into:

- 80% Training Data
- 20% Testing Data

Stratification is used to maintain a similar churn ratio in both datasets.

---

 Feature Standardisation

"StandardScaler" is used to standardise the numerical features.

This makes the features comparable in scale before applying Logistic Regression.

The scaler is fitted only on the training data and then applied to the test data to avoid data leakage.

---

 Machine Learning Model

Logistic Regression

The project uses Logistic Regression because churn is a binary classification problem.

The model learns the relationship between:

Age + Monthly Spend + Complaints → Churn

It also produces a churn probability, which can be useful for ranking customers according to their risk level.

---

 Model Evaluation

The model is evaluated using:

- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-Score

These metrics help understand not only how often the model is correct, but also the types of mistakes it makes.

The notebook's expected results are approximately:

- Accuracy: 89–95%
- Recall: ~100%
- Precision: 83–91%

The exact values may vary depending on the execution environment and dataset.

---

 Key Business Insights

The model coefficients are used to understand the factors influencing churn.

1. Monthly Spend

Higher monthly spending is associated with lower churn risk in this dataset.

2. Complaints

A higher number of complaints is associated with higher churn risk.

This makes customer complaint resolution an important area for SmartKart's retention strategy.

3. Age

Age has a comparatively smaller effect on churn in this dataset.

 Business Takeaway

«Reducing customer complaints and protecting high-spend customer relationships are important retention strategies for SmartKart.»

---

 Final Output

The project creates a business-ready file:

"smartkart_churn_risk_report.csv"

The report contains:

- Customer ID
- Age
- Monthly Spend
- Complaints
- Actual Churn
- Predicted Churn
- Churn Probability
- Risk Label

Customers are sorted according to their churn probability, allowing the retention team to focus on high-risk customers first.

The project also identifies the Top 5 highest-risk customers for immediate retention attention.

---
 Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Logistic Regression

---

 How to Run the Project

Option 1: Google Colab

1. Open the notebook in Google Colab.
2. Run the cells from top to bottom.
3. When prompted, upload:
   "SmartKart_dirty_100_rows.csv"
4. Continue running each step.
5. At the end, download:
   "smartkart_churn_risk_report.csv"

The notebook is designed to be run from top to bottom, with explanations provided throughout the pipeline.

Option 2: GitHub

Upload the following files to your repository:

SmartKart_Churn_Prediction_ML_Pipeline.ipynb
SmartKart_dirty_100_rows.csv
smartkart_churn_risk_report.csv
README.md

---

 Project Structure

SmartKart-Churn-Prediction/
│
├── SmartKart_Churn_Prediction_ML_Pipeline.ipynb
├── SmartKart_dirty_100_rows.csv
├── smartkart_churn_risk_report.csv
└── README.md

---

Learning Outcomes

Through this project, I learned how to:

- Work with a real-world-style dirty dataset.
- Identify and handle missing values.
- Remove duplicate records.
- Handle invalid data.
- Detect and treat outliers.
- Select relevant features.
- Define and encode a target variable.
- Split data into training and testing sets.
- Standardise numerical features.
- Build and train a Logistic Regression model.
- Make predictions.
- Evaluate a classification model.
- Interpret model coefficients.
- Convert ML predictions into a business-focused output.

---

 Future Improvements

The project can be improved further by:

- Testing other classification algorithms.
- Comparing multiple models.
- Using a larger customer dataset.
- Adding more customer behaviour features.
- Creating a dashboard for the retention team.
- Using the churn probability to create different customer-risk categories.

---

 Project Context

Course: Introduction to AI & ML
Program: BBA AI/ML / BBA FinTech & AI
Institution: Chitkara Business School

Project: SmartKart Customer Churn Prediction
Model: Logistic Regression
Dataset: 100 customer records

---

 Conclusion

This project demonstrates an end-to-end Machine Learning workflow for solving a real business problem.

Starting with a dirty customer dataset, the project performs data cleaning, outlier treatment, feature selection, standardisation, model training, prediction, and evaluation. Finally, the model generates a ranked churn-risk report that can help SmartKart's retention team decide which customers require attention first.
