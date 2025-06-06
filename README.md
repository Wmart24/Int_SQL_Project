# Intermediate SQL - Sales Analysis

## Overview
Analysis of customer behavior, retention, and lifetime value for an e-commerce company to improve customer retention and maximize revenue.

## Business Questions
1. **Customer Segmentation:** Who are our most valuable customers?
2. **Cohort Analysis:** How do different customer groups generate revenue?
3. **Retention Analysis:** Which customers haven't purchased recently?

## Analysis Approach

### 1. {Customer Segmentation Analysis}
- Categorized customers based on total lifetime value (LTV)
- Assigned customers to High, Mid, and Low-value segments
- Calculated key metrics: total revenue

Query: [1_customer_segmentation.sql](1_customer_segmentation.sql)

**Visualization:**

<img src = "images/customer_ltv_pie_chart.png" width ="50%">


**Key Findings:**
- High-value segment (25% of customers) drives 66% of revenue ($135.4M)
- Mid-value segment (50% of customers) generates 32% of revenue ($66.6M)
- Low-value segment (25% of customers) accounts for only 2% of revenue ($4.3M)

**Business Insights:**
- High-Value (66% revenue): Offer premium membership program to 12,375 VIP customers, as losing one customer significantly impacts revenue
- Mid-Value (32% revenue): Create upgrade paths through personalized promotions, with potential $66.6 -> $135.4M revenue opportunity
- Low-Value (2% revenue): Design re-engagement campaigns and price-sensitive promotions to increase purchase frequency

### 2. Cohort Analysis
- Tracked revenue and customer count per cohorts
- Cohorts were grouped by year of first purchase
- Analyzed customer retention at a cohort level

Query: [2_cohort_analysis.sql](/2_cohort_analysis.sql)

**Visualization:**

<img src = "images/customer_revenue_by_first_purchase_year.png">

**Key Findings:**
- Revenue per customer shows an alarming decreasing trend over time
- 2022-2024 cohorts are consistently performing worse than earlier cohorts
- NOTE: Although net revenue is increasing, this is likely due to a larger customer base, which is not reflective of customer value

**Business Insights:**
- Value extracted from customers is decreasing over time and needs further investigation
- In 2023 we saw a drop in number of customers acquired, which is concerning
- With both lowering LTV and decreasing customer acquisition, the company is facing a potential revenue decline

### 3. Customer Retention
- Identified customers at risk of churning
- Analyzed last purchase patterns
- Calculated customer-specific metrics

Query: [3_retention_analysis.sql](3_retention_analysis.sql)

**Visualization:**

<img src = "images/total_customer_retention_and_churn_by_cohort_year.png">

**Key Findings:**
- Cohort churn stabilizes at ~90% after 2-3 years, indicating a predictable long-term retention pattern.
- Retention rates are consistenly low (8-10%) across all cohorts, suggesting retention issues are systemic rather than specific to certain years.
- Newer cohorts (2022-2023) show similar churn trajectories, signaling that without intervention, future cohorts will follow the same pattern.

**Business Insights:**
- Strengthen early engagement strategies to target the first 1-2 years with onboarding incentives, loyalty rewards, and personalized offers to improve long-term retention.
- Re-engage high-value churned customers by focusing on targeted win-back campaigns rather than broad retention efforts, as reactivating valuable users may yield higher ROI.
- Predict & promot churn risk and use customer-specific warning indicators to proactively intervene with at-risk users before they lapse.

## Strategic Recommendations

1. **Customer Value Optimization** (Customer Segmentation)
- Launch VIP program for 12,375 high value customers who drive 66% of revenue to reduce churn and increase retention.
- Introduce personalized upgrade paths for mid value customers to unlock a potential revenue increase from $66.6M to 135.4M.
- Deploy cost effective re-engagement campaigns and promotional offers aimed at low value customers to encourage repeat purchases.

2. **Cohort Performance Strategy** (Customer Revenue by Cohort)
- Prioritize re-engagement efforts for 2022-2024 cohorts through personalized communication and incentives.
- Introduce loyalty or subscription models to boost long term engagement and stabilize revenue from newer cohorts.
- Analyze and replicate successful retention tactics from top performing 2016-2018 cohorts to improve outcomes in recent years.

3. **Retention & Churn Preventions** (Customer Retention)
- Focus on the first 1-2 years of the customer journey with strong onboarding flows, loyalty rewards, and personalized outreach.
- Launch high impact win back campaigns for churned high value customers to regain lost revenue more efficiently.
- Develop a proactive churn prediction system using behavioral indicators to intervene before customers disengage. 

## Technical Details
- **Database:** PostgreSQL
- **Analysis Tools:** PostgreSQL, DBeaver, VS Code
- **Visualization:** ChatGPT
