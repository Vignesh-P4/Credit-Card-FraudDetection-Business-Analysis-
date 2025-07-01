
# 💳 Credit Card Fraud Detection – BI Dashboard Project

A business intelligence project that explores and visualizes credit card transaction data to detect and analyze fraudulent behavior using Power BI.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Objective](#objective)
- [Dataset](#dataset)
- [Tools Used](#tools-used)
- [Data Cleaning & Transformation](#data-cleaning--transformation)
- [Dashboard Features](#dashboard-features)
- [Business Insights](#business-insights)
- [Recommendations](#recommendations)
- [Screenshots](#screenshots)
- [Run This Project](#run-this-project)
- [License](#license)
- [Author](#author)

---

## 🧾 Overview

This project leverages the power of data visualization and BI tools to analyze real-world credit card transactions and detect fraudulent activity patterns. It focuses on building a Power BI dashboard to assist fraud detection teams in financial institutions.

---

## 🎯 Objective

- Analyze transactional behavior in credit card data
- Identify and understand fraud patterns
- Visualize fraud KPIs for business decision-making
- Recommend actions to improve fraud detection efficiency

---

## 📊 Dataset

- 📍 **Source**: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- 📦 **Total Records**: 284,807 transactions
- 🧬 **Features**:
  - `Time`: Seconds since the first transaction
  - `Amount`: Transaction value
  - `V1–V28`: PCA-transformed features (anonymized)
  - `Class`: 0 = Valid, 1 = Fraud

---

## 🧰 Tools Used

- Power BI  
- Excel  
- DAX (for calculated measures)  
- Power Query (for data transformation)  

---

## 🧼 Data Cleaning & Transformation

Performed in Power BI's **Power Query Editor**:
- Checked for nulls – none found
- Changed column data types (Time: whole number, Amount: decimal, Class: whole number)
- Added custom column: `Transaction Type = if [Class] = 1 then "Fraud" else "Valid"`
- Loaded cleaned data into Power BI

---

## 📈 Dashboard Features

### ✅ KPIs:
- Total Transactions  
- Valid Transactions  
- Fraud Transactions  
- Fraud Percentage  

### 📊 Visuals:
- Pie chart: Fraud vs Valid Distribution  
- Bar chart: Amount by Transaction Type  
- Line chart: Sum of Amount over Time  
- Slicers: Filter by Transaction Type

### 📌 Key DAX Measures:
```dax
Total Transactions = COUNT('Sheet1'[Class])
Valid Transactions = CALCULATE(COUNT('Sheet1'[Class]), 'Sheet1'[Class] = 0)
Fraud Transactions = CALCULATE(COUNT('Sheet1'[Class]), 'Sheet1'[Class] = 1)
Fraud % = DIVIDE([Fraud Transactions], [Total Transactions], 0)
```

---

## 📊 Business Insights

🔹 Only 0.17% of transactions were fraudulent (492 out of 285K+)  
🔹 Fraud amounts tend to be smaller on average  
🔹 Certain time windows show a higher frequency of fraud  
🔹 Valid transactions dominate the dataset (>99.8%)  
🔹 Slicers allow dynamic filtering to drill down into fraud cases

---

## 💡 Recommendations

- Implement real-time fraud alerts during peak fraud times  
- Add verification for small-value, high-frequency transactions  
- Use dashboard insights to update ML fraud detection models  
- Review dashboard KPIs monthly for audit and fraud detection teams  

---

## 📸 Screenshots

Attached to this repository.

---

## 🛠️ Run This Project

1. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)  
2. Open `PowerBI_Report.pbix` file in Power BI Desktop  
3. Click **Transform Data** to review query steps  
4. Explore dashboard KPIs and insights  

---

## 📄 License

This project is shared for educational purposes under the MIT License.

---

## 🙋‍♂️ Author

Vignesh Pobbathi – Data Analyst | BI Developer  
[LinkedIn](https://www.linkedin.com/in/vigneshpobbathi/) • [GitHub](https://github.com/Vignesh-P4)

---
