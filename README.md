# 🏡 Bengaluru House Price Predictor

This project aims to predict **real estate prices** in **Bengaluru** using **machine learning** and **data analysis**. We explored and modeled the relationship between price, location, number of bedrooms, area type, and more — to help **buyers, sellers, and investors** make smarter, data-driven decisions.

---

## 🎯 Problem Statement

Buying or selling a house in Bengaluru is complicated due to high price variance across neighborhoods. There’s **no clear benchmark** for what a property *should* cost — making it easy to overpay or underprice.

> This project provides a solution: a machine learning model trained on real data that predicts **fair property prices**. It supports more **confident, transparent, and data-backed decisions** in the real estate market.

---

## 📊 Exploratory Data Analysis (EDA)

We performed detailed EDA to establish key relationships:

- **Location vs Price**: Properties in premium areas like Indira Nagar and HSR Layout tend to be priced significantly higher.
- **BHK vs Price**: While more BHKs usually cost more, the relationship is not always linear.
- **Area Type**: Properties in built-up and super-built-up areas command higher prices than plots.
- **Bathroom Count**: Surprisingly, the number of bathrooms showed **strong correlation** with price, sometimes more than location.

> These insights helped in **feature selection** and gave us a clearer understanding of the Bengaluru housing market.

---

## 🧹 Outlier Removal Using IQR Method

To ensure reliability, we removed extreme outliers using the **Interquartile Range (IQR)** method — a standard statistical approach that filters values lying far outside the typical range.

> This step improved model performance by ensuring we learn from genuine, consistent data rather than rare anomalies.

---

## 🛠️ Feature Engineering Highlights

### 🧲 Creating `balcony_count` from BHK

We engineered a new feature assuming that **higher BHKs tend to have more balconies**, helping the model capture subtle patterns in housing features.

### 🎯 Target Encoding of Categorical Features

To convert non-numeric features like `location` and `area_type`, we used **Target Encoding**. It replaces categories with their average house prices from the training data — helping the model understand the influence of each category.

> For example, instead of just knowing a house is in “Whitefield,” the model understands that houses in Whitefield *tend to cost X lakhs*.

---

## 📈 Model Comparison & Results

We trained and compared multiple machine learning models:

| Model                     | MAE   | R² Score |
|---------------------------|-------|------------|
| 🎯 Random Forest          | 15.07 | 0.71       |
| 🌱 Gradient Boosting     | 15.14 | 0.71       |
| 📊 Linear Regression      | 17.72 | 0.64       |
| 📉 Support Vector Regressor | 16.37 | 0.63       |

> **Random Forest** was the top-performing model with a strong balance of accuracy and generalization.

---

## 🌟 Feature Importance Insights

Using the Random Forest model, we found that:
- `total_sqft` and `bath` were among the top predictive features.
- Surprisingly, **`bathroom count` was more predictive than `location`**.
  - This suggests that the **quality and comfort level inside a property** often impact pricing more than just the area.
  - This effect was also **amplified by target encoding**, which smooths the influence of high-cardinality features like location.

---

## ✅ Final Model Evaluation

```python
# Metrics for Random Forest
MAE = 15.07 lakhs
MSE = 387.2 lakhs²
R² Score = 0.71
```

> The model can predict home prices with an average error of just **15.07 lakhs**, which is quite acceptable in urban real estate.

---

## 🔒 Model Reliability & Transparency

- We cleaned and validated the dataset thoroughly.
- Applied rigorous preprocessing and feature selection.
- Tested models across **multiple algorithms** for consistency.

> You can **rely on this model** as a dependable tool — not a final decision-maker, but a strong guide to assist in real estate valuation.

---

## 🔭 Future Scope

To improve further, we can:
- Integrate **real-time data** from housing platforms (e.g. MagicBricks, 99acres).
- Add new features: **metro proximity**, school ratings, crime index, etc.
- Deploy this model via a **web app or mobile app** for users and field agents.
- Build an **interactive price negotiation assistant** for real estate agents.

---

## 👥 Stakeholder Value

For **homebuyers**:
- Know if a property is overpriced or a good deal.

For **sellers**:
- Price your home competitively and attract more buyers.

For **investors**:
- Identify undervalued properties with high return potential.

---

## 📌 Conclusion

This Bengaluru House Price Predictor project combines **data science and business logic** to help stakeholders make better, faster, and smarter real estate decisions.

It's not just about prediction — it's about **empowering people with reliable insights** in a market that traditionally runs on guesswork.