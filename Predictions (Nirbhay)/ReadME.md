📊 Expense Category Forecasting – Monthly Prediction System
📌 Project Overview

This project focuses on forecasting monthly expenses across different categories using historical transaction data.
The notebook processes raw expense data, converts it into a time-series format, applies multiple forecasting techniques, and automatically selects the best-performing model for each category.

The final output is a JSON file that contains:

Predicted expenses for the next month (per category)

Historical monthly trend data

Information about which model was selected for each category

This structure is designed to be frontend-friendly, making it easy to visualize trends and predictions.

🗂 Dataset Description

The input dataset (dataset.csv) is expected to contain:

month_year → Month of the transaction (e.g., 2024-06)

category → Expense category (e.g., Food, Rent, Travel)

amount → Expense value

🔄 Data Processing Workflow
1️⃣ Monthly Aggregation

Expenses are grouped by month and category

Total spending per category is calculated for each month

Data is converted into a pivot table where:

Rows → Months

Columns → Categories

Values → Total expense amount

This makes the data suitable for time-series modeling.

2️⃣ Time-Series Preparation

For each category:

Missing categories are handled safely by filling values with 0

A time index t is created to represent sequential months

This allows models to learn temporal trends

🤖 Forecasting Models Used

For each expense category, the notebook evaluates three prediction approaches:

🔹 Linear Regression

Captures linear trends over time

Trained using past months to predict the next month

🔹 Random Forest Regressor

Handles non-linear patterns

More flexible for irregular spending behavior

🔹 Moving Average

Uses the average of the last k months

Acts as a fallback when data is limited

🧠 Model Selection Logic

If a category has very limited data, Moving Average is used

Otherwise:

All three methods generate predictions

Their errors are compared against the most recent actual value

The model with the lowest absolute error is selected

This ensures adaptive and data-driven model selection per category.

💾 Model Persistence

Trained models (Linear Regression or Random Forest) are saved using joblib

Models are stored in the models/ directory

Only the selected best model is saved

📤 Final Output

The notebook generates a single JSON file:

predictions_output.json

It contains:

Predicted expense values for each category

Historical monthly trend data for visualization

Model metadata, including:

Selected model type

Saved model file (if applicable)

This output is optimized for integration with dashboards or frontend applications.

🛠 Technologies Used

Python

Pandas & NumPy (Data processing)

Scikit-learn (Machine learning models)

Joblib (Model saving)

JSON (Data exchange format)

✅ Key Highlights

Handles multiple expense categories automatically

Chooses the best model per category instead of a single global model

Robust to missing or limited data

Frontend-ready JSON output

Clean and modular design

📌 Conclusion

This notebook provides a scalable and interpretable expense forecasting system that adapts to different spending behaviors across categories.
It balances simplicity and performance by combining classical regression, ensemble learning, and statistical baselines.