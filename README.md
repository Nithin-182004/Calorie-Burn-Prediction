# Calorie Burn Prediction Using XGBoost

This repository contains a complete pipeline to predict the number of calories burned during physical activity using machine learning. The project utilizes XGBoost, a powerful gradient boosting algorithm, to deliver accurate predictions based on user features and exercise parameters.

---

## 🔍 Project Overview

Predicting calories burned is valuable for fitness tracking, health monitoring, and personalized workout planning. This project addresses the challenge by building a regression model that estimates calories burned from a mix of demographic and activity-related data.

The dataset includes:
- Demographic features: Age, Gender, Height, Weight
- Activity features: Exercise duration, heart rate, steps, etc.
- Target variable: Calories burned

The goal is to train a robust model that generalizes well to unseen data.

---

## 🚀 Approach & Methodology

1. **Data Loading and Exploration**
   - Load training and test datasets.
   - Understand feature types and check for missing values.
   - Analyze distributions and relationships.

2. **Data Preprocessing**
   - Convert categorical variables (e.g., Gender) into numeric using Label Encoding.
   - Fill missing values using mean imputation.
   - Standardize numerical features with `StandardScaler` to normalize scales.

3. **Train-Validation Split**
   - Split training data into 80% training and 20% validation sets to evaluate model generalization.

4. **Model Training**
   - Use XGBoost Regressor configured with:
     - Objective: `reg:squaredlogerror` (optimizes RMSLE loss)
     - 100 trees (`n_estimators=100`)
     - Learning rate: 0.1
     - Max tree depth: 6
   - Train on training split.

5. **Evaluation**
   - Predict on validation data.
   - Clip negative predictions to zero (calories can’t be negative).
   - Calculate Root Mean Squared Log Error (RMSLE) to assess accuracy.

6. **Final Predictions**
   - Predict on test data.
   - Save predictions with IDs into `submission.csv` for competition submission.

---
