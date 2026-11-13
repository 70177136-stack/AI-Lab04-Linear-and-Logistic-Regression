# Lab 04: Supervised Machine Learning — Linear & Logistic Regression

**Author:** Mohsin Raza  
**SAP ID:** 70177136  
**Email:** 70177136@student.uol.edu.pk  
**Institution:** The University of Lahore (UOL)  
**Course:** Introduction to Artificial Intelligence (AI-101L)  

---

## 📌 Overview
This repository contains the complete implementation and evaluation of **Laboratory 04**:
1. **Simple Linear Regression:** Univariate model for salary estimation based on work experience.
2. **Multiple Linear Regression:** Multivariate house pricing predictor ($7$ features) with residual error analysis.
3. **Logistic Regression:** Probabilistic binary diagnostic classifier for diabetes detection using clinical vitals.

---

## 📁 Repository Structure
```
Lab04_Linear_and_Logistic_Regression/
├── Simple_Linear_Regression.ipynb       # Univariate linear regression
├── Multi_Linear_Regression.ipynb        # Multivariate linear regression (bug-fixed)
├── Diabetes_Logistic_Regression.ipynb   # Logistic regression classification & ROC analysis
├── Salary_dataset.csv                   # Experience & salary data
├── house_price_regression_dataset.csv   # House attributes & valuation data
├── housing.csv                          # Auxiliary housing reference data
├── diabetes.csv                         # Pima Indians diabetes diagnostic dataset
├── report.md                            # Comprehensive laboratory report
├── requirements.txt                     # Python dependencies
└── README.md                            # Execution instructions
```

---

## 🚀 How to Run

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Launch Notebooks
Open any of the notebooks in Jupyter Lab, VS Code, or Google Colab:
```bash
jupyter notebook Simple_Linear_Regression.ipynb
jupyter notebook Multi_Linear_Regression.ipynb
jupyter notebook Diabetes_Logistic_Regression.ipynb
```
All notebooks use relative dataset paths and execute smoothly in any working directory.
