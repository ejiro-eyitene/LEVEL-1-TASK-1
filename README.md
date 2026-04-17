# LEVEL 1
## Stock Price Data Cleaning & Preprocessing

**Codveda Technologies - Data Analysis Intern**  
**Eyitene Ejiro Marvin |ID :- CV/A1/65350**

## Project Overview
This project involves the initial data cleaning and preprocessing of a comprehensive stock price dataset. The goal was to transform raw financial data into a standardized, analysis-ready format by handling missing values, verifying uniqueness, and correcting data types.

## Dataset Description
The dataset, **"2) Stock Prices Data Set.csv"**, contains **497,472 records** with the following features:
* **symbol**: The stock ticker identifier.
* **date**: The trading date.
* **open, high, low, close**: The stock price points for the given day.
* **volume**: The number of shares traded.

---

## Preprocessing Workflow

### 1. Missing Value Analysis
Upon initial inspection, the following columns were found to have missing entries:
* **Open**: 11 missing values.
* **High**: 8 missing values.
* **Low**: 8 missing values.

### 2. Grouped Imputation
To maintain the integrity of the time-series data, missing values were handled using a grouped imputation strategy:
* **Method**: Data was grouped by the stock `symbol`.
* **Logic**: Applied a combination of **Forward Fill (ffill)** and **Backward Fill (bfill)** within each group to estimate missing prices based on chronological neighbor data.
* **Result**: Successfully reduced the total null count to **0**.

### 3. Duplicate Verification
* A check for duplicated rows was performed across the entire dataset.
* **Finding**: The dataset contained **0** duplicate rows, confirming data uniqueness.

### 4. Format Standardization
The most critical step for time-series analysis was standardizing the `date` column:
* **Initial Format**: Stored as a generic `object` (string).
* **Correction**: Converted the column to `datetime64[ns]` using `pd.to_datetime()` with `errors='coerce'`.
* **Benefit**: This ensures the data can be correctly sorted and indexed for future trend analysis or forecasting.

---

## Tools Used
* **Python**: Core programming language.
* **Pandas**: Primary library for data manipulation and cleaning.

## Final Data State
After preprocessing, the dataset is clean, fully populated (no missing values), unique (no duplicates), and properly typed for financial modeling.
