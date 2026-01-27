# 📊 Expense Category Forecasting – Monthly Prediction System

## 📌 Overview
This project implements a **monthly expense forecasting system** that predicts future spending for different expense categories using historical data.  
The notebook processes raw transaction data, converts it into a time-series format, trains multiple models per category, selects the best one automatically, and exports the results in a frontend-ready JSON format.

---

## 📂 Project Structure

<pre>
Financial-Advisor-ML-project/
├── Predictions (Nirbhay)/
│   └── Models
│   └── Notebook
│   └── Prediction
│   └── Readme.md
├── notebooks/
│   └── finance_pipeline.ipynb
├── data/
│   └── transactions_clean.csv
├── requirements.txt
├── .gitignore
└── README.md
</pre>



---

## 📊 Dataset Requirements
The input dataset (`dataset.csv`) must contain the following columns:

| Column Name | Description |
|------------|-------------|
| `month_year` | Month and year of the expense (e.g., `2024-06`) |
| `category` | Expense category (Food, Rent, Travel, etc.) |
| `amount` | Expense amount |

---

## 🔄 Data Processing

### 1. Monthly Aggregation
- Expenses are grouped by `month_year` and `category`
- Total monthly spending per category is calculated
- Data is reshaped into a **pivot table**:
  - Rows → Months
  - Columns → Categories
  - Values → Total expenses

### 2. Time-Series Preparation
- Each category is handled independently
- Missing categories are filled with `0`
- A time index (`t`) is added to represent sequential months

---

## 🤖 Forecasting Methods

For every expense category, three prediction techniques are evaluated:

### 🔹 Linear Regression
- Models linear trends over time
- Trained on historical monthly data

### 🔹 Random Forest Regressor
- Captures non-linear spending patterns
- Suitable for irregular or volatile expenses

### 🔹 Moving Average
- Uses the average of the last `k` months
- Acts as a fallback for small datasets

---

## 🧠 Model Selection Strategy
- If insufficient data is available, **Moving Average** is used
- Otherwise:
  - All three models generate predictions
  - Each prediction is compared against the most recent actual value
  - The model with the **lowest absolute error** is selected

This allows **adaptive, per-category model selection** instead of a single global model.

---

## 💾 Model Saving
- Selected models (Linear Regression or Random Forest) are saved using `joblib`
- Models are stored in the `models/` directory
- Moving Average does not require model persistence

---

## 📤 Output

### `predictions_output.json`
The final output file contains:
- **Predicted expense values** for each category
- **Historical monthly trend data**
- **Model metadata**, including:
  - Chosen model type
  - Saved model file path (if applicable)

This output is optimized for **frontend dashboards and visualizations**.

---

## 🛠 Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Joblib
- JSON

---

## ⭐ Key Features
- Category-wise forecasting
- Automatic model comparison and selection
- Handles missing and limited data gracefully
- Modular and scalable design
- Frontend-ready output

---

## 📌 Conclusion
This project provides a flexible and interpretable system for **monthly expense forecasting**.  
By combining statistical baselines with machine learning models, it ensures robust predictions while remaining simple and extensible.

---
