# 🎯 CS:GO Round Winner Prediction

## 📌 Overview
This project builds a machine learning pipeline to **predict Counter-Strike: Global Offensive (CS:GO) round winners** — either **Counter-Terrorists (CT)** or **Terrorists (T)** — using in-game round-level data such as:
- Player health and armor
- Team economy and equipment
- Map information
- Number of players alive
- Weapons and grenades held
- Bomb status

The notebook explores **data preprocessing**, **exploratory data analysis (EDA)**, **statistical tests**, **model training**, and **model evaluation** using multiple machine learning algorithms.

---

## 📊 Dataset
- **Source:** [OpenML](https://www.openml.org/) – CS:GO rounds dataset  
- **Size:** ~122,000 rounds  
- **Features:** 97+ columns including numerical, categorical, and binary weapon/utility indicators  
- **Target:** `round_winner` (CT or T)

---

## 🧪 Methodology

1. **Data Loading & Cleaning**
   - Imported raw `.arff`-style dataset from OpenML
   - Converted to pandas DataFrame
   - Handled categorical encoding for `map`
   - Removed non-informative features

2. **EDA & Statistical Insights**
   - Win rate analysis for CT vs T overall and by map  
   - Chi-square tests for association between map and winner  
   - Binomial tests for overall win rate balance  

3. **Feature Engineering**
   - One-hot encoding of map names
   - Retained key numerical features (economy, health, alive count)
   - Engineered binary weapon/grenade flags

4. **Model Training**
   - Logistic Regression (baseline)
   - k-Nearest Neighbors (tuned via RandomizedSearchCV)
   - Random Forest Classifier (baseline & tuned)
   - Evaluated using:
     - Accuracy
     - Confusion Matrix
     - KS statistic & Gini coefficient
     - ROC Curve

5. **Model Selection**
   - KNN improved from **80.8% → 83.2%**
   - Random Forest achieved **86.6%**, highest among tested models
   - Feature importance shows armor, money, kits, and health as top predictors

---

## 📈 Results

| Model                  | Accuracy | Notes |
|------------------------|----------|-------|
| Logistic Regression    | ~78%     | Fast baseline, interpretable |
| KNN (tuned)            | ~83.2%   | Lower error rates than baseline |
| Random Forest (tuned)  | **86.6%**| Best accuracy, balanced predictions |

**Key Findings:**
- Team T won slightly more (~51%) than CT (~49%), statistically significant.
- Map choice influences win probability (Chi-square test p ≪ 0.05).
- Top features: `t_armor`, `ct_armor`, `t_money`, `ct_money`, and `ct_defuse_kits`.

---

## 🚀 Future Work
- **Real-time prediction** by integrating with live CS:GO match data feeds
- **Advanced models** like XGBoost, LightGBM, CatBoost
- **Hyperparameter tuning** for Random Forest and boosting models
- **Explainability** with SHAP values and feature visualizations
- **Dashboard/Visualization** for analysts and spectators
- **API deployment** for live match integrations

---

## 📂 Repository Structure
