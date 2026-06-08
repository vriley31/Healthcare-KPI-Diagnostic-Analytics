# Hospital-Length-of-Stay-Regression-Model

This project uses a Predictive Hospital Analytics dataset to develop a Multiple Linear Regression model that predicts patient Length of Stay (LOS). The objective is to identify patient, clinical, and operational factors that influence hospital stay duration and provide data-driven insights that support capacity planning, resource allocation, and discharge management.

## Project Objective

The goal of this project is to determine whether hospital length of stay can be predicted using demographic, clinical, and operational variables. By understanding the factors associated with extended stays, healthcare leaders can proactively improve patient flow, optimize staffing, and reduce unnecessary healthcare costs.

## Business Problem

Length of Stay (LOS) is a critical healthcare KPI that directly impacts:

- Bed occupancy rates
- Hospital throughput
- Staffing requirements
- Resource utilization
- Cost per patient encounter
- Discharge planning efficiency

This project applies predictive analytics to determine whether LOS can be estimated using available patient and hospital data.

---

## Key Steps

1. Imported and explored the Predictive Hospital Analytics dataset.
2. Audited the dataset for missing values, duplicates, and data quality issues.
3. Identified Length of Stay (LOS) as the target variable.
4. Selected predictor variables based on clinical and operational relevance.
5. Performed exploratory data analysis and descriptive statistics.
6. Encoded categorical variables using one-hot encoding.
7. Split the dataset into training and testing datasets.
8. Built a Multiple Linear Regression (OLS) model using Statsmodels.
9. Evaluated model performance using R², RMSE, and MAE.
10. Created diagnostic plots to assess model assumptions.
11. Interpreted coefficients and predictor significance.
12. Developed recommendations for healthcare leadership.

---

## Variables Used

### Target Variable
- LengthOfStay

### Predictor Variables
- Age
- ComorbiditiesCount
- AdmissionType
- DRGSeverityLevel
- DischargeDisposition
- DRGCode
- HospitalID

---

## Tools & Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-Learn

---

## Model Selection

A Multiple Linear Regression model was selected because Length of Stay is a continuous variable. The model estimates the relationship between LOS and multiple patient and operational characteristics simultaneously.

### Model Evaluation Metrics

- R² Score
- Adjusted R²
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Residual Analysis

---

## Key Findings

### Operational Insights

- Length of Stay can be partially predicted using existing hospital administrative and clinical data.
- Discharge disposition appears to have a stronger impact on LOS than demographic variables.
- Hospital-level differences contribute to LOS variation but were not statistically significant.
- The model is more effective for identifying high-risk patients than predicting exact LOS values.

### Business Value

Predicting LOS allows hospitals to:

- Improve bed management
- Optimize staffing schedules
- Enhance discharge planning
- Reduce bottlenecks in patient flow
- Improve resource utilization
- Support data-driven operational decisions

---

## Project Screenshots

### Length of Stay Distribution

```markdown
![Length of Stay Distribution](images/los_distribution.png)
```

### Residuals vs Fitted Values

```markdown
![Residuals vs Fitted Values](images/residuals_vs_fitted.png)
```

### Actual vs Predicted LOS

```markdown
![Actual vs Predicted LOS](images/actual_vs_predicted.png)
```

### OLS Regression Results

```markdown
![OLS Regression Summary](images/ols_regression_results.png)
```

---

## Sample Code

```python
predictors = [
    "Age",
    "ComorbiditiesCount",
    "AdmissionType",
    "DRGSeverityLevel",
    "DischargeDisposition",
    "DRGCode",
    "HospitalID"
]

df_model = df[[target] + predictors].dropna()
print("Model dataset shape:", df_model.shape)


import statsmodels.api as sm

X_train_sm = sm.add_constant(X_train)
X_test_sm = sm.add_constant(X_test)

model = sm.OLS(y_train, X_train_sm).fit()

print(model.summary())
```

---

## Future Improvements

Potential enhancements to improve predictive accuracy include:

- Incorporating laboratory results
- Including procedure and diagnosis data
- Adding ICU utilization indicators
- Integrating social determinants of health
- Testing advanced machine learning models such as:
  - Random Forest Regression
  - Gradient Boosting
  - XGBoost
  - Neural Networks

---

## References

Bruce, P. C., & Gedeck, P. (2020). *Practical Statistics for Data Scientists: 50+ Essential Concepts Using R and Python* (2nd ed.). O'Reilly Media.

Utterback, C. (2021). *Multiple Linear Regression Python 101*. Towards Data Science.

Van De Steeg, L., & Wagner, C. (2014). *Can Preventable Adverse Events Be Predicted Among Hospitalized Older Patients? The Development and Validation of a Predictive Model*. International Journal for Quality in Health Care, 26(5), 547–555.

---

## Author

**Victoria Riley**

Graduate Student | Data Analytics & Predictive Modeling

GitHub: [@vriley31](https://github.com/vriley31)

---
⭐ If you found this project interesting, consider giving it a star!
