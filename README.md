**Health Insurance Premium Predictor**

A machine learning application that predicts medical insurance premiums based on age, BMI, gender, number of children, region, and smoking status.

 **Objective**

Build an end-to-end regression model to estimate medical insurance costs and deploy it through a simple Streamlit application.

🏗️ **Architecture**

User Input
    ↓
Data Preprocessing
    ↓
Feature Engineering
    ↓
One-Hot Encoding
    ↓
Random Forest Regression
    ↓
Insurance Premium Prediction
    ↓
Streamlit Application

🔄 **ML Workflow** :
Data Cleaning & Exploratory Data Analysis
Feature Engineering
One-Hot Encoding
Model Training
Model Comparison
Hyperparameter Tuning using GridSearchCV
Model Evaluation
Model Serialization using Joblib
Streamlit Deployment

 **Models**
Decision Tree Regressor
Random Forest Regressor
Optimized Random Forest using GridSearchCV

📊 **Model Performance**
Metric	Score
R² Score	0.87
MAE	2356.3
RMSE	4386.0
Cross-Validation Score	0.84

🖥️ **Application**

The trained model is integrated with Streamlit to provide an interactive interface for entering user details and obtaining the predicted insurance premium.

🛠️ **Tech Stack**

Python · Pandas · NumPy · Scikit-learn · Matplotlib · Seaborn · Joblib · Streamlit

🚀** Run Locally**
pip install -r requirements.txt
streamlit run app1.py
📌 Key Learning

This project provided hands-on experience with the complete end-to-end machine learning workflow, from data preprocessing and feature engineering to model training, hyperparameter tuning, evaluation, model saving, and deployment.

