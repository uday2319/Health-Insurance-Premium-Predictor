<div align="center">

# 🏥 Health Insurance Premium Predictor

**An end-to-end machine learning app that estimates a person's medical insurance premium from their age, BMI, gender, number of children, region and smoking status. A tuned Random Forest model makes the predictions, served through a Streamlit web interface.** 

</div>

---

## 📌 Overview

Insurance premiums depend on a mix of personal and lifestyle factors, and the relationship isn't simple. Smoking alone can multiply costs, and it interacts with age and BMI.

This project builds a **regression model** that learns these patterns from historical insurance data and predicts the expected premium for a new person. The final model is saved and wrapped in a **Streamlit app**, so anyone can enter their details and get an estimate instantly with no code.

### 🎯 Objective
Build a complete ML pipeline that covers data cleaning, EDA, feature engineering, model training, tuning, evaluation and deployment, so that it predicts medical insurance costs accurately and is easy to use.

---

## 📂 Input Features

| Feature    | Type        | Description                                    |
|------------|-------------|------------------------------------------------|
| `age`      | Numerical   | Age of the primary beneficiary                 |
| `sex`      | Categorical | Gender: male / female                          |
| `bmi`      | Numerical   | Body Mass Index                                |
| `children` | Numerical   | Number of children / dependents covered        |
| `smoker`   | Categorical | Smoking status: yes / no                       |
| `region`   | Categorical | Residential region in the US                   |
| **`charges`** | **Target** | **Medical insurance premium to predict**     |

---

## 🏗️ Architecture

```
┌──────────────────────┐
│     User Input       │  age, sex, bmi, children, smoker, region
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│  Data Preprocessing  │  cleaning, type handling
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ Feature Engineering  │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│   One-Hot Encoding   │  sex, smoker, region → numeric columns
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ Random Forest Model  │  tuned with GridSearchCV, loaded via Joblib
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ Premium Prediction   │  displayed in the Streamlit app
└──────────────────────┘
```

---

## 🔄 ML Workflow

| Step | Stage                        | What was done                                                     |
|:----:|------------------------------|-------------------------------------------------------------------|
| 1    | **Data Cleaning & EDA**      | Checked for missing values and duplicates; looked at distributions and how features relate to charges |
| 2    | **Feature Engineering**      | Prepared and transformed features for modelling                   |
| 3    | **One-Hot Encoding**         | Converted categorical columns (`sex`, `smoker`, `region`) to numeric |
| 4    | **Model Training**           | Trained Decision Tree and Random Forest regressors                |
| 5    | **Model Comparison**         | Compared models on R², MAE and RMSE                               |
| 6    | **Hyperparameter Tuning**    | Tuned Random Forest using `GridSearchCV`                          |
| 7    | **Model Evaluation**         | Checked on the test set and with cross-validation                 |
| 8    | **Model Serialization**      | Saved the final model with `joblib`                               |
| 9    | **Deployment**               | Built an interactive Streamlit app for live predictions           |

---

## 🤖 Models

| Model                                | Role                                                    |
|--------------------------------------|---------------------------------------------------------|
| Decision Tree Regressor              | Baseline: simple, easy to interpret, prone to overfitting |
| Random Forest Regressor              | Ensemble of trees: lower variance, better generalisation |
| **Random Forest + GridSearchCV** ✅  | **Final model**, tuned for the best performance         |

---

## 📊 Model Performance (Final Model)

| Metric                     | Score      | Meaning                                                  |
|----------------------------|------------|----------------------------------------------------------|
| **R² Score**               | **0.87**   | Explains ~87% of the variance in insurance charges       |
| **MAE**                    | **2356.3** | On average, predictions are off by ~2,356                |
| **RMSE**                   | **4386.0** | Penalises large errors more; affected by high-cost cases |
| **Cross-Validation Score** | **0.84**   | Performance stays consistent across data splits          |

> The small gap between the test R² (0.87) and the CV score (0.84) suggests the model **generalises well** and isn't heavily overfitting.

---

## 🖥️ Streamlit Application

The trained model is loaded into a Streamlit interface where users can:

1. Enter **age, BMI, gender, number of children, region and smoking status**
2. Click **Predict**
3. Instantly see the **estimated insurance premium**

<!-- Add a screenshot of your app here -->
<!-- ![App Screenshot](assets/app_screenshot.png) -->

---

## 🛠️ Tech Stack

| Category            | Tools                          |
|---------------------|--------------------------------|
| Language            | Python                         |
| Data Handling       | Pandas, NumPy                  |
| Visualization       | Matplotlib, Seaborn            |
| Machine Learning    | Scikit-learn                   |
| Model Serialization | Joblib                         |
| Deployment          | Streamlit                      |

--- 

## 📁 Project Structure

```
Health-Insurance-Premium-Predictor/
├── app1.py                 # Streamlit application
├── model.pkl               # Saved Random Forest model (joblib)
├── insurance.csv           # Dataset
├── notebook.ipynb          # EDA, training, tuning & evaluation
├── requirements.txt        # Python dependencies
└── README.md
```

> ✏️ Update the file names above to match your repository.

---

## 🔮 Future Improvements

- [ ] Try gradient boosting models (**XGBoost**, **LightGBM**, **CatBoost**)
- [ ] Add **SHAP** explanations to show *why* a premium was predicted
- [ ] Wrap preprocessing and the model in a single scikit-learn `Pipeline`
- [ ] Deploy publicly on **Streamlit Community Cloud** or **Hugging Face Spaces**
- [ ] Add input validation and confidence ranges to predictions

---

## 📌 Key Learnings

- Built a **complete ML lifecycle** from raw data to a deployed app
- Saw how **ensemble methods** (Random Forest) beat a single Decision Tree
- Used **GridSearchCV** and **cross-validation** for reliable tuning and evaluation
- Learned to **serialize models** with Joblib and serve them through **Streamlit**
- Learned to read regression metrics (**R², MAE, RMSE**) in a real business setting

---
 
