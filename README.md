# A/B Test Analysis (Fast Food Marketing Campaign)

## Project Overview

This project conducts a comprehensive A/B Test analysis using the Fast Food Marketing Campaign dataset. The primary objective was to determine the most effective marketing promotion among three distinct options in increasing sales across multiple locations.

## Key Analysis Steps

1. **Data Extraction**  
   - Queried data from `wa_marketing_campaign` in BigQuery SQL  
   - Focused on: `location_id`, `promotion`, `week`, and `sales_in_thousands`  
   - Aggregated data by `location_id` and `promotion` for analysis  

2. **Metrics Calculation**  
   - Calculated total weekly sales for each promotion at each location  
   - Measured effectiveness using average sales (in thousands)  

3. **Pairwise Comparisons**  
   Conducted statistical testing between each pair of promotions:  
   - Promotion 1 vs. Promotion 2: **Lift: +22.75%**, **P-value: 0.0013** (Statistically significant at 0.01 level)  
   - Promotion 1 vs. Promotion 3: **Lift: +4.95%**, **P-value: 0.4259** (Not statistically significant)  
   - Promotion 2 vs. Promotion 3: **Lift: -14.51%**, **P-value: 0.0136** (Not significant at 0.01 level)  

4. **Statistical Testing**  
   - Used a **99% confidence level** to reduce Type I error risk (false positives)  

5. **Analysis and Visualization**  
   - Findings summarized in a PowerPoint presentation for clarity  

## Key Metrics

- **Promotion 1**: Highest average weekly sales, statistically outperformed Promotion 2  
- **Promotion 2**: Lowest performing promotion across all locations  
- **Promotion 3**: Performed similarly to Promotion 1 but without statistical significance  

## Recommendations

- **Prioritize Promotion 1**: Expand this campaign to drive revenue growth  
- **Consider Promotion 3**: A reasonable alternative when Promotion 1 is not feasible  
- **Reevaluate Promotion 2**: Modify its approach or consider phasing it out  

## SQL Query Used

```sql
-- SQL Query for A/B Test Analysis
SELECT location_id, promotion, week, SUM(sales_in_thousands) AS total_sales
FROM `tc-da-1.turing_data_analytics.wa_marketing_campaign`
GROUP BY location_id, promotion, week
ORDER BY promotion, location_id, week;

---

## Tools Used

- **BigQuery SQL**: Data extraction and aggregation  
- **Excel**: Statistical testing and data validation  
- **PowerPoint**: Visualization and executive summary presentation

## Dataset

Available at:  
[Fast Food Marketing Campaign A/B Test Dataset on Kaggle](https://www.kaggle.com/datasets/chebotinaa/fast-food-marketing-campaign-ab-test)
