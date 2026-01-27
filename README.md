# Financial Advisor ML Project

## Group Project – Coding Ninjas

This repository contains a Machine Learning–based Financial Advisor system developed as a group project for Coding Ninjas. The project focuses on analyzing user transaction data, categorizing expenses using machine learning techniques, and generating meaningful financial insights to help users understand their spending behavior.

---

## Problem Statement

Managing personal finances is a difficult task for many individuals due to unstructured transaction data, lack of categorization, and absence of clear spending insights. Users often receive transaction records in raw textual form, making it challenging to analyze expenses and track where money is being spent. Manual categorization of transactions is time-consuming and prone to errors. Hence, there is a need for an automated system that can intelligently process transaction data and provide structured financial analysis.

---

## Proposed Solution

The proposed solution is an AI-powered Financial Advisor that uses Machine Learning and Natural Language Processing to automatically analyze transaction data. The system processes raw transaction descriptions, predicts appropriate expense categories, allocates transaction amounts correctly, and generates analytical summaries and visualizations. This approach enables users to gain clarity about their spending patterns and make informed financial decisions.

---

## Project Workflow

1. Input transaction data in a structured CSV format containing transaction descriptions and amounts.  
2. Preprocess the data by cleaning text, handling missing values, and normalizing amounts.  
3. Split compound transaction descriptions into individual items when multiple purchases are present.  
4. Convert text data into numerical features using TF-IDF vectorization.  
5. Predict expense categories using a Logistic Regression classifier.  
6. Allocate transaction amounts proportionally across predicted categories.  
7. Generate category-wise spending summaries and visualizations such as bar charts and pie charts.  
8. Optionally generate short financial insights using a language model.

---

## Machine Learning Approach

The project uses Natural Language Processing techniques to analyze transaction descriptions. TF-IDF is used for text feature extraction with unigrams and bigrams. Logistic Regression is chosen as the classification model due to its efficiency, simplicity, and strong performance on text classification tasks. The model is trained on labeled transaction data and evaluated using standard classification metrics.

---

## Expense Forecasting and Trend Analysis Module

In addition to transaction categorization and historical analysis, the project includes a **monthly expense forecasting module** that predicts future spending trends across different expense categories.

This module enhances the Financial Advisor system by enabling **proactive financial insights**, allowing users to anticipate upcoming expenses rather than only analyzing past behavior.

### Forecasting Workflow

1. Aggregate categorized transaction data on a **monthly basis** for each expense category.  
2. Convert aggregated data into a **time-series format** suitable for modeling.  
3. Prepare independent time series for each category, handling missing values safely.  
4. Train multiple forecasting models per category:
   - Linear Regression
   - Random Forest Regressor
   - Moving Average baseline  
5. Compare predictions using recent historical values and select the **best-performing model per category**.  
6. Save selected models for reuse and generate next-month expense predictions.  
7. Export predictions, historical trends, and model metadata in a structured JSON format.

### Forecasting Approach

- **Linear Regression** captures steady and long-term spending trends.  
- **Random Forest Regressor** models non-linear and irregular expense patterns.  
- **Moving Average** is used when historical data is limited.

By dynamically selecting the most suitable model for each category, the system ensures robust and adaptable predictions.

### Output Integration

The forecasting module produces a JSON output containing:
- Category-wise next-month expense predictions  
- Historical monthly trend data  
- Selected model details for each category  

This output can be directly integrated with frontend dashboards and visualization components of the Financial Advisor system.



---

## Technologies Used

Programming Language: Python  
Libraries and Tools: Pandas, NumPy, Scikit-learn, Matplotlib  
Development Environment: Jupyter Notebook  
Optional Component: Ollama for generating language model–based financial insights

---

## Project Structure

<pre>
Financial-Advisor-ML-project/
├── data/
│   └── transactions_clean.csv
├── Models/
├── notebooks/
│   └── finance_pipeline.ipynb
│   └── prediction_notebook.ipynb
├── Predictions/
├── requirements.txt
├── .gitignore
└── README.md
</pre>

---

## How to Run the Project

1. Download or clone the repository.  
2. Install the required dependencies using `pip install -r requirements.txt`.  
3. Open Jupyter Notebook and load `finance_pipeline.ipynb`.  
4. Run all cells to execute the financial analysis pipeline and view results.

---

## Expected Outcomes

The system automatically categorizes transactions, provides a clear breakdown of expenses by category, and visualizes spending patterns. Users gain better financial awareness through structured analysis and graphical representations.

---

## Learning Outcomes

This project provides hands-on experience in building an end-to-end machine learning pipeline. It enhances understanding of text preprocessing, feature engineering, supervised learning, data visualization, and practical application of machine learning in financial data analysis.

---

## Disclaimer

This project is developed strictly for educational purposes as part of a Coding Ninjas group assignment. It is not intended to provide professional or financial advice.

---

## Contributors

Group Project Team – Coding Ninjas
