

---

#  Heart Disease Prediction using Decision Trees

##  Project Overview
This project applies **Decision Tree Classifiers** to the UCI Heart Disease dataset.  
The goal is to understand how tree depth and parameters affect model performance, and to visualize the decision rules for medical interpretability.

---

##  Dataset
- **Source:** UCI Heart Disease dataset (`heart.csv`)  
- **Features:**  
  - age, sex, cp (chest pain type), trestbps (resting blood pressure), chol (cholesterol), fbs (fasting blood sugar), restecg (ECG results), thalach (max heart rate), exang (exercise-induced angina), oldpeak (ST depression), slope, ca (major vessels), thal (thalassemia)  
- **Target:**  
  - `0` → No Disease  
  - `1` → Disease  

---

##  Experiments
We trained three models by varying **max_depth**:
- **Model 1:** max_depth = 2 → Underfits (low accuracy)  
- **Model 2:** max_depth = 5 → Best balance (good generalization)  
- **Model 3:** max_depth = None → Overfits (perfect training accuracy, poor test accuracy)  

We also compared:
- **Criterion:** `gini` vs. `entropy` → Similar accuracy, Gini faster.  
- **min_samples_leaf:** Larger values reduce overfitting but may underfit if too high.  

---

##  Results (Typical Ranges)
| Model | max_depth | Training Accuracy | Testing Accuracy | Notes |
|-------|-----------|-------------------|------------------|-------|
| 1     | 2         | ~70–75%           | ~68–72%          | Underfitting |
| 2     | 5         | ~85–90%           | ~78–82%          | Best balance |
| 3     | None      | ~100%             | ~65–70%          | Overfitting |

---

##  Visualization
We plotted the **Decision Tree (max_depth=5)** with:
- **Feature names** for interpretability  
- **Class names:** `No Disease`, `Disease`  

This helps clinicians and data scientists see the rules (e.g., *if cp ≤ 1 and ca = 0 → Disease*).

---

##  Conclusion
- **Shallow trees** → Too simple, miss patterns.  
- **Deep trees** → Memorize training data, fail on new patients.  
- **Balanced trees (depth ~5, min_samples_leaf ~5)** → Best performance and interpretability.  
- **Decision Trees** are suitable for medical datasets because they are **transparent, easy to interpret, and form the basis of ensemble methods** like Random Forests and XGBoost.  
