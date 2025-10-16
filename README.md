# Overview

This project analyzes the results of an A/B test conducted by the Global Benefits Insurance Company (GBIC) to evaluate the impact of a new “Big Bills” payment method on customer behavior and business outcomes. The analysis focuses on conversion, premium collection, loss ratios, and cancellation rates to determine whether the 1.5× first-month payment plan performs better than the existing 1/6 upfront method.

# Project Components

__1. Data Modeling__  
Created a relational schema joining three core datasets — Account, Quote, and Policy — to represent the customer funnel from account creation through policy purchase.  
Established relationships via `account_id` and `quote_id` keys.

__2. Data Engineering__  
Built SQL table schemas with correct data types (numeric, boolean, datetime).  
Implemented joins and filters to align Test vs. Control groups, with eligibility logic (`big_bill_eligible`).  
Validated data integrity and handled missing values and outliers.

__3. Data Analysis__  
Performed SQL-based analysis to compute key business metrics:
- Quote → Policy conversion rate 

- Collected premium per policy

- Loss ratio and claim severity  

- Cancellation rate and bad-debt percentage  

- Additional metrics: claims frequency, average policy premium, and total premium by group

# Files
__GBIC_ABTest_Analysis.sql:__ SQL queries used to generate metrics for each experimental group.  
__GBIC_Dashboard.png:__ Sample visualization showing Test vs. Control metric comparisons.  
__Mock Datasets (.csv):__ Account, Quote, and Policy tables used for analysis (not included here).

# Key Features
__Experiment Verification:__ Confirmed group assignment and eligibility consistency.  
__Metric Comparison:__ Evaluated performance across Test and Control for all funnel stages.  
__Outlier Detection:__ Identified and removed extreme loss values affecting averages.  
__Visualization:__ Built Mode Analytics dashboards to illustrate key differences across metrics.

# Dependencies
__SQL Environment:__ Snowflake / PostgreSQL for query execution.  
__Visualization:__ Mode Analytics (for multi-metric dashboards).  
__Data Modeling:__ ERD outlining Account → Quote → Policy relationships.  
__CSV Integration:__ Source data imported into relational tables.

# Technologies Used
__SQL:__ For metric calculation and joins.  
__Mode Analytics:__ For visual dashboards.  
__Python / Excel (optional):__ For data validation and descriptive statistics.

# How to Use
1. Clone this repository to your local environment.  
2. Upload the CSV datasets into your SQL environment.  
3. Run the `GBIC_ABTest_Analysis.sql` file to recreate all calculated metrics.  
4. Export results into Mode or another BI tool to visualize Test vs. Control outcomes.  
5. Review the metrics to identify which payment method performs better across conversion, revenue, and risk.

# Results Summary
The Test group (1.5× first-month “Big Bills” plan) collected higher premiums per policy and showed no significant increase in losses.  
However, conversion from quote to policy declined by roughly 10 percentage points.  
Overall, the Big Bills plan improves per-policy profitability but reduces total customer acquisition.  
Recommendation: maintain the 1/6 upfront plan for broader conversions while selectively offering Big Bills to high-value or low-risk segments.
