# Final Project: Module 6 – Regression Analysis
**Name:** Lindsay Foster 
**Date:** 11/23/2025

## Introduction

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