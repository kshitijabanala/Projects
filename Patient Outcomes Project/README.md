# Medicare 2017 Payment Analysis

## Table of Contents
1. [Business Problem](#business-problem)
2. [Analysis Process](#analysis-process)
3. [Results](#results)
4. [Recommendations](#recommendations)
5. [Implementation](#implementation)
6. [Future Work](#future-work)
7. [Conclusion](#conclusion)

---

## Business Problem
Understanding the drivers of variation in Medicare payments is critical for ensuring cost efficiency and equitable distribution of resources in the healthcare system. This analysis focuses on how provider-related characteristics, such as hospital referral regions, DRG definitions, and provider states, influence the total Medicare payments for medical services. By identifying key factors contributing to payment disparities, the goal is to provide actionable insights to optimize payment structures and improve healthcare delivery.

### Research Question
**How do provider-related characteristics, such as hospital referral region, DRG definition, and provider state, influence average total Medicare payments for medical services?**

## Analysis Process
### Data Exploration
The dataset used is the **Medicare 2017 Charge Data**, which includes the following key variables:

- **Variables Used:**
   - **`DRG Definition`**: Diagnosis-Related Group (DRG) is a code and description of a medical service or procedure.
  - **`Average Coverage Charges`**: Charges by hospitals for a specific DRG procedure before reimbursements.
  - **`Average Medicare Payments`**: Payments made by Medicare post-adjustments for a specific DRG.
  - **`Average Total Payments`**: Total payments for a DRG procedure, including non-Medicare sources.
  - **`Provider ID`**: Unique identifier for each healthcare provider.
  - **`Total Discharges`**: Number of patients discharged for a specific DRG.
  - **`Hospital Referral Region`**: Market area for healthcare referrals.
  - **`Provider City`**, **`Provider State`**, **`Provider ZIP Code`**, and **`Provider Street Address`**: Geographical location data for providers.
- **Target Variable:** `Average Total Payments`

The key variables are: 
- **Provider Characteristics**: DRG Definition, Provider ID, Provider State, and Referral Region.
- **Payment Metrics**: Average Coverage Charges, Average Medicare Payments, and Average Total Payments.
- **Patient Metrics**: Total Discharges.

### Methodology
1. **Data Cleaning**: Ensured consistency in variable formats and handled missing values.
2. **Visualization**: Leveraged Power BI for creating dashboards to represent insights dynamically.
3. **Statistical Analysis**: Examined relationships between provider characteristics and payment metrics using regression and correlation analysis.
4. **Geospatial Trends**: Mapped regional disparities in payments to identify high-cost areas.
5. **Predictive Modeling**: Built models to forecast high-cost regions and procedures based on provider characteristics and DRG definitions.

## Results
### Key Findings
1. **Top Influencers of Payments**:
   - **DRG Definition**: High-cost DRGs, such as heart transplants, increase average total payments by approximately $253.5K.
   - **Regional Differences**: Metropolitan areas like Chicago and Houston report significantly higher payments due to demand and provider characteristics.

2. **Geographic Trends**:
   - States like California and Texas show the highest average total payments, linked to higher service demand and cost of living.

3. **Provider-Level Variations**:
   - Specialized hospitals, such as the **US Pain & Spine Hospital**, drive up costs with average payments exceeding $72,000 per procedure.

4. **Payment Disparities**:
   - Average Medicare Payments: $11,000.
   - Average Total Payments: $27,960.
  
I aimed to understand how provider-related characteristics, such as hospital referral region, DRG definition, and provider state, influence average total Medicare payments for medical services. One of the key findings was the significant variation in payments across different regions and providers. For instance, the US Pain and Spine Hospital in Houston, Texas, reported the highest average total payments of $72,000. This suggests that specialized procedures, patient demographics, and regional factors play a major role in driving up costs. Houston, with its more diverse medical market and fewer competing providers, likely has less negotiating power, leading to higher payments. On the other hand, regions like Lancaster, San Francisco, and Los Angeles showed significantly lower average total payments, which I believe can be attributed to competitive pricing strategies within larger regional networks. These areas tend to have a higher rate of insured individuals, which likely influences the pricing and payments that providers can charge.

Additionally, I explored how hospital referral patterns differ across cities. I found that Chicago had the most hospital referrals, while Washington had the least. This indicates that Chicago has a more fragmented healthcare system, where patients are frequently referred to specialists or other hospitals for specialized care. It seems that the higher number of referrals in Chicago reflects a system that focuses on specialized care across multiple providers. This can also indicate a lack of injury specific hospitals or a lack of trauma centers with enough resources to treat certain conditions. However, Washington’s healthcare system appears to be more integrated, where patients can typically receive the majority of their care within a single provider network or hospital. This difference in healthcare system models impacts total payments, as more referrals can lead to higher costs due to the need for additional services and care coordination. 

Lastly, there was a significant difference between average Medicare payments, which are about $11,000, and average total payments, which are $27,960. This disparity points to the broader financial challenges faced by hospitals, as Medicare payments are fixed and regulated by the government, while total payments often include contributions from private insurance, out-of-pocket expenses, or other sources. The higher total payments are crucial for hospitals to cover the full cost of care, particularly for services that are not fully reimbursed by Medicare or for patients who do not qualify for the program. This gap highlights the complex relationship between public and private payment structures and the financial sustainability of healthcare providers. In conclusion, my analysis reveals that the variation in Medicare and total payments is influenced by multiple factors, such as regional differences, provider characteristics, and the broader healthcare system models in place. These insights are essential for understanding how payment disparities arise and for addressing the financial challenges within the healthcare system.


### Insights
- **Referrals and Costs**: Chicago has the most hospital referrals, reflecting a fragmented healthcare system. In contrast, Washington's integrated system leads to lower total payments.
- **Public vs. Private Contributions**: Total payments often depend on private insurance or out-of-pocket expenses, highlighting gaps in Medicare reimbursements.

## Recommendations
### Short-Term
1. Standardize reporting metrics across regions and use DRG-specific benchmarks to identify outliers.
2. Investigate high-payment regions for inefficiencies and disparities, promoting resource equity.

### Long-Term
1. Integrate multi-year data to track trends and predict future payment patterns.
2. Develop predictive models using advanced machine learning techniques to identify high-cost regions and procedures.

## Implementation
### Power BI Dashboard Features
1. **Key Influencers**: Highlight top factors affecting payments.
2. **Geospatial Trends**: Map state and regional disparities.
3. **Dynamic Filters**: Enable users to select provider characteristics dynamically.
4. **Provider Metrics**: Compare referral volumes, charges, and payments.

 <img width="977" alt="Screenshot 2024-12-31 at 2 14 38 PM" src="https://github.com/user-attachments/assets/e960589f-a652-4a53-99c6-752b5277c371" />

## Future Work
1. **Time Series Trends**: Analyze multi-year data to forecast payment patterns.
2. **Policy Impact Analysis**: Assess the effects of Medicare policy changes on provider payments.
3. **Enhanced Predictive Modeling**: Use external data, such as patient demographics, for better forecasts.

## Conclusion
My analysis provides a comprehensive overview of Medicare payments and the key drivers behind these costs. By leveraging advanced analytics and visualization tools, I have been able to identify the main factors influencing the variation in Medicare payments, such as regional differences, provider practices, and the role of private insurance in supplementing Medicare reimbursements. Through this approach, I have uncovered valuable insights into how these factors interact and contribute to the overall cost structure within the healthcare system. In particular, I have highlighted areas where disparities exist between Medicare and total payments, offering actionable insights for stakeholders such as policymakers, healthcare providers, and insurers. These insights can help guide future decisions to improve cost efficiency, reduce payment disparities, and enhance the overall healthcare delivery model. By understanding these underlying drivers, stakeholders can better align their strategies to ensure more equitable and sustainable healthcare outcomes.
