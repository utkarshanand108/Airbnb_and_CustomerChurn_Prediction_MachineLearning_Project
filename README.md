# DataScienceCourse6_Project
**Machine Learning Dual Project — Airbnb Price Prediction & Customer Churn Prediction**  
*Internshala Placement Guarantee Program | DS PGC Course 6 | Utkarsh Anand*

---

## 📘 Project Overview
This dual project applies **machine learning techniques in Python** to solve two real-world problems:
1. **Airbnb Price Prediction** — Regression model to estimate property listing prices.
2. **Customer Churn Prediction** — Classification model to predict whether customers will leave a telecom service.

Both projects follow a **structured data science workflow** — data preprocessing, feature engineering, model building, evaluation, visualization, and insights.

---

## 🧠 Project 1: Airbnb Price Prediction

### 🎯 Objective
Predict Airbnb listing prices based on property, room, amenities, and city-level attributes using regression analysis.

### 🧩 Steps Performed
#### 1️⃣ Data Exploration & Preprocessing
- Imported dataset (`Airbnb_data.xlsx`) — 74,111 rows, 29 columns → Cleaned to 51,545 rows.
- Dropped irrelevant columns (`thumbnail_url`, `first_review`, `last_review`, etc.).
- Removed missing values and irrelevant text fields.
- Encoded categorical features using one-hot encoding (`pd.get_dummies()`).
- Standardized numeric features with `StandardScaler()`.

#### 2️⃣ Model Development
- Algorithm used: **Linear Regression (Scikit-learn)**
- Train-test split: 80–20 ratio
- Features: 50, Target: `log_price`

#### 3️⃣ Model Evaluation
| Metric | Value |
|:--------|:--------|
| RMSE | 0.418 |
| MAE | 0.322 |
| R² Score | 0.598 |

**Visualization:** Bar chart comparing RMSE, MAE, and R².

#### 4️⃣ Key Insights
- `Entire home/apt` and `Apartment` listings are priced highest.
- Number of bedrooms, beds, and accommodates strongly influence price.
- High correlation between amenities count and `log_price`.

---

## 🧮 Example Code
```python
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

model = LinearRegression()
model.fit(X_train_scaled, y_train)
y_pred = model.predict(X_test_scaled)

print("RMSE:", round(np.sqrt(mean_squared_error(y_test, y_pred)), 3))
print("MAE:", round(mean_absolute_error(y_test, y_pred), 3))
print("R² Score:", round(r2_score(y_test, y_pred), 3))
```

---

## 📊 Project 2: Customer Churn Prediction

### 🎯 Objective
Predict which customers are likely to churn based on demographic and service-related attributes using classification algorithms.

### 🧩 Steps Performed
#### 1️⃣ Data Exploration & Cleaning
- Loaded `Customer_data.xlsx` — 7,043 rows, 21 columns.
- Dropped customer ID, handled 11 null `TotalCharges` entries.
- One-hot encoded all categorical columns.
- Final dataset shape: (7032, 31).

#### 2️⃣ Model Building
- **Logistic Regression** — baseline model
- **Decision Tree Classifier** — comparison model

#### 3️⃣ Model Evaluation
| Metric | Logistic Regression | Decision Tree |
|:--------|:--------------------|:----------------|
| Accuracy | 0.787 | 0.725 |
| AUC | 0.832 | 0.662 |
| F1 Score | 0.781 | 0.728 |

#### 4️⃣ Visualization
- Confusion Matrix heatmap (`seaborn.heatmap`)  
- ROC Curve with AUC comparison

#### 5️⃣ Key Insights
- Logistic Regression outperforms Decision Tree.
- Tenure, Contract Type, and Monthly Charges are major churn indicators.
- Customers on **month-to-month contracts** are most likely to churn.
- High-value insight: longer-tenure customers show strong loyalty patterns.

---

## 🧰 Tools & Technologies
| Category | Tools |
|:----------|:-------|
| Programming | Python 3 |
| IDE | Jupyter Notebook / Google Colab |
| Libraries | `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`, `scipy` |
| Techniques | Regression, Classification, Feature Encoding, Scaling, Evaluation Metrics |

---

## 📂 Files Included
```
DataScienceCourse6ProjectProblemStatement.pdf   # Project Instructions (Airbnb + Churn)
Airbnb_Price_Prediction.ipynb                   # Notebook (Airbnb)
Airbnb_Price_Prediction.py                      # Script (Airbnb)
Airbnb_Price_Prediction.ipynb - Colab.pdf       # Notebook PDF Export
CustomerChurnPrediction.ipynb                   # Notebook (Churn)
CustomerChurnPrediction.py                      # Script (Churn)
Copy of CustomerChurnPrediction.ipynb - Colab.pdf # PDF Report
```

---

## 🧭 How to Review
1. View `.ipynb` files in GitHub for live-rendered code + outputs.  
2. Open `.py` files for clean Python scripts.  
3. Open `.pdf` versions for formatted reports.  
4. Each project folder includes **Google Drive links** for video presentations.

---

## 🏁 Results Summary
| Project | Type | Algorithm(s) | Accuracy / R² | Highlights |
|:---------|:------|:---------------|:----------------|:-------------|
| Airbnb Price Prediction | Regression | Linear Regression | R² = 0.598 | Price drivers: room type, amenities, bedrooms |
| Customer Churn Prediction | Classification | Logistic Regression, Decision Tree | 78.7% accuracy | Logistic Regression best performer |

---

## 👤 Author
**Utkarsh Anand**  
DS PGC Course 6 — Final Project  
Internshala Placement Guarantee Program  
GitHub Portfolio: *(link after all repos are uploaded)*  
Google Drive Presentation: *(link inside notebook)*  
Date: November 2025
