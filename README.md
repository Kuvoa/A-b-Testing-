# 🚂 A/B Test Analysis (Fast Food Marketing Campaign)

### 📊 Project Overview

This project conducts a comprehensive A/B Test analysis using the Fast Food Marketing Campaign dataset. The primary objective was to determine the most effective marketing promotion among three distinct options in increasing sales across multiple locations.

### 🚀 Key Analysis Steps

1. **Data Extraction:**

   * Queried data from `wa_marketing_campaign` in BigQuery SQL.
   * Focused on key columns: `location_id`, `promotion`, `week`, and `sales_in_thousands`.
   * Aggregated data by `location_id` and `promotion` before analysis.

2. **Metrics Calculation:**

   * Calculated total weekly sales for each promotion at each location.
   * Measured the effectiveness of each promotion using average sales (in thousands).

3. **Pairwise Comparisons:**

   * Conducted statistical testing using pairwise comparisons:

     * **Promotion 1 vs. Promotion 2:** Lift: +22.75%, P-value: 0.0013 (Statistically significant at 0.01 level)
     * **Promotion 1 vs. Promotion 3:** Lift: +4.95%, P-value: 0.4259 (Not statistically significant)
     * **Promotion 2 vs. Promotion 3:** Lift: -14.51%, P-value: 0.0136 (Not statistically significant at 0.01 level)

4. **Statistical Testing:**

   * Used a **99% confidence level** for statistical tests to minimize the risk of Type I errors (false positives).

5. **Analysis and Visualization:**

   * Summarized findings in a PowerPoint presentation for clear communication.

## 📊 Key Metrics

* Promotion 1: Highest sales, significantly outperformed Promotion 2.
* Promotion 2: Weakest performer, with the lowest sales.
* Promotion 3: Viable alternative, similar to Promotion 1 but not statistically better.

## 💡 Recommendations

* **Prioritize Promotion 1:** Scale this promotion to maximize sales.
* **Consider Promotion 3:** Use it as a backup if Promotion 1 is not feasible.
* **Reevaluate Promotion 2:** Adjust its strategy or discontinue it.

## 📌 SQL Query Used

```sql
-- SQL Query for A/B Test Analysis
SELECT location_id, promotion, week, SUM(sales_in_thousands) AS total_sales
FROM `tc-da-1.turing_data_analytics.wa_marketing_campaign`
GROUP BY location_id, promotion, week
ORDER BY promotion, location_id, week;
```

## 🛠️ Tools Used

* **BigQuery SQL:** For data extraction and aggregation.
* **Excel:** For statistical calculations and data validation.
* **PowerPoint:** For visual presentation of findings and recommendations.

## 🚀 Featured Projects Line

* 🔎 [A/B Test Analysis (Fast Food Marketing Campaign)](link-to-your-project) - Conducted a robust A/B test using BigQuery SQL, Excel, and PowerPoint, identifying the most effective marketing promotion.
