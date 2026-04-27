# A/B Test Analysis and Statistical Significance
> Created with Google Colab, BigQuery and Tableau.

This project focuses on evaluating the effectiveness of marketing and product experiments for a global e-commerce platform. The analysis dives into conversion rate performance across key funnel stages, identifying statistically significant shifts in user behavior. By utilizing the google.cloud.bigquery library for seamless data ingestion, Python for rigorous statistical testing, and Tableau for interactive visualization, this project provides data-driven recommendations for business strategy.  

### **SQL Data Integration:**  
* CTEs 
* Unions 
* Joins
  
### **Libraries Python:**  
* Cloud and Auth: google-cloud-bigquery, google.colab.auth
* Data Manipulation: pandas, numpy.
* Statistical Analysis: statsmodels (proportions_ztest) to calculate p-values and verify the statistical significance of conversion shifts.  

### **Tableau Visualization**  
* Traffic Overview: tracked distribution and balance across groups and channels using Pie chart, Stacked Bar charts, and Line chart.
* Statistical Dashboard: developed an interactive interface with calculation tables and segment filters to evaluate the mathematical significance of results.

### **Analysis Process**  
1. Data Ingestion. Loaded data for four A/B tests from BigQuery via Python, using SQL queries to integrate experiment results and metadata.  
2. Data Transformation and Statistical Processing. Cleaned and reshaped the dataset by splitting it into metrics and sessions tables for proper indexing. After merging and segmenting by test groups, I calculated conversion rates and percentage differences. Finally, I automated the analysis using a Python loop to perform Z-Tests for Proportions via statsmodels, adding p-values and significance conclusions for every metric.  
3. Multi-Segment Geographic Analysis. Applied the same statistical pipeline to analyze results at the continent level. This granular approach helps identify regional success stories that might be hidden in global averages, allowing for targeted strategy implementation in specific markets.
4. Device-Level Performance Evaluation. Extended the analytical pipeline to evaluate results across Desktop, Mobile, and Tablet segments. By isolating these platforms, I identified "winning" device types that showed statistical significance even when global results remained neutral, enabling platform-specific optimization strategies.
5. Interactive Visualization. Exported the processed data to CSV and integrated it into Tableau for final visualization. Developed a two-page interactive dashboard: the first page analyzes traffic distribution and percentage changes between groups, while the second focuses on conversion performance with p-value results at the total, device, and continent levels.
6. Conclusions and Recommendations. Summarized the findings for each test and provided actionable insights for further decision-making based on the calculated statistical results.

### **Insights and Recommendations**  
**Data Quality and Traffic Distribution**  
In all four experiments, traffic distribution was verified as balanced. Analysis confirmed equal proportions across test groups in total, within daily dynamics, and across all key segments, including marketing channels, continents, countries, and devices. This ensures the reliability of the following statistical conclusions.  
✅**Test 1**    
The experiment proved highly effective, demonstrating a confirmed statistical lift in key conversion stages: adding payment information, shipping details, and checkout initiation. This success was primarily driven by a powerful synergy between Desktop users and the European market, where the positive impact was most consistent and significant. In contrast, results for the Mobile and Tablet segments remained inconclusive or neutral. Based on these findings, it is recommended to proceed with a strategic rollout for Desktop users in the European region, while simultaneously refining the approach for mobile platforms to capture similar growth.  
❌**Test 2**     
At the aggregate level, the experiment did not demonstrate statistically significant results. Despite some positive trends in Asia, a substantial negative impact on adding payment information and other metrics was recorded in the Africa region. Due to these inconsistent results and the risks identified in specific markets, implementing the changes at this stage is not recommended; the strategy requires further adjustment.  
❌**Test 3**     
Statistical data confirmed a decline in the begin_checkout conversion rate, which was particularly evident among Mobile and Tablet users. Although a slight uptick was observed in adding payment information, it did not reach the threshold for significance. Given that the overall trend across most regions remains negative, it is advisable to reject the changes, revert to the original interface, and re-evaluate the initial hypothesis.  
⏳**Test 4**    
The experiment led to a notable performance drop in Europe and on Desktop devices, specifically in adding payment information and checkout initiation. However, the Mobile segment proved to be an exception, showing a statistically verified lift in checkout initiation. Therefore, the global rollout should be halted. It is, however, appropriate to conduct a separate, targeted test for Mobile users with a larger sample size to validate and scale this positive effect.
## [Interactive Dashboards (Tableau)](https://public.tableau.com/app/profile/angela.krupa/viz/ABTestDistributionandAnalysis/ABtest#2)  

**A/B Test Distribution**  
<img width="999" height="1499" alt="AB test" src="https://github.com/user-attachments/assets/eaaeb6ad-b5d1-4db5-b4c9-cc2a41ea2a47" />

**Statistical Significance Report**  
<img width="999" height="1499" alt="Metrics" src="https://github.com/user-attachments/assets/93a70a2a-bbbf-4955-8616-a608573a72f9" />




