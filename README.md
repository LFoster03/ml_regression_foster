# Final Project: Module 6 – Regression Analysis
**Name:** Lindsay Foster 
**Date:** 11/23/2025

## Introduction
This project uses regression analysis to explore how different factors influence a target outcome. Using the Medical Cost dataset, the goal is to build and evaluate models that predict insurance charges based on features like age, BMI, and smoking status. The project includes data exploration, feature selection, model training, and comparison of regression methods.

# Steps

- Create the virtual environment

- Use Python’s built-in venv module: python -m venv .venv. .venv is the folder where your virtual environment will be stored.After this, your project folder will have a .venv directory.Tip: Use lowercase .venv (or venv) for convention. VS Code automatically recognizes .venv.

- Activate the virtual environment: .venv\Scripts\Activate. A requirements.txt lists all the Python packages your project needs so others (or you in a new environment) can install them easily with pip install -r requirements.txt.

- How to use it - Save this file as requirements.txt in your project folder. Make sure your virtual environment is activated (.venv). Install all packages with: pip install -r requirements.txt. Select .venv as the kernel. Tell VS Code to use this .venv interpreter. Press Ctrl+Shift+P → type Python: Select Interpreter. Look for the interpreter in your .venv, e.g.:C:\Repos\project02\.venv\Scripts\python.exe. Select it. Reload VS Code to make sure it takes effect. This makes your editor aware of all packages installed in .venv.
- 1️⃣ Upgrade pip, setuptools, and wheel

First, make sure pip can find prebuilt wheels:

python -m pip install --upgrade pip setuptools wheel

2️⃣ Install numpy and pandas separately

Instead of installing everything from requirements.txt (which may force old versions), install the main dependencies directly as prebuilt wheels:

pip install numpy pandas


This avoids building from source, which fails on Windows if you don’t have Visual Studio C++ installed.

3️⃣ (Optional) Install other requirements

If your requirements.txt has other packages, you can now try:

pip install -r requirements.txt


or comment out pandas==2.2.0 first, since you already installed it.

- CSV file into data folder
  - Medical Costs Dataset (Predict insurance charges based on age, BMI, smoking status)  
   - [Medical Cost Dataset](https://www.kaggle.com/mirichoi0218/insurance)

## Project Steps
1. Import and Inspect the Data
2. Data Exploration and Preparation
3. Feature Selection and Justification
4. Train a Model (Linear Regression)
5. Improve the Model or Try Alternates (Implement Pipelines)
6. Final Thoughts & Insights
7. Peer Review

## Section 1: Import and Inspect the Data

Load the dataset from data/insurance.csv and display the first few rows.

Check for missing values and summary statistics.

Initial inspection revealed no missing values and identified the distribution of numerical and categorical features.

## Section 2: Data Exploration and Preparation

Explored data patterns and distributions using histograms, boxplots, and count plots.

Observed that smokers had higher charges, and BMI and age were moderately correlated with charges.

Handled missing values (none in this dataset).

Created BMI categories (underweight, normal, overweight, obese) and encoded categorical variables using one-hot encoding.

Scaled numeric features (age, BMI, children, charges) for consistency, though linear regression is scale-invariant.

Outliers were noted in charges, but no extreme transformations were applied.

## Section 3: Feature Selection and Justification

Features (X): age, BMI, children, sex, smoker, region (encoded as numeric).

Target (y): charges.

Justification:

Smoker status, BMI, and age strongly affect charges.

Sex, children, and region may add incremental predictive power.

Feature matrix and target shapes:

X shape: (1191, 8)
y shape: (1191,)

## Section 4: Train and Evaluate Models

Split data into training and test sets using train_test_split.

Trained a linear regression model on the training set.

Evaluation metrics:

Regression: R², MAE, RMSE

Observed residuals and outliers using predicted vs actual plots.

Results showed good predictive performance with residuals mostly close to zero, except for a few outliers.

## Section 5: Improve the Model or Try Alternates (Pipelines)

Pipeline 1: Imputer → StandardScaler → Linear Regression.

Pipeline 2: Imputer → Polynomial Features (degree=3) → StandardScaler → Linear Regression.

Findings:

Pipeline 1 performed the same as the original model — scaling did not change linear regression predictions.

Pipeline 2 overfit: higher MAE/RMSE and lower R² due to polynomial features capturing noise.

Comparison Table:

Pipeline	MAE	RMSE	R²
Linear Regression (original)	0.445	0.692	0.544
Pipeline 1	0.445	0.692	0.544
Pipeline 2 (Polynomial)	0.514	0.766	0.440

Visualizations: Bar charts comparing metrics and predicted vs actual plots confirmed Pipeline 2 overfit.

## Section 6: Final Thoughts & Insights

Key findings:

Smoker status, BMI, and age are the strongest predictors.

Simple linear models captured trends effectively.

More complex polynomial models can overfit small datasets.

Challenges: Handling outliers, understanding scaling, and encoding categorical variables.

Next steps:

Test regularized regression (Ridge/Lasso).

Explore non-linear models (Random Forest, Gradient Boosting).

Create interaction features (e.g., BMI × smoker status).

Apply robust scaling or feature transformations for skewed data.

Analyze feature importance for model explainability.