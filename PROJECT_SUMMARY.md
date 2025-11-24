# Project Summary: Regression Analysis on Medical Cost

This document summarizes the key decisions, assumptions, and findings for this regression analysis project.

## Problem Definition (Front Matter)

- Project Title: Final Project: Module 6 – Regression Analysis
- Author/Alias: Lindsay Foster
- Brief description: Healthcare insurers need to estimate individual medical insurance charges based on demographic and health-related factors. This project uses regression techniques to model insurance charges based on features like age, BMI, smoking status, sex, number of children, and region.
- What decision or action the model is intended to support: The model is intended to support decisions related to policy pricing, risk assessment, and resource allocation for clients with higher expected medical costs.
- Who would use this model: Actuaries, insurance analysts, and data science teams in healthcare or insurance companies.


## 1. Target Variable

- Target variable name: charges
- Type: Continuous Numeric
- Summary Statistics: 
  - **Count:** 1,338 records  
  - **Mean:** \$13,270.42  
  - **Median:** \$9,382.03  
  - **Standard deviation:** \$12,110.01  
  - **Minimum:** \$1,121.87  
  - **25th percentile:** \$4,740.29  
  - **75th percentile:** \$16,639.91  
  - **Maximum:** \$63,770.43 
- Missing Values: None
- Distribution: Right-skewed, some high-cost outliers


## 2. Costs of Errors

- What an error means: Difference between predicted and actual charges
- Consequences of overestimation: Policy may be priced too high, potentially losing customers
- Consequences of underestimation: Financial risk to insurer if actual costs exceed predictions
- Error prioritization: Minimize RMSE to reduce large errors, maintain balanced performance
- Rationale: RMSE penalizes larger errors more heavily, important for financial impact


## 3. Feature Review

- List of available features: age, sex, bmi, children, smoker, region, charges
- Interaction features: age_smoker, children_smoker, age_children
- Any restricted/disallowed features: charges cannot be used as input
- Possible target leakage: None
- Example of potential leakage: Including predicted_charges from other models in features


## 4. Evaluation Metrics

- Primary metric chosen: RMSE (Root Mean Squared Error)
- Why: Measures average magnitude of error in the same units as standardized charges
- Secondary metrics: R², MAE
- Brief discussion: Linear regression achieved R² ≈ 0.63, random forest R² ≈ 0.62, polynomial regression overfit and performed poorly
- Use of domain-specific metrics: Standardized metrics used for comparability; RMSE emphasizes large prediction errors


## 5. Baseline Performance

- Baseline: Predict the mean of charges for all observations
- Baseline RMSE: 1.030 (standardized)
- Minimum performance required: RMSE < 1.030 to outperform baseline
- Rationale: The model must provide meaningful predictive improvement over the naive mean prediction.
- Model Performance (After Training)
    - Model RMSE: 0.620
    - Model MAE: 0.367
    - Model R²: 0.633

- Comparison: The model significantly reduces prediction error compared to the baseline, providing more accurate and actionable estimates of medical charges


## 6. Data Splitting and Validation

- Method used: Train/test split (80% train / 20% test)
- Rationale: Standard approach to evaluate generalization to unseen data
- Is time order relevant: No
- Possible leakage risks: Including target or derived features in training
- Mitigation: Scaler fitted only on training set; interactions computed consistently


## 7. Real-World Impact

- Primary users: Actuaries and insurance analysts
- Action triggered: Adjust policy pricing or risk assessment for high-cost clients
- Consequences of overestimation: Policies priced too high, losing customers
- Consequences of underestimation: Financial risk to insurer
- Ethical concerns: Ensure fair pricing and no discrimination based on protected characteristics


## 8. Final Notes

- Key limitations: Linear model may not capture all nonlinear interactions; random forest improves accuracy but loses interpretability; high-cost outliers affect predictions.
- Future improvements: Test gradient boosting, XGBoost, hyperparameter tuning, log-transform charges to reduce skewness, incorporate additional features like pre-existing conditions.
- Open questions/assumptions: Assumes dataset is representative; features independent except for included interactions.