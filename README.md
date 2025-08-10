# CS:GO Round Winner Prediction – Machine Learning Notebook

## 📌 Project Overview
This project builds and evaluates machine learning models to **predict the winner of a Counter‑Strike: Global Offensive (CS:GO) round** based on round‑level match data.  
It covers the full data science workflow:

1. **Downloading** the dataset from [OpenML](https://www.openml.org/)
2. **Parsing** `.arff` format and converting it to CSV
3. **Exploring** and preprocessing data
4. **Feature engineering** (One‑Hot Encoding for categorical data)
5. **Training and evaluating** multiple ML models:
   - Logistic Regression (baseline linear model)
   - K‑Nearest Neighbors (with hyperparameter tuning)
   - Random Forest Classifier
6. **Comparing model performance**
7. **Saving the best model** for future use

---

## 📂 Dataset
- **Source:** [OpenML Dataset – CS:GO Round Win Prediction](https://www.openml.org/d/???)
- **Format:** `.arff` (Attribute‑Relation File Format)
- **Target Variable:** `round_winner` – `"CT"` (Counter‑Terrorists) or `"T"` (Terrorists)
- **Key Features:**
  - Match metadata (`map`, round number, team scores)
  - Economy info (team money, equipment value)
  - Player stats (alive players, kills, etc.)

---

## ⚙️ Workflow / Notebook Sections
1. **Install & Import Dependencies**  
2. **Download Dataset**  
3. **Parse ARFF to CSV**  
4. **Load & Explore Data (EDA)**  
5. **Preprocessing** (One‑Hot Encoding)  
6. **Feature/Target Split**  
7. **Train–Test Split**  
8. **Model Training & Evaluation**  
   - Logistic Regression  
   - KNN + RandomizedSearchCV  
   - Random Forest  
9. **Save Best Model**  
10. **Summary & Next Steps**

---

## 📊 Model Performance (Actual Results)

| Model                  | Test Accuracy |
|------------------------|---------------|
| Logistic Regression    | **0.7410**    |
| Best KNN               | **0.8065**    |
| Random Forest          | **0.8602**    |

---

## 🚀 How to Run
1. Clone the repo & open the notebook:
