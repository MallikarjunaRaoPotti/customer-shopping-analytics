# 🛒 Customer Shopping Analytics Pipeline

A complete end-to-end data analytics pipeline built on a real customer shopping dataset covering data extraction, cleaning, normalization, analysis and visualization.

---

## 📌 Project Overview

This project simulates a real-world ETL pipeline where raw messy customer shopping data is extracted, transformed through cleaning and normalization, analyzed for business insights, and loaded as a clean dataset ready for business use.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core programming language |
| Pandas | Data manipulation and cleaning |
| Sklearn | Min-Max Normalization |
| Matplotlib | Data visualization |
| Google Colab | Development environment |
| SQLite | Database storage |

---

## 📂 Project Structure

```
customer-shopping-analytics/
│
├── customer_analytics.ipynb       # Main Colab notebook
├── customer_shopping_messy.csv    # Raw messy dataset
├── customer_analytics_clean.csv   # Final clean dataset
└── README.md                      # Project documentation
```

---

## 🔄 ETL Pipeline Workflow

```
Raw CSV Dataset (99,957 rows)
        ↓
     EXTRACT
     Load CSV → Explore Data
        ↓
    TRANSFORM
    ├── Standardize text columns
    ├── Remove 478 duplicate records
    ├── Remove outlier age values (> 100)
    ├── Remove negative price values
    ├── Fill 300 missing age values with mean
    ├── Fill 200 missing price values with mean
    ├── Fix mixed date formats to datetime
    ├── Fix age column from float to int
    └── Min-Max Normalize age and price
        ↓
      LOAD
      Save clean CSV (98,729 rows)
```

---

## 🧹 Data Cleaning Steps

| Problem | Action | Records Affected |
|---------|--------|-----------------|
| Duplicate rows | `drop_duplicates()` | 478 removed |
| Missing age values | `fillna(mean)` | 300 filled |
| Missing price values | `fillna(mean)` | 200 filled |
| Outlier age (999) | Filter age <= 100 | 150 removed |
| Negative price (-99) | Filter price > 0 | 100 removed |
| Inconsistent gender | `str.lower().str.strip()` | Standardized |
| Inconsistent category | `str.lower().str.strip()` | Standardized |
| Inconsistent payment | `str.lower().str.strip()` | Standardized |
| Extra spaces in mall | `str.strip()` | Standardized |
| Mixed date formats | `pd.to_datetime(format='mixed')` | Fixed |

---

## 📊 Normalization

Applied **Min-Max Scaling** using sklearn's MinMaxScaler on:
- `age` → scaled from 18-69 to 0.0-1.0
- `price` → scaled from 5.23-5250 to 0.0-1.0

---

## 📈 Business Insights

### 1. Average Spending by Age Group
- All age groups spend equally around 680-700
- Product appeals uniformly across all demographics

### 2. Monthly Sales Trend
- Sales consistently stable at 2.5M-2.7M per month
- Peak months observed in July and October 2021

### 3. Payment Method by Category
- Cash is the most preferred payment method across all categories
- Clothing is the top selling category at 31M+ total sales
- Technology and Shoes follow as second and third highest

---

## 📉 Dataset Summary

| Metric | Value |
|--------|-------|
| Raw rows | 99,957 |
| Final clean rows | 98,729 |
| Total columns | 15 |
| Date range | 2021-2023 |
| Categories | 8 |
| Shopping malls | 10 |

---

## 🚀 How to Run

1. Open [Google Colab](https://colab.research.google.com)
2. Upload `customer_analytics.ipynb`
3. Upload `customer_shopping_messy.csv`
4. Run all cells in order

---

## 👤 Author

**Mallikarjuna Rao Potti**  
