# Retail Store Sales — Data Cleaning & Preprocessing

## Project Overview

This project focuses on cleaning and preprocessing a retail store sales dataset to make it suitable for reliable data analysis.

The dataset contains **12,575 transaction records and 11 columns** covering transaction details, customers, products, prices, quantities, payment methods, locations, dates, and discounts.

## Objectives

- Identify missing values
- Identify duplicate records
- Handle missing categorical and numerical values
- Correct inappropriate data types
- Validate the cleaned dataset
- Export a clean dataset for further analysis

## Data Quality Issues Identified

The initial dataset contained missing values in:

| Column | Missing Values |
|---|---:|
| Item | 1,213 |
| Price Per Unit | 609 |
| Quantity | 604 |
| Total Spent | 604 |
| Discount Applied | 4,199 |

No completely duplicate rows were found.

## Cleaning Approach

### Categorical Variables

Missing values in `Item` and `Discount Applied` were replaced with `Unknown`.

This preserves the transaction records without making unsupported assumptions about the missing information.

### Numerical Variables

Missing values in `Price Per Unit` and `Quantity` were imputed using the median.

The median was selected because it is less affected by extreme values than the mean.

### Total Spent

Missing `Total Spent` values were first calculated using:

`Price Per Unit × Quantity`

Where this calculation was not possible, the remaining missing values were handled using the median.

### Transaction Date

`Transaction Date` was converted from an object/string format to a proper datetime format.

## Final Result

After cleaning:

- Missing values: **0**
- Duplicate rows: **0**
- Dataset retained: **12,575 records**
- Dataset prepared for further analysis

## Tools Used

- Python
- Pandas
- NumPy
- Jupyter Notebook

## Project Structure

```text
Retail-Store-Sales-Cleaning/
│
├── retail_store_sales_cleaning.ipynb
├── retail_store_sales_cleaned.csv
├── README.md
└── requirements.txt
```

## Next Steps

The cleaned dataset can be used for:

- Exploratory Data Analysis (EDA)
- Data visualization
- Business intelligence dashboards
- Customer and sales analysis
- Further statistical analysis
