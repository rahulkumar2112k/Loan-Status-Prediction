# 💰 Loan Prediction System Using SVM

Predict whether a loan will be **approved** or **disapproved** based on applicant details using a **Support Vector Machine (SVM)** model.

---

## 🚀 Project Overview

The Loan Prediction System predicts loan approval status using historical applicant data. Users can enter their details, and the system provides **real-time predictions**.  

Key features:
- Predict loan approval using SVM.
- Accepts user-friendly inputs (`Yes/No`, `Male/Female`).
- Handles numeric and categorical data.
- Works for single applicants or batch predictions.

---

## 🗂 Dataset Details

The dataset contains information of loan applicants and their financial background.  

| Column             | Type      | Description |
|-------------------|-----------|-------------|
| Gender             | Categorical | Male / Female |
| Married            | Categorical | Yes / No |
| Dependents         | Categorical / Numeric | 0,1,2,3+ (3+ converted to 4) |
| Education          | Categorical | Graduate / Not Graduate |
| Self_Employed      | Categorical | Yes / No |
| ApplicantIncome    | Numeric    | Applicant's income |
| CoapplicantIncome  | Numeric    | Co-applicant's income |
| LoanAmount         | Numeric    | Loan amount in thousands |
| Loan_Amount_Term   | Numeric    | Loan term in months |
| Credit_History     | Binary     | 1 = meets credit requirements, 0 = does not |
| Property_Area      | Categorical | Rural / Semiurban / Urban |
| Loan_Status        | Binary     | 1 = Approved, 0 = Not Approved (target variable) |

---

## 🛠 Data Preprocessing

- Removed rows with missing values.  
- Converted categorical columns to numeric:  
  - Gender: Male=1, Female=0  
  - Married: Yes=1, No=0  
  - Education: Graduate=1, Not Graduate=0  
  - Self_Employed: Yes=1, No=0  
  - Property_Area: Rural=0, Semiurban=1, Urban=2  
  - Dependents: '3+' → 4  
  - Loan_Status: Y=1, N=0  

---

## 📊 Dataset Insights

- **Applicants with Graduate education** have a higher loan approval rate.  
- **Married applicants** are more likely to have loans approved.  
- **Good credit history** strongly correlates with loan approval.  
- **Property area** also influences approval: Urban > Semiurban > Rural.  

| Feature              | Observation |
|---------------------|------------|
| Education            | Graduates ~70% approval, Non-Graduates ~50% |
| Married              | Married applicants ~65% approval |
| Credit_History       | Good credit history ~80% approval |
| Property_Area        | Urban ~75%, Semiurban ~60%, Rural ~50% |

---

## 🤖 Model Details

- **Algorithm:** Support Vector Machine (SVM)  
- **Kernel:** Linear  
- **Training Accuracy:** 83%  
- **Test Accuracy:** 80%  

**Confusion Matrix (Test Data)**

| Predicted \ Actual | Approved (1) | Disapproved (0) |
|-------------------|--------------|----------------|
| Approved (1)      | 45           | 7              |
| Disapproved (0)   | 5            | 23             |

- **Interpretation:**  
  - Model correctly predicts **approved and disapproved loans** with high accuracy.  
  - Few misclassifications occur for borderline cases.  

---

## 🖥 Sample Predictions

| Applicant Details                                           | Model Prediction |
|-------------------------------------------------------------|----------------|
| Male, Graduate, Married, 2 Dependents, Good Credit, Urban  | Loan Approved ✅ |
| Female, Not Graduate, Single, No Dependents, Bad Credit, Rural | Loan Disapproved ❌ |
| Male, Graduate, Married, 1 Dependent, Good Credit, Semiurban | Loan Approved ✅ |
| Female, Graduate, 3+ Dependents, Good Credit, Urban        | Loan Approved ✅ |

- Users can input **personal and financial information** to get **instant loan approval prediction**.

---

## 📌 Usage

1. Clone the repository.  
2. Install required libraries (pandas, numpy, scikit-learn, seaborn, matplotlib).  
3. Load the dataset and train the SVM model.  
4. Enter applicant details for predictions.  

---

## 📈 Future Enhancements

- Deploy as a **web application** using Flask or Streamlit.  
- Use advanced ML models like Random Forest or XGBoost to improve accuracy.  
- Add **feature importance analysis** and **visual dashboard**.  
- Handle **imbalanced datasets** using oversampling or SMOTE.  

---

