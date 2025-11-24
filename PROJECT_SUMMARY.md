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
- Two class values:
- Values are mutually exclusive and collectively exhaustive (yes/no):
- Any unexpected or missing class values identified:


## 2. Positive Class Definition

- Positive class (label = 1):
- Rationale for choosing this class:
- How this affects interpretation of precision, recall, and related metrics:


## 3. Class Distribution

- Percentage of positive class:
- Percentage of negative class:
- Is the dataset imbalanced (yes/no):
- If imbalanced, implications for modeling or evaluation:


## 4. Costs of Errors

- What a true positive means in this application:
- What a false positive means:
- What a false negative means:
- Which error is worse for this problem and why:
- Whether the model should prioritize sensitivity, specificity, or a balanced tradeoff:
- Rationale for this prioritization:


## 5. Decision Threshold

- Is the default threshold of 0.5 appropriate (yes/no):
- Why or why not:
- Proposed threshold:
- Rationale for chosen threshold:
- Should the threshold be optimized for precision, recall, cost, or other factors:
- Who determines acceptable tradeoffs (stakeholders, domain experts, policy):


## 6. Feature Review

- List of available features:
- Any restricted or disallowed features:
- Possible sources of target leakage:
- Example of potential leakage in this scenario:
- How time-dependent features were handled:
- Any features occurring after the true outcome and how they were treated:


## 7. Evaluation Metrics

- Primary metric chosen:
- Why this metric is appropriate:
- Secondary metrics reported:
- Brief discussion of these metrics:
- Use of ROC-AUC, PR-AUC, F1, or other domain-specific metrics:
- Brief explanation:


## 8. Baseline Performance

- Majority-class accuracy:
- How majority-class accuracy was calculated:
- Random-guess accuracy:
- How random-guess accuracy was calculated:
- Minimum performance required for the model to be useful:
- Rationale for this threshold:

## 9. Data Splitting and Validation

- Method used (train/test split or cross-validation):
- Rationale for chosen method:
- Is time order relevant (yes/no):
- If yes, how time-based splitting was handled:
- Possible leakage risks across splits (duplicates, identifiers, out-of-order events):
- How these risks were mitigated:


## 10. Real-World Impact

- Primary users or decision-makers for this model:
- Action triggered by a positive prediction:
- Consequences of false positives:
- Consequences of false negatives:
- Potential impact on people, decisions, or systems:
- Any ethical concerns or additional safeguards:


## 11. Final Notes

- Key limitations:
- Future improvements:
- Any open questions or assumptions: