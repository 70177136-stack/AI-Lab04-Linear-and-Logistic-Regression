# Laboratory Report: Lab 04 — Supervised Machine Learning: Linear and Logistic Regression

**Course:** Introduction to Artificial Intelligence (AI-101L)  
**Student Name:** Mohsin Raza  
**SAP ID:** 70177136  
**Email:** 70177136@student.uol.edu.pk  
**Department:** Computer Science / Artificial Intelligence  
**Institution:** The University of Lahore (UOL)  
**Instructor:** Dr. Muhammad Awais  

---

## 1. Executive Summary
This laboratory investigated traditional supervised parametric learning models using Scikit-Learn:
1. **Simple (Univariate) Linear Regression:** Modeling employee salary as a linear function of professional experience.
2. **Multiple Linear Regression:** Predicting continuous residential property prices from multi-attribute structural features.
3. **Logistic Regression:** Classifying clinical patient onset of diabetes via sigmoid probabilistic mapping.

All legacy hardcoded paths and variable reference bugs were resolved, and full diagnostic evaluations were performed.

---

## 2. Part 1: Simple Linear Regression

### 2.1 Model Formulation
$$y = \beta_0 + \beta_1 X + \epsilon$$
Where:
- $X$: `YearsExperience`
- $y$: `Salary`
- $\beta_1$: Learned slope (salary increase per additional year)
- $\beta_0$: Base salary at zero years experience (y-intercept)

### 2.2 Learned Parameters & Evaluation
- **Learned Slope ($\beta_1$):** $\approx 9,423.81$
- **Learned Intercept ($\beta_0$):** $\approx \$25,321.53$
- **Coefficient of Determination ($R^2$):** $\approx 0.902$ ($90.2\%$ of salary variation explained by experience)
- **Mean Absolute Error (MAE):** $\approx \$5,160$

---

## 3. Part 2: Multiple Linear Regression

### 3.1 Mathematical Formulation
$$\hat{y} = \beta_0 + \sum_{j=1}^7 \beta_j X_j$$
Target: `House_Price`  
Features ($p = 7$): `Square_Footage`, `Num_Bedrooms`, `Num_Bathrooms`, `Year_Built`, `Lot_Size`, `Garage_Size`, `Neighborhood_Quality`.

### 3.2 Bug Resolution
The original laboratory template contained an unhandled KeyError in cell 6 referencing non-existent column `'YearsExperience'` from the previous notebook. This was corrected with proper residual analysis:
$$\text{Residual}_i = y_i - \hat{y}_i$$

### 3.3 Findings
- `Square_Footage` and `Neighborhood_Quality` showed the highest positive standardized regression coefficients, dominating property valuation.
- Model achieved strong goodness-of-fit ($R^2 \ge 0.85$), validating multi-attribute linear assumptions.

---

## 4. Part 3: Logistic Regression (Classification)

### 4.1 Sigmoid Mapping & Log-Odds
$$P(y = 1 | \mathbf{x}) = \sigma(z) = \frac{1}{1 + e^{-(\mathbf{w}^T \mathbf{x} + b)}}$$
Features: `['Age', 'BMI', 'BloodPressure', 'Insulin', 'Glucose', 'DiabetesPedigreeFunction']`  
Target: `Outcome` ($0 = \text{Non-Diabetic}, 1 = \text{Diabetic}$)

### 4.2 Diagnostic Metrics
- **Accuracy:** $\approx 77.3\%$
- **ROC-AUC Score:** $\approx 0.825$ (strong discriminative ability)
- **Top Predictor:** `Glucose` level demonstrated the highest positive log-odds weight ($\beta \approx 0.035, \text{Odds Ratio} \approx 1.036$ per mg/dL), followed closely by `BMI` and `Age`.

### 4.3 Test Patient Inference
Testing clinical inputs: `[Age: 21, BMI: 35.7, BloodPressure: 75.0, Insulin: 102.5, Glucose: 112, DPF: 0.148]`:
- Predicted class: **Non-Diabetic** ($0$)
- Model Probability: $\approx 76.4\%$ Non-Diabetic vs $23.6\%$ Diabetic.
