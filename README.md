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

---

# Day 3: Cohort Month Creation & Retention Analysis Setup
## Objective

The objective of this phase was to transform the cleaned transactional dataset into a cohort-ready dataset by identifying customer acquisition months, calculating customer lifecycle periods, and preparing the foundation for retention analysis and cohort visualization.

## Tasks Performed
### 1. Loaded Cleaned Dataset
- Imported the cleaned transactional dataset (online_retail_cleaned_v1.csv).
- Verified dataset shape and data quality.

### 2. Datetime Conversion
- Converted InvoiceDate into datetime format.
- Ensured compatibility for monthly cohort calculations.

### 3. Created Invoice Month
- Extracted transaction month from each purchase date.
- Standardized all transactions at monthly granularity.

### 4. Identified Customer Acquisition Month
- Grouped transactions by Customer ID.
- Determined each customer's first purchase month.
- Created the Cohort Month variable.

### 5. Cohort Mapping
- Assigned every transaction to its corresponding acquisition cohort.
- Linked historical purchases with the customer's original cohort.

### 6. Calculated Cohort Index
- Measured the number of months elapsed since customer acquisition.
- Created the key metric required for retention analysis.

### 7. Built Retention Base Table
- Calculated unique retained customers for every cohort and month.
- Prepared the dataset required for retention matrix generation.

## Key Results
### Dataset Summary
### Metric	Value
Transactions	779,425

Cohorts Identified	25

Minimum Cohort Index	1

Maximum Cohort Index	25

## Example Retention Data
### Cohort Month	Cohort Index	Customers
2009-12	1	955

2009-12	2	337

2009-12	3	319

This indicates significant customer drop-off after the acquisition month and provides the foundation for retention analysis.

## Files Generated
### Processed Data
cohort_prepared_data.csv

retention_base_table.csv

---

# Day 4- Cohort Retention matrix & Heatmap

## Cohort Retention Matrix Completed

## Tasks Performed

- Created Retention Count Matrix
- Created Retention Percentage Matrix
- Generated Cohort Retention Heatmap
- Calculated Average Retention Trends
- Exported Retention Analysis Outputs

## Deliverables

- retention_count_matrix.csv
- retention_percentage_matrix.csv
- retention_heatmap.png

These outputs reveal customer retention behavior over time and identify churn patterns across acquisition cohorts.

---

# Day- 5 :- Customer Lifetime Value (CLTV) Foundation Analysis & Customer Segmentation

## Objective
The objective of this notebook is to build the foundation for Customer Lifetime Value (CLTV) analysis using the Online Retail dataset. In this phase, we calculate customer-level revenue metrics and prepare the dataset for customer segmentation and CLTV modeling.

## Dataset Used
**File:** cohort_prepared_data.csv

This dataset contains:
- Cleaned transaction records
- Customer information
- Cohort analysis variables
- Retention analysis features

## Tasks Performed

### 1. Loaded Cohort Prepared Dataset
- Imported the processed cohort dataset.
- Verified dataset structure, shape, and data types.
- Checked for missing values.

### 2. Dataset Validation
- Confirmed:
  - No missing values
  - CohortIndex range from 1 to 25
  - 5,878 unique customers
  - 36,969 unique invoices

### 3. Revenue Calculation
Created a new column:

Revenue = Quantity × Price

This represents the monetary value generated from each transaction.

### 4. Revenue Analysis
- Calculated total revenue generated by the business.
- Analyzed revenue distribution across all transactions.
- Identified high-value transactions.

### 5. Customer Revenue Analysis
Aggregated customer-level revenue using:

Customer Revenue = Sum of Revenue per Customer

This helps identify the most valuable customers.

### 6. Order Frequency Analysis
Calculated the number of unique invoices per customer to measure customer purchasing behavior.

### 7. Average Order Value (AOV)
Calculated:

AOV = Total Revenue / Total Orders

AOV helps understand average customer spending per order.

## Key Findings

- Total Customers: 5,878
- Total Orders: 36,969
- Total Revenue: 17.37 Million
- Average Order Value (Mean): 385.18
- Highest Revenue Customer Generated: 580,987+

The analysis revealed significant variation in customer spending behavior, indicating strong potential for customer segmentation and CLTV-based marketing strategies.

## Output Generated
- Revenue column created
- Customer revenue table created
- Customer order metrics created
- Average Order Value (AOV) calculated
- CLTV base dataset prepared

---

