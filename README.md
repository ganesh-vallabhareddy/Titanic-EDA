# Titanic Survival Prediction - Detailed Analysis

## Overview
My aim here is to analyze the Titanic dataset and build a predictive model to determine survival probabilities. The entire process includes data preprocessing, exploratory data analysis (EDA), machine learning model training, and optimization.

## Step-by-Step Process

### 1. Introduction
- The Titanic disaster occurred on April 15, 1912, where 2,224 passengers were onboard, and only 722 survived.
- Factors such as age, gender, class, and ticket fare influenced survival.
- The goal is to analyze these factors and build a model to predict survival chances.

### 2. Data Preprocessing
#### Handling Missing Values
- **Age**: Replaced missing values with the median to avoid extreme values.
- **Embarked**: Filled missing values with the most common value (mode).
- **Cabin**: Dropped because 77% of values were missing.

#### Identifying Outliers
- Used boxplots to detect extreme values.
- **Capped Values:**
  - Age limited to 60.
  - SibSp capped at 3.
  - Parch capped at 3.
  - Applied log transformation on Fare to manage extreme values.

### 3. Exploratory Data Analysis (EDA)
#### Survival Analysis by Passenger Class
- **1st Class:** 62.9% survived.
- **2nd Class:** 47.3% survived.
- **3rd Class:** 24.2% survived.
- Conclusion: Higher-class passengers had a better survival chance.

#### Correlation Analysis
- **Pclass & Fare (-0.66):** Higher-class passengers paid more.
- **Pclass & Survived (-0.34):** Higher-class passengers had a better survival rate.
- **Fare & Survived (0.33):** Higher fares correlated with higher survival chances.
- **SibSp & Parch (0.46):** Passengers with family had different survival rates.

### 4. Model Training
- Used **Random Forest Classifier** as the base model.
- Split the dataset into **training (80%)** and **testing (20%)**.
- Built a pipeline for preprocessing and model training.

#### Performance Evaluation
- **Accuracy:** 81.56% before tuning.
- **ROC AUC Score:** 0.8920.
- **Classification Report:** Measured Precision, Recall, and F1-score.
- **Confusion Matrix:** Analyzed misclassified predictions.

### 5. Model Optimization
- Performed **Hyperparameter Tuning** using GridSearchCV.
- Tuned parameters:
  - Number of trees (n_estimators)
  - Max depth
  - Minimum samples per split and leaf
- Achieved **Final Accuracy: 83.80%** (improved from 81.56%).
- Final **ROC AUC Score: 0.8981** (better class separation).

### 6. Execution Performance Enhancements
- Used **pipelines** for efficient preprocessing and model training.
- **Hyperparameter tuning** improved accuracy.
- Identified **feature importance:**
  - **Most influential:** Sex, Fare, Pclass.
  - **Less influential:** Embarked location.
- Saved the final trained model using **Joblib**.

### 7. Conclusion
- The project successfully identified survival patterns.
- Higher-class passengers, females, and those who paid higher fares had a better chance of survival.
- The optimized Random Forest model predicts survival with improved accuracy.
- The final trained model can be used for further Titanic-related research or similar classification problems.

