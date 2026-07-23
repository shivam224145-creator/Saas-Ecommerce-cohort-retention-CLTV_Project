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

# Day 6- CLTV_Calculation_(Purchase Frequency + Customer Lifespan + Historical CLTV)_AND_Customer_Segmentation
## Customer Lifetime Value (CLTV) Calculation & Customer Segmentation

## Objective
The objective of this notebook is to calculate Customer Lifetime Value (CLTV) for each customer and segment customers based on their long-term business value.

## Tasks Performed

### 1. Load CLTV Base Dataset
- Loaded the prepared customer transaction dataset.
- Verified dataset structure, shape, columns, and data quality.

### 2. Revenue Analysis
- Used the Revenue column created in the previous notebook.
- Calculated total revenue generated by each customer.

### 3. Order Analysis
- Calculated the total number of unique orders placed by each customer.
- Generated customer-level order frequency metrics.

### 4. Average Order Value (AOV)
- Calculated Average Order Value using:

AOV = Total Revenue / Total Orders

- Analyzed the distribution of customer spending behavior.

### 5. Purchase Frequency
- Calculated overall purchase frequency using:

Purchase Frequency = Total Orders / Total Customers

### 6. Customer Lifespan
- Estimated customer lifespan using the project dataset.
- Used lifespan as an important component for CLTV calculation.

### 7. Historical CLTV Calculation
Calculated Customer Lifetime Value using:

CLTV = AOV × Purchase Frequency × Customer Lifespan

This provided an estimate of the long-term value generated by each customer.

### 8. Customer Segmentation
- Segmented customers into four groups using quartile-based segmentation (qcut):
  - Segment A → Highest Value Customers
  - Segment B → High Value Customers
  - Segment C → Medium Value Customers
  - Segment D → Low Value Customers

### 9. Segment Analysis
- Compared average CLTV across all segments.
- Evaluated customer distribution across segments.
- Identified high-value customers for retention strategies.

### 10. Save Processed Dataset
Saved final customer-level CLTV dataset:

customer_cltv_segments.csv

## Key Outputs
- Revenue per Customer
- Total Orders per Customer
- Average Order Value (AOV)
- Purchase Frequency
- Customer Lifespan
- Historical CLTV
- CLTV Segmentation (A/B/C/D)

## Business Value
This analysis helps businesses:
- Identify high-value customers.
- Prioritize retention efforts.
- Improve customer relationship strategies.
- Allocate marketing budgets more effectively.
- Focus on long-term customer profitability.

## Conclusion

Successfully calculated Customer Lifetime Value (CLTV) for all customers and segmented them into four value-based groups.

### Key Findings
- Significant variation exists in customer value across the dataset.
- Segment A customers contribute the highest lifetime value and should be prioritized for retention programs.
- Segment D customers represent low-value customers and may require re-engagement strategies.
- The customer base is evenly distributed across all four segments through quartile-based segmentation.

### Deliverables Created
- customer_cltv_segments.csv

---

# Day 7- CLTV_Visualization And Business Insights
## Customer Lifetime Value (CLTV) Analysis & Segmentation

## Objective
Calculate Customer Lifetime Value (CLTV) for each customer and segment customers into different value groups based on their purchasing behavior.

## Dataset Used
cltv_base_data.csv

Shape:
- Rows: 779,425
- Columns: 16

## Steps Performed

### 1. Loaded CLTV Base Dataset
- Imported processed dataset.
- Verified shape, columns and missing values.

### 2. Customer Level Aggregation
Calculated:
- Total Revenue
- Total Orders

for each customer.

### 3. Average Order Value (AOV)
Calculated:

AOV = Revenue / Total Orders

to measure customer spending behavior.

### 4. CLTV Calculation
Created a simplified CLTV metric using:

CLTV = AOV × Total Orders × Average Purchase Frequency

### 5. CLTV Segmentation
Customers were divided into:

- Segment A (Highest Value)
- Segment B
- Segment C
- Segment D (Lowest Value)

using quartile-based segmentation.

### 6. Segment Performance Analysis
Analyzed:

- Revenue Contribution
- Average Orders
- Average AOV
- Average CLTV

for each segment.

### 7. Pareto Analysis
Validated the 80/20 principle.

Key Finding:
Approximately 23% of customers generated nearly 80% of total revenue.

### 8. Customer Strategy Recommendations
Created business recommendations for:

- Retain Segment A
- Upsell Segment B
- Engage Segment C
- Reactivate Segment D

### 9. Visualizations Created
- Revenue Contribution by Segment
- Customer Distribution by Segment
- CLTV Distribution
- Revenue Share Analysis
- Pareto Analysis

### 10. Exported Files
Saved:

- customer_cltv_segments.csv
- segment_summary.csv
- pareto_analysis.csv

for Power BI dashboard development.

## Key Findings

- Segment A generated over 65% of total revenue.
- Average CLTV across customers was approximately 4,898.
- Top customers contributed disproportionately to revenue.
- Around 23% of customers generated nearly 80% of revenue.

## Outcome

Successfully built a customer segmentation framework using CLTV analysis that can support retention, upselling, and targeted marketing strategies.

---

# Day 8 :- Customer Segmentation Analysis & Business Insights

## Objective
The objective of this notebook is to analyze Customer Lifetime Value (CLTV) segments, evaluate customer contribution to revenue, identify high-value customers, perform Pareto Analysis, and generate business recommendations for customer retention and growth strategies.

## Dataset Used
**File:** customer_cltv_segments.csv

This dataset contains:
- Customer ID
- Revenue
- Total Orders
- Average Order Value (AOV)
- Customer Lifetime Value (CLTV)
- CLTV Segment

## Step 1: Load Customer CLTV Dataset

- Imported required libraries
- Loaded customer_cltv_segments.csv
- Verified dataset shape, columns, data types, and missing values

### Validation Checks
- Dataset loaded successfully
- No missing values detected
- Customer count verified

## Step 2: Segment Performance Analysis

Analyzed CLTV segments:

- Segment A
- Segment B
- Segment C
- Segment D

Calculated:

- Average Revenue
- Average Orders
- Average AOV
- Average CLTV

### Key Observation
Segment A customers generated the highest revenue and CLTV values.

## Step 3: Revenue Contribution Analysis

Calculated:

- Total Revenue by Segment
- Revenue Contribution Percentage

### Findings

| Segment | Revenue Contribution |
|----------|----------|
| A | 65.18% |
| B | 19.55% |
| C | 10.84% |
| D | 4.43% |

Segment A contributes the majority of business revenue.

## Step 4: CLTV Contribution Analysis

Calculated:

- Total CLTV by Segment
- Average CLTV by Segment

### Finding

Segment A customers have significantly higher lifetime value compared to other segments.

## Step 5: Pareto Analysis (80/20 Principle)

Performed Pareto Analysis to identify customers responsible for the majority of revenue.

Calculated:

- Cumulative Revenue
- Cumulative Revenue Percentage

### Key Insight

A relatively small percentage of customers contributes a large share of total revenue.

## Step 6: Top Customers Identification

Identified top customers based on:

- Revenue
- CLTV

Generated Top 10 customer list for business targeting.

## Step 7: Executive Summary

Created management-level KPI summary including:

- Total Customers
- Total Revenue
- Average Revenue
- Average CLTV
- Top Performing Segment

## Step 8: Business Recommendations

Generated segment-wise recommendations:

### Segment A
Retain and reward high-value customers.

### Segment B
Upsell and cross-sell premium products.

### Segment C
Increase engagement through campaigns.

### Segment D
Run reactivation and retention campaigns.

## Step 9: Data Export

Exported final dashboard-ready datasets:

- executive_summary.csv
- business_recommendations.csv

These files will be used in the Power BI dashboard phase.

## Conclusion

Successfully completed customer segmentation analysis, revenue contribution analysis, Pareto analysis, executive KPI generation, and business recommendations. The exported datasets are now ready for dashboard development and business reporting.

---

# Day 9 :- Segment Insights & Business Recommendations Analysis

## Objective
Analyze CLTV customer segments in detail and generate business-focused insights, recommendations, and executive summaries.

## Dataset Used
customer_cltv_segments.csv

Source:
data/processed/customer_cltv_segments.csv

## Tasks Performed

### 1. Data Loading & Validation
- Loaded customer CLTV segmented dataset.
- Verified dataset structure and dimensions.
- Checked column names and data types.
- Confirmed no missing values.

### 2. CLTV Distribution Analysis
- Analyzed overall CLTV distribution.
- Reviewed minimum, maximum, mean, median and quartile values.
- Identified high-value customer outliers.

### 3. Top Customer Identification
- Ranked customers based on CLTV.
- Extracted Top 10 highest CLTV customers.
- Reviewed Revenue and CLTV contribution.

### 4. Revenue Contribution Analysis
- Calculated revenue generated by each segment.
- Calculated CLTV contribution by each segment.
- Compared Revenue % vs CLTV % contribution.

### 5. Segment Performance Evaluation
Generated segment-level KPIs:

- Customer Count
- Customer Percentage
- Average Orders
- Average Revenue
- Average CLTV

Segments:
- A Segment
- B Segment
- C Segment
- D Segment

### 6. Business Insight Generation
Created business interpretations for every segment:

| Segment | Insight |
|----------|----------|
| A | Premium Customers |
| B | Upsell Opportunity |
| C | Growth Opportunity |
| D | Reactivation Target |

### 7. Business Recommendation Framework
Prepared actionable recommendations:

- Retain Segment A Customers
- Upsell Segment B Customers
- Engage Segment C Customers
- Reactivate Segment D Customers

### 8. Executive Summary Creation
Created executive-level KPI summary including:

- Total Customers
- Top Segment
- Highest Revenue Segment
- Highest CLTV Segment

### 9. Data Export
Saved final outputs:

- segment_summary.csv
- business_recommendations.csv

Location:
data/processed/

## Key Findings

- Segment A contributes most revenue and CLTV.
- Segment B customers represent strong upsell opportunities.
- Segment C customers show growth potential.
- Segment D customers require reactivation strategies.
- Revenue distribution is highly concentrated among top customers.

## Outcome

Successfully completed customer segmentation insight generation and business recommendation framework required for the SaaS Ecommerce Cohort Retention & CLTV Analysis project.

---

# Day 10 :- Business Insights & Executive Reporting Analysis

## Objective
Build a business-focused reporting layer on top of CLTV segmentation results to generate executive summaries, customer insights, revenue contribution analysis, and strategic recommendations.

## Step 1: Load Customer CLTV Dataset
- Loaded `customer_cltv_segments.csv`
- Verified shape, columns, and data types
- Reviewed customer-level Revenue, Orders, AOV, CLTV, and Segment data

## Step 2: Executive KPI Analysis
Created high-level business KPIs:
- Total Revenue
- Total Customers
- Average Revenue per Customer
- Average CLTV
- Top Revenue Segment

Generated executive summary table for management reporting.

## Step 3: Revenue & CLTV Contribution Analysis
Calculated:
- Revenue contribution percentage by segment
- CLTV contribution percentage by segment

Key Finding:
- Segment A contributes 65.18% of total revenue
- Segment A contributes 55.48% of total CLTV

## Step 4: Segment Performance Evaluation
Compared:
- Average Revenue
- Average Orders
- Average AOV
- Average CLTV

Across:
- Segment A
- Segment B
- Segment C
- Segment D

## Step 5: Customer Distribution Analysis
Analyzed customer distribution across all segments.

Result:
- Nearly equal customer distribution (~25% each segment)

## Step 6: Revenue vs CLTV Efficiency Analysis
Calculated efficiency gap:

Efficiency Gap = Revenue % − CLTV %

Insights:
- Segment A = Strongest performing segment
- Segments B, C, D = Future growth opportunities

## Step 7: Business Story Framework
Created strategic interpretation table:

- A → Premium Customers
- B → Upsell Opportunity
- C → Growth Opportunity
- D → Reactivation Target

## Step 8: Recommendation Framework
Generated actionable recommendations:

- Retain Segment A Customers
- Upsell Segment B Customers
- Engage Segment C Customers
- Reactivate Segment D Customers

## Step 9: Save Final Outputs
Saved:

- business_story.csv
- business_recommendations_v2.csv

into the processed folder.

## Step 10: Validation & Cross Check
- Verified saved files
- Reloaded files
- Checked shapes and contents
- Confirmed successful storage for Power BI reporting phase

## Outcome
Successfully completed the Business Insights & Executive Reporting layer for the SaaS E-commerce Cohort Retention & CLTV Project. The project now includes customer segmentation, executive KPIs, business recommendations, revenue contribution analysis, and management-ready reporting datasets.

---

