# ☕ Cafe Sales Analysis & Forecasting

This project applies data science techniques to analyze and forecast cafe sales. It includes predictive modeling, sales trend analysis, product clustering, and a recommendation system to support decision-making for small cafes and food businesses.

---

## 📌 Table of Contents
- [Introduction](#introduction)  
  - [Background](#background)  
  - [Problem Statement](#problem-statement)  
  - [Objective](#objective)  
  - [Significance of Project](#significance-of-project)  
- [Approach](#approach)  
  - [Data Collection](#data-collection)  
  - [Preprocessing and Data Cleaning](#preprocessing-and-data-cleaning)  
  - [Methods of Analysis](#methods-of-analysis)  
  - [Tools Used](#tools-used)  
- [Modeling](#modeling)  
  - [Predictive Modeling](#predictive-modeling)  
    - [Feature Preparation](#feature-preparation)  
    - [Train-Test Split & Model Selection](#train-test-split--model-selection)  
  - [Sales Analysis by Region](#sales-analysis-by-region)  
    - [Objective](#region-objective)  
    - [Methodology & Results](#region-methodology--results)  
  - [Product Clustering Analysis](#product-clustering-analysis)  
    - [Methodology & Results](#clustering-methodology--results)  
  - [Product Recommendation System](#product-recommendation-system)  
    - [Overview](#recommendation-overview)  
    - [Methodology & Results](#recommendation-methodology--results)  
    - [Business Implications](#business-implications)  
- [Conclusion](#conclusion)

---

## 📖 Introduction

### Background
The dataset, obtained from Kaggle, contains transactional records from a cafe. Each entry includes item name, quantity sold, unit price, total amount, payment type, location, and date of sale.

### Problem Statement
Cafe sales are volatile, making inventory control, pricing, and staffing difficult. The project addresses issues like:
- Perishable overstock/understock
- Identifying top-selling vs. underperforming items
- Understanding customer purchasing patterns
- Regional performance variations

**Key Research Questions:**
- How can we forecast weekly/monthly item-level sales?
- What products are frequently bought together?
- Which products are high, medium, or low performers?
- How does sales performance vary across locations?

### Objective
This study aims to support cafe operations through:
- Analysis of historical sales
- Forecasting future trends
- Identifying drivers of performance
- Evaluating model accuracy

### Significance of Project
The findings help:
- Reduce waste through better inventory planning
- Improve staffing and supply chain decisions
- Drive revenue through product recommendations
- Build data-driven tools for small cafes and F&B businesses

---

## 🚀 Approach

### Data Collection
- Sourced from Kaggle
- Includes sales details by item, location, and date

### Preprocessing and Data Cleaning
- Removed missing/inconsistent values
- Parsed timestamps and created time-based features
- Grouped data by item, region, and time period

### Methods of Analysis
- Exploratory Data Analysis (EDA)
- Time Series Forecasting
- Association Rule Mining
- Clustering
- Recommendation Algorithms

### Tools Used
- Python (Pandas, NumPy, Scikit-learn)
- Facebook Prophet, XGBoost, LSTM
- Matplotlib, Seaborn
- MLxtend (Apriori Algorithm)
- Jupyter Notebook
- GitHub for version control

---

## 🧠 Modeling

### Predictive Modeling

#### Feature Preparation
- Time-based features (day, month, seasonality)
- Lag and rolling window stats
- Encoded categories and holiday flags

#### Train-Test Split & Model Selection
- Time-aware train-test split
- Models used:
  - Linear Regression
  - XGBoost
  - Facebook Prophet
  - LSTM Neural Network
- Evaluation Metrics:
  - RMSE, MAE

---

### Sales Analysis by Region

#### Region Objective
To compare performance across different locations and support regional planning.

#### Region Methodology & Results
- Aggregated sales by region
- Visualized seasonal trends
- Identified top/bottom performing branches

---

### Product Clustering Analysis

#### Methodology & Results
- Used K-Means clustering on product sales volume and revenue
- Categorized products into high, medium, and low performers
- Visualized clusters for inventory management

---

### Product Recommendation System

#### Overview
A basic recommender system identifies frequently purchased item pairs.

#### Methodology & Results
- Applied Apriori Algorithm for association rules
- Filtered by confidence and lift
- Created item-to-item recommendation matrix

#### Business Implications
- Promote bundled offers
- Encourage upselling
- Enhance digital menu personalization
# ☕ Cafe Sales Forecasting & Recommendation System

This project analyzes and forecasts sales trends for a cafe using transactional data. It includes **sales prediction**, **regional sales analysis**, **product clustering**, and a **recommendation system**, offering practical insights for improving operations, inventory, and marketing strategies.

---

## 🔍 Project Objectives

- 📦 Forecast item-level sales to reduce waste and optimize inventory  
- 🥇 Identify high, medium, and low-performing items  
- 🛒 Analyze item combinations frequently bought together  
- 🎯 Provide actionable recommendations for marketing and operations  

---

## 📦 Dataset Description

- **Source**: Kaggle — *Cafe Sales Data*  
- **Fields**:
  - `Transaction ID`
  - `Item`
  - `Quantity`
  - `Price per Unit`
  - `Total Spent`
  - `Payment Method`
  - `Location`
  - `Transaction Date`

---

## 🛠️ Methodology

### 1. 🔧 Data Preprocessing
- Handled missing values:
  - **Mode** for categorical
  - **Median** for numerical
- Converted dates to `datetime`, encoded categories
- Removed duplicates and outliers
- Unified category labels (e.g., "tea", "TEA" → "TEA")
- Applied `log1p` transformation to handle skew in `Total Spent`

### 2. 🔮 Sales Forecasting
- **Models Used**:
  - `Random Forest Regressor`
  - `Linear Regression`
- **Target Variable**: `Total Spent`
- **Best Model**:  
  - **Random Forest**  
    - R² Score: **0.899**  
    - MSE: **0.0358**

### 3. 🌍 Regional Sales Analysis

| Location   | Total Sales | Avg Quantity | Monthly Growth |
|------------|-------------|--------------|----------------|
| Takeaway   | 13,460.13   | 2.97         | **+26%**       |
| In-Store   | 5,818.34    | 2.98         | **−12%**       |

- Takeaway is growing, while in-store sales are declining.

### 4. 🧊 Product Clustering (K-Means)
- Clustered items by:
  - Total quantity
  - Purchase frequency
  - Revenue

| Cluster | Items                    | Avg Revenue | Type            |
|---------|--------------------------|-------------|-----------------|
| 1       | Juice                    | 4,335.89    | 🏆 Top Performer |
| 2       | Coffee, Cake, Sandwich   | ~2,369      | 🎯 Mid Tier      |
| 0       | Tea, Cookie              | 1,549.18    | 🚨 Low Performer |

- **Silhouette Score**: 0.35 (Moderate cohesion)

### 5. 🧠 Product Recommendation System
- **Approach**: Content-based filtering using **cosine similarity**
- **Input Example**: `"Sandwich"`  
- **Top Recommendations**:
  - `Coffee`
  - `Cake`
  - `Cookie`

- **Use Cases**:
  - Bundle offers (e.g., Sandwich + Cookie + Juice)
  - Menu optimization
  - Checkout suggestions

---

## 📊 Tools & Technologies

| Category         | Tools & Libraries                                     |
|------------------|--------------------------------------------------------|
| Language         | Python 3.13                                            |
| Data Handling    | `pandas`, `NumPy`                                      |
| Visualization    | `matplotlib`, `seaborn`                                |
| Modeling         | `LinearRegression`, `RandomForestRegressor`, `KMeans` |
| Recommendation   | `cosine_similarity` from `scikit-learn`                |

---

## 📈 Key Insights

- ✅ **Random Forest** outperforms Linear Regression for predicting total sales.
- 📈 **Takeaway sales** show strong positive growth, unlike in-store.
- 🍹 **Juice** is the best-selling product, while **Tea** and **Cookie** underperform.
- 🍰 **Sandwich** is commonly purchased with Coffee, Cake, and Cookie—ideal for bundle deals.

---

## 📁 Folder Structure

```bash
📁 cafe-sales-analysis/
├── 📊 data/
│   └── dirty_cafe_sales.csv
├── 📁 notebooks/
│   ├── preprocessing.ipynb
│   ├── modeling.ipynb
│   ├── clustering.ipynb
│   └── recommendation.ipynb
├── 📄 cafe_analysis.py
├── 📄 requirements.txt
└── 📄 README.md


---

## Conclusion

This project offers a complete analytical framework to improve sales forecasting, product strategy, and customer insights for cafes. The insights derived help in:
- Reducing inventory waste
- Boosting revenue
- Enhancing customer satisfaction
- Supporting small business digitization through data

---

 

