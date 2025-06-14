# ☕ Cafe Sales Forecasting & Recommendation System

This project applies data science techniques to analyzes and forecasts sales trends for a cafe using transactional data. It includes **sales prediction**, **regional sales analysis**, **product clustering**, and a **recommendation system**, offering practical insights for improving operations, inventory, and marketing strategies.

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
  - [Sales Analysis by Region](#sales-analysis-by-region)  
  - [Product Clustering Analysis](#product-clustering-analysis)  
  - [Product Recommendation System](#product-recommendation-system)  
- [Key Insights](#key-insights)  
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
- Handled missing values:
  - **Mode** for categorical
  - **Median** for numerical
- Converted dates to `datetime`, encoded categories
- Removed duplicates and outliers
- Unified category labels (e.g., "tea", "TEA" → "TEA")
- Applied `log1p` transformation to handle skew in `Total Spent`
- Extracted time-based features like day, month, and year

### Methods of Analysis
- Exploratory Data Analysis (EDA)
- Regression Forecasting
- K-Means Clustering
- Content-Based Recommendation System

### Tools Used
- Python 3.13
- Libraries: `pandas`, `NumPy`, `matplotlib`, `seaborn`, `scikit-learn`
- MLxtend for Apriori Algorithm
- Jupyter Notebooks for development
- GitHub for version control

---

## 🧠 Modeling

### 🔮 Predictive Modeling

#### Feature Preparation
- Encoded categorical variables
- Extracted time-based features like month, weekday, etc.

#### Train-Test Split & Model Selection
- Time-aware train-test split
#### Models Used:
- Linear Regression
- Random Forest Regressor
- Decision Tree Regressor

#### Evaluation Metrics:
| Model             | R² Score | MSE     |
|------------------|----------|---------|
| Random Forest     | 0.899    | 0.0358  |
| Decision Tree     | 0.795    | 0.0726  |
| Linear Regression |0.8786    |0.04310  |

**Random Forest** showed superior performance in predicting `Total Spent` compared to the simpler Decision Tree and Linear Regression.

---

### 🌍 Sales Analysis by Region

#### Objective
To compare performance across different locations and support regional planning.

#### Methodology & Results

| Location   | Total Sales | Avg Quantity | Monthly Growth |
|------------|-------------|--------------|----------------|
| Takeaway   | 13,460.13   | 2.97         | **+26%**       |
| In-Store   | 5,818.34    | 2.98         | **−12%**       |

- Takeaway channels are growing significantly.
- In-store traffic is declining,indicating areas to improve service or marketing.

---

### 🧪 Product Clustering Analysis

#### Methodology & Results
- Clustered items by:
  - Total quantity
  - Purchase frequency
  - Revenue
- Applied K-Means Clustering
- Used Elbow Method to determine optimal K
- **Silhouette Score**: 0.35

| Cluster | Items                    | Avg Revenue | Type            |
|---------|--------------------------|-------------|-----------------|
| 1       | Juice                    | 4,335.89    | 🏆 Top Performer |
| 2       | Coffee, Cake, Sandwich   | ~2,369      | 🎯 Mid Tier      |
| 0       | Tea, Cookie              | 1,549.18    | ⚠️ Low Performer |
-Silhouette Score: **0.35** (moderate separation)

---

### 🧠 Product Recommendation System

#### Overview
Built a content-based recommendation system to suggest item pairs.

#### Methodology & Results
- Used user-item matrix
- Computed cosine similarity between items
- Alternatively tested Apriori for frequent pairs

#### Sample Recommendation
If a customer buys a **Sandwich**, recommend:
- `Coffee`
- `Cake`
- `Cookie`

#### Business Implications
- Promote bundled deals
- Personalized upselling
- Drive revenue through cross-selling

---

## 📈 Key Insights

- ✅ **Random Forest** outperforms Linear Regression for predicting total sales.
- ✅ The **Decision Tree** model, while simpler, underperformed (R² = 0.795, MSE = 0.0726)
- 📈 **Takeaway** sales show strong positive growth.
- 📈 **Takeaway** sales channels dominate, while **In-Store** channels are declining.
- 🍹 **Juice** is the highest-performing product.
- 🍚 **Tea** and **Cookie** underperform and may need pricing/menu optimization.
- 📈 Product bundling opportunities are clearly supported by the **recommendation system** and **clustering analysis**.
- 🍰 **Sandwich** pairs well with other high-volume products—ideal for promotions.

---

## Conclusion

This study demonstrates the practical application of machine learning in optimizing operations within the food and beverage industry. From data preprocessing to predictive modeling, regional sales analysis, product clustering, and recommendation systems, each component contributes to a data-driven understanding of customer behavior and sales trends.
This project offers a complete analytical framework to improve sales forecasting,improve operational efficiency, and profitability through intelligent analytics,product strategy, and customer insights for cafes. The insights derived help in:
- Reducing inventory waste
- Boosting revenue
- Enhancing customer satisfaction
- Supporting small business digitization through data

---



