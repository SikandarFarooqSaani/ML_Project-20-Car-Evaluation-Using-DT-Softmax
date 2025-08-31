# 🚗 Car Evaluation Classification Project  

![Car Logo](https://img.icons8.com/emoji/96/automobile.png)  

---

## 📌 Project Overview  
This project focuses on **classifying cars into 4 categories** (`unacc`, `acc`, `good`, `v-good`) using **Decision Tree Classifier**.  
We explored **GridSearchCV** and **RandomizedSearchCV** for hyperparameter tuning to improve accuracy and efficiency.  

---

## 🛠️ Tools & Libraries Used  

| Logo | Library | Purpose |
|------|---------|---------|
| 🐍 | **OS** | File handling |
| ![Kaggle](https://upload.wikimedia.org/wikipedia/commons/7/7c/Kaggle_logo.png) | **KaggleHub** | Direct dataset import |
| ![NumPy](https://upload.wikimedia.org/wikipedia/commons/3/31/NumPy_logo_2020.svg) | **NumPy** | Numerical operations |
| ![Pandas](https://upload.wikimedia.org/wikipedia/commons/e/ed/Pandas_logo.svg) | **Pandas** | Data manipulation |
| 🌳 | **DecisionTreeClassifier** | ML model for classification |
| 📏 | **Accuracy Metrics** | Model evaluation |
| ![Matplotlib](https://upload.wikimedia.org/wikipedia/commons/8/84/Matplotlib_icon.svg) | **Matplotlib (pyplot)** | Visualizations |
| ![Seaborn](https://seaborn.pydata.org/_images/logo-mark-lightbg.svg) | **Seaborn** | Heatmaps, plots |

---

## 📂 Dataset  

📌 **Source:** [Car Evaluation Dataset](https://www.kaggle.com/datasets/elikplim/car-evaluation-data-set)  

- **Shape:** `(1727, 7)`  
- **Target Classes:**  
  - `unacc`: **1210 (70.02%)**  
  - `acc`: **384 (22.22%)**  
  - `good`: **69 (3.99%)**  
  - `v-good`: **65 (3.76%)**  
- **Data Cleaning:**  
  - Some columns had `object` datatypes → converted to categorical (numeric mapping).  
  - No duplicates found.  

---

## ⚙️ Workflow  

1. Import dataset with **KaggleHub**.  
2. Checked and converted object types into categories.  
3. Verified no duplicates.  
4. Final dataset shape: **(1727, 7)**.  
5. Train-test split.  
6. Fitted **Decision Tree Classifier**.  

---

## 🔍 Model Experiments & Results  

### 📌 Decision Tree (Default)  
- Accuracy: **0.97**  
- Confusion Matrix:  
  <img width="649" height="547" alt="20-1" src="https://github.com/user-attachments/assets/f9b2ba16-a607-4d74-beac-6f23be2affd2" />
 

---

### 📌 GridSearchCV  
- Parameters tested:  
```python
param_grid = {
    'criterion':['gini','entropy'],
    'splitter':['best','random'],
    'max_depth':[2,4,8,10,13,None],
    'max_features':['sqrt','log2',None],
    'min_samples_leaf':[1,2,3,4,5],
}
### 📌 GridSearchCV
{'criterion': 'entropy',
 'splitter': 'best',
 'max_depth': 10,
 'max_features': None,
 'min_samples_leaf': 1}
## 📌 RandomizedSearchCV  

- Parameters tested with **n_iter=10**  
- **Best Score:** 0.9514  
- **Advantage:** Much faster than GridSearchCV.  

---

## 📊 Feature Importance  

Extracted **feature importance** from Decision Tree → showed which car features impact classification the most.  

---

## 🚀 Conclusion  

- Decision Tree performed very well (**97% accuracy**).  
- GridSearchCV helped find the **best hyperparameters (96% accuracy)**.  
- RandomizedSearchCV was **faster** but gave slightly lower accuracy (**95.14%**).  
- Learned how tuning methods improve models and how **time vs. accuracy trade-off** works.  

---

## 💡 Future Improvements  

- Try **Random Forest** and **XGBoost**.  
- Apply **cross-validation** for robust results.  
- Visualize **Decision Tree graph** for interpretability.  

---

## 👨‍💻 Author  

Made with ❤️ by **Sikandar Farooq Saani**  


