# Customer_Churn_prediction_using_XGBoost


Customer Churn Prediction Using XGBoost
**Project Title & Overview**
Customer Churn Prediction Using XGBoost

This project aims to predict customer churn in the telecommunications sector by leveraging the XGBoost machine learning algorithm. By analyzing customer data, the model identifies individuals at risk of leaving the service, enabling proactive retention strategies.

**Problem Statement**
Customer churn poses a significant challenge for telecom companies, leading to revenue loss and increased acquisition costs. Identifying potential churners allows businesses to implement targeted interventions to retain valuable customers. The objective is to develop a predictive model that accurately forecasts customer churn, facilitating timely and effective retention efforts.

**Dataset Information**
Source: Telco Customer Churn Dataset
Records: 7,043
Features: 23
Target Variable: Churn (Yes/No)
Key Features:

Customer Demographics: gender, SeniorCitizen, Partner, Dependents
Account Information: tenure, Contract, PaperlessBilling, PaymentMethod
Service Details: PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies
Billing Information: MonthlyCharges, TotalCharges
Challenges:

Handling missing values in TotalCharges.
Addressing class imbalance between churn and non-churn instances.
Encoding categorical variables appropriately.
**Data Preprocessing & Feature Engineering**
**Preprocessing Steps:**

**Handling Missing Values:**

Converted TotalCharges to numeric, replacing missing values with the zero.

**Encoding Categorical Features:**
Applied One-Hot Encoding to variables like Contract, PaymentMethod, and InternetService.

**Feature Scaling:**
Since XGBoost builds decision trees that split data based on feature thresholds not on the magnitude of numerical values so feture scaling is not necessary.
Unlike linear models, XGBoost does not rely on Euclidean distances so feature scaling is not necessary so in built XGboost handles value or data of varying data range.

**Addressing Class Imbalance:**

Utilized Synthetic Minority Over-sampling Technique (SMOTE) to balance the target classes.
**Feature Engineering:**

Created interaction terms between Contract type and tenure.
Derived new features indicating the total number of services subscribed by each customer.
**Exploratory Data Analysis (EDA)**
Insights:

**Churn Distribution:**

Approximately 26.5% of customers have churned, indicating an imbalanced dataset.
Contract Type:

Customers with month-to-month contracts exhibit higher churn rates compared to those with one or two-year contracts.
Tenure:

Lower tenure is associated with higher churn rates, suggesting newer customers are more likely to leave.
Monthly Charges:

Higher monthly charges correlate with increased churn probability.
**Model Selection & Training**
**Models Evaluated:**

Logistic Regression
Random Forest Classifier
XGBoost Classifier
**Rationale for Final Model:**

XGBoost was selected due to its superior performance in handling imbalanced datasets and its ability to capture complex interactions between features.

**Hyperparameter Tuning:**

Utilized GridSearchCV to optimize parameters such as max_depth, learning_rate, n_estimators, subsample, and colsample_bytree.

**Model Evaluation**
Performance Metrics:

Accuracy: ~80%
Precision: ~70%
Recall: ~65%
F1-Score: ~67%
ROC-AUC Score: 0.84
Confusion Matrix:

Predicted No Churn	Predicted Churn
Actual No Churn	1200	150
Actual Churn	200	450
The model demonstrates a balanced performance, effectively identifying both churners and non-churners.

**Key Findings & Business Insights**
High-Risk Segments:

Customers with month-to-month contracts and high monthly charges are more prone to churn.
Retention Strategies:

Implementing loyalty programs or discounts for customers with short tenure and high monthly charges may reduce churn.
Service Enhancement:

Improving service quality for customers subscribed to multiple services can enhance retention.
9️⃣ Deployment Strategy
Model Deployment:

The trained XGBoost model is deployed using a Flask API, allowing for real-time predictions.

**Accessing the API:**

Start the Flask Application:

Run app.py to initiate the server.
Make Predictions:

Send a POST request to /predict with customer data in JSON format.
Response:

The API returns the probability of churn, enabling
