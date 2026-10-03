# Airbnb Open Data – Data Cleaning with Python

A complete data cleaning workflow on the Airbnb Open Data dataset using Python and pandas.

---

## Project Overview

This project demonstrates a systematic approach to cleaning a raw, messy dataset using Python and pandas. The dataset contains short-term rental listings from New York City, originally sourced from Kaggle.

The goal was to transform the raw data into a clean, analysis-ready format by:
- Identifying and handling missing values
- Removing duplicate records
- Standardising column names and text values
- Correcting data types
- Exporting a clean CSV file for further analysis

---

## Dataset

| Detail | Description |
|--------|-------------|
| **Source** | [Airbnb Open Data – Kaggle](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata) |
| **Original Size** | 102,599 rows × 26 columns |
| **Final Size** | 83,969 rows × 20 columns |
| **Domain** | Short-term rental listings (New York City) |

---

## Tools and Libraries

- **Python 3.13**
- **pandas** – data loading, cleaning, and transformation
- **NumPy** – numerical operations
- **Matplotlib** – available for visualisation

---

## Cleaning Workflow

### 1. Data Loading and Inspection
Loaded the raw CSV file using `pd.read_csv()` and inspected its structure with `.info()`, `.head()`, and `.columns`.

### 2. Missing Value Analysis
Calculated missing value counts and percentages for each column to identify which columns had critical data quality issues.

### 3. Column Selection
Dropped six columns that had high missing rates or low analytical value:

| Column Dropped | Missing % | Reason |
|----------------|-----------|--------|
| `license` | 99.99% | Almost entirely empty |
| `house_rules` | 50.81% | Too many missing values |
| `availability 365` | 0.44% | Redundant for cleaning scope |
| `calculated host listings count` | 0.31% | Low analytical value |
| `review rate number` | 0.32% | Low analytical value |
| `reviews per month` | 15.48% | High missing rate |

### 4. Column Name Standardisation
Capitalised all column names for consistency. For example, `host id` became `Host id` and `price` became `Price`.

### 5. Duplicate Removal
Identified and removed 541 duplicate rows from the dataset.

### 6. Handling Missing Values
Dropped rows containing remaining null values. This reduced the dataset from 102,058 rows to 83,969 rows, producing a clean and high-quality subset.

### 7. Text Standardisation
Cleaned the `Host_identity_verified` and `Cancellation_policy` columns using `.str.strip().str.capitalize()` to ensure consistent text formatting.

### 8. Currency Cleaning
Removed dollar signs (`$`) from the `Price` and `Service fee` columns and removed thousands separators (`,`) from the `Price` column.

### 9. Data Type Conversion
Converted `Price` and `Service fee` from `object` to `int64`. Converted `Construction year` from `float64` to `int64` since years should not be decimal values.

### 10. Export
Saved the cleaned dataset as `airnb_clean_data.csv` for use in further analysis.

---

## Before vs After

| Metric | Before Cleaning | After Cleaning |
|--------|-----------------|----------------|
| Rows | 102,599 | 83,969 |
| Columns | 26 | 20 |
| Duplicates | 541 | 0 |
| Price Type | object (`$966`) | int64 (`966`) |
| Construction Year Type | float64 (`2020.0`) | int64 (`2020`) |

---
## Connect with me

[My GitHub Acc](https://github.com/Sayahtet)

[My LinkedIn Acc](www.linkedin.com/in/htet-aung-myint-46a4a6313)