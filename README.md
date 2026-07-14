# Saas-Ecommerce-cohort-retention-CLTV_Project

# DAY 1
# Searching and Selecting the right dataset for Project
- In day 1 we are seaching and selecting the right dataset for the project in which all required things are present, to achieve project Goal. finally we find a right and useful dataset for Project on kaggle - https://www.kaggle.com/code/nuranynovita/cohort-analysis-customer-retention?select=online_retail_II.csv


# Day 2: Data Understanding & Data Cleaning
### Objective

The objective of this phase was to understand the Online Retail II dataset, identify data quality issues, and prepare a clean transactional dataset for Cohort Analysis, Customer Retention Analysis, and Customer Lifetime Value (CLTV) calculations.

### Tasks Performed
- Loaded and inspected the raw dataset.
- Analyzed dataset structure, data types, and missing values.
- Identified and removed records with missing Customer IDs.
- Converted InvoiceDate to datetime format.
- Detected and removed cancelled/refunded transactions using Invoice IDs starting with 'C'.
- Investigated duplicate records and removed exact duplicates.
- Identified and removed transactions with zero product prices.
- Performed final data validation checks.
- Saved the cleaned dataset for further cohort analysis.

## Data Cleaning Summary
### Metric	Count
- Original Rows:-	1,067,371
- Missing Customer IDs Removed:-	243,007
- Cancelled Transactions Removed:-	18,744
- Duplicate Records Removed:-	26,125
- Zero Price Records Removed:-	71
- Final Cleaned Rows:-	779,425

### Final Dataset Status
- Missing Customer IDs: 0
- Cancelled Transactions: 0
- Negative Quantity Records: 0
- Zero Price Records: 0
- Duplicate Records: 0

### Output
online_retail_cleaned_v1.csv

## Day 2 Conclusion

## Data Understanding & Cleaning Completed

### Initial Dataset
- Rows: 1,067,371
- Columns: 8

### Data Quality Issues Found
- Missing Customer IDs: 243,007
- Cancelled Transactions: 18,744
- Duplicate Records: 26,125
- Zero Price Records: 71

### Cleaning Actions Performed
1. Removed records with missing Customer IDs.
2. Removed cancelled/refunded transactions using Invoice IDs starting with 'C'.
3. Converted InvoiceDate to datetime format.
4. Removed duplicate records.
5. Removed records with zero product price.

### Final Dataset
- Rows: 779,425
- Columns: 8
- Missing Customer IDs: 0
- Cancelled Transactions: 0
- Negative Quantity Records: 0
- Zero Price Records: 0
- Duplicate Records: 0

The cleaned dataset is now ready for Cohort Analysis, Retention Analysis, and Customer Lifetime Value (CLTV) calculations.
