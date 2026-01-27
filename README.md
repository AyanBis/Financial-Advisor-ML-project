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

## Technologies Used

Programming Language: Python  
Libraries and Tools: Pandas, NumPy, Scikit-learn, Matplotlib  
Development Environment: Jupyter Notebook  
Optional Component: Ollama for generating language model–based financial insights

---

## Project Structure

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
