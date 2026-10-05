# 💳 Credit Risk Assessment System

An end-to-end **Machine Learning + FastAPI** application that predicts loan default risk using borrower and loan information.

The system uses **XGBoost** for binary classification, an optimized decision threshold for risk classification, and **FastAPI** to expose the trained model through a REST API. The application is deployed on **Render** for public access.

## 🚀 Live Demo

**Live API:**
https://credit-risk-system-shan.onrender.com

**Interactive API Documentation:**
https://credit-risk-system-shan.onrender.com/docs

The `/docs` endpoint provides an interactive Swagger UI for testing the prediction API directly from the browser.


<img width="1796" height="967" alt="image" src="https://github.com/user-attachments/assets/10eecef2-e98a-431d-b1aa-eebeb09a206d" />
---

## 📌 Project Overview

Credit risk assessment is an important problem in financial institutions, where accurately identifying potentially risky borrowers can help reduce loan defaults.

This project converts a machine-learning model into a deployable API-based application.

### System Workflow

```text
Borrower Input
      ↓
FastAPI REST API
      ↓
Pydantic Validation
      ↓
Feature Preparation
      ↓
XGBoost Model
      ↓
Default Probability
      ↓
Optimized Threshold
      ↓
Risk Prediction
```

---

## 🧠 Machine Learning

The system uses **XGBoost** for binary classification.

Instead of directly returning only a class label, the model generates a probability of default:

```text
P(Default)
```

This probability is evaluated using an optimized classification threshold stored in:

```text
best_threshold.pkl
```

The trained model is stored in:

```text
credit_risk_model.pkl
```

This allows the deployed FastAPI application to load the trained model and perform predictions without retraining.

---

## 📊 Input Features

The API accepts the following borrower and loan features:

| Feature                      | Description                         |
| ---------------------------- | ----------------------------------- |
| `person_age`                 | Applicant's age                     |
| `person_income`              | Annual income                       |
| `person_home_ownership`      | Home ownership status               |
| `person_emp_length`          | Employment length                   |
| `loan_intent`                | Purpose of the loan                 |
| `loan_grade`                 | Loan grade                          |
| `loan_amnt`                  | Requested loan amount               |
| `loan_int_rate`              | Loan interest rate                  |
| `loan_percent_income`        | Loan amount as percentage of income |
| `cb_person_default_on_file`  | Previous default indicator          |
| `cb_person_cred_hist_length` | Length of credit history            |

---

## ⚡ API

### Prediction Endpoint

```http
POST /predict
```

The endpoint receives borrower information and returns a credit-risk prediction from the trained XGBoost model.

### Example Request

```json
{
  "person_age": 30,
  "person_income": 60000,
  "person_home_ownership": "RENT",
  "person_emp_length": 5,
  "loan_intent": "PERSONAL",
  "loan_grade": "B",
  "loan_amnt": 10000,
  "loan_int_rate": 11.5,
  "loan_percent_income": 0.17,
  "cb_person_default_on_file": "N",
  "cb_person_cred_hist_length": 8
}
```

### Test the API

Open the Swagger documentation:

**https://credit-risk-system-shan.onrender.com/docs**

From there, you can select `POST /predict`, click **Try it out**, provide the input values, and execute the request directly from the browser.

---

## 🗂️ Project Structure

```text
Credit_risk_System/
│
├── creditRisk.ipynb
├── main.py
├── credit_risk_model.pkl
├── best_threshold.pkl
├── requirements.txt
├── runtime.txt
├── render.yaml
└── README.md
```

### Key Files

| File                    | Purpose                                                        |
| ----------------------- | -------------------------------------------------------------- |
| `creditRisk.ipynb`      | Data analysis, preprocessing, model development and evaluation |
| `main.py`               | FastAPI application and prediction endpoint                    |
| `credit_risk_model.pkl` | Trained XGBoost model                                          |
| `best_threshold.pkl`    | Optimized classification threshold                             |
| `requirements.txt`      | Python dependencies                                            |
| `runtime.txt`           | Python runtime configuration                                   |
| `render.yaml`           | Render deployment configuration                                |

---

## 🛠️ Tech Stack

**Machine Learning**

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Joblib

**Data Analysis**

* Matplotlib
* Seaborn

**Backend**

* FastAPI
* Pydantic
* Uvicorn

**Deployment**

* Render
* GitHub

---

## 💻 Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/AnviJha/Credit_risk_System.git
cd Credit_risk_System
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv .venv
```

Activate it:

```powershell
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Start the API

```bash
uvicorn main:app --reload
```

The API will be available at:

```text
http://127.0.0.1:8000
```

Swagger documentation:

```text
http://127.0.0.1:8000/docs
```

---

## ☁️ Deployment

The application is deployed using **Render**.

### Deployment Architecture

```text
GitHub Repository
       ↓
     Render
       ↓
Install Dependencies
       ↓
Start FastAPI Application
       ↓
Public REST API
       ↓
User / Client Application
```

### Live Application

```text
https://credit-risk-system-shan.onrender.com
```

### API Documentation

```text
https://credit-risk-system-shan.onrender.com/docs
```

---

## 📈 Key Highlights

* End-to-end credit-risk machine learning pipeline
* XGBoost binary classification
* Probability-based default prediction
* Optimized classification threshold
* Serialized model for production inference
* FastAPI REST API
* Pydantic input validation
* Interactive Swagger API documentation
* Cloud deployment using Render
* GitHub-based deployment workflow

---

## 🔮 Future Improvements

* SHAP-based prediction explainability
* Feature importance visualization
* Credit-risk dashboard
* Authentication and authorization
* Automated model retraining
* Model performance monitoring
* Data drift detection
* Unit and integration testing
* CI/CD pipeline
* Database integration
* API logging and monitoring

---

## 🎯 Project Objective

The objective of this project is to demonstrate the complete journey from **machine-learning experimentation to a publicly accessible ML API**.

```text
Data Analysis
      ↓
Model Training
      ↓
Model Evaluation
      ↓
Threshold Optimization
      ↓
Model Serialization
      ↓
FastAPI
      ↓
Cloud Deployment
```

This demonstrates practical skills across **Machine Learning, Backend API Development, and ML Deployment**.

---

## 👩‍💻 Author

**Anvi Jha**

B.Tech Computer Science & Data Science

GitHub: https://github.com/AnviJha

---

## ⭐ Project Highlight

> An end-to-end credit-risk prediction system that combines XGBoost-based machine learning, optimized thresholding, FastAPI inference, and cloud deployment to provide an accessible loan-default risk prediction API.
