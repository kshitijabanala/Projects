# Medicare 2017 Payment Analysis

## Table of Contents
1. [Research Question](#research-question)
2. [Summary](#summary)
3. [Dataset Information](#dataset-information)
4. [Key Insights](#key-insights)
5. [Recommendations](#recommendations)
6. [Implementation](#implementation)
7. [Analysis](#analysis)
8. [Future Work](#future-work)
9. [Conclusion](#conclusion)


## Research Question
**How do provider-related characteristics, such as hospital referral region, DRG definition, and provider state, influence average total Medicare payments for medical services?**

## Summary
This analysis investigates the factors driving variations in Medicare payments using the 2017 Medicare charge data. The dataset includes critical variables related to provider characteristics, discharges, and payment metrics. Using Power BI for visualization, this project identifies top influencers, highlights regional and provider-level disparities, and provides actionable recommendations.

The analysis is augmented with advanced predictive techniques and geospatial trends to uncover key drivers of costs. A Power BI dashboard was created to visually represent findings and allow for dynamic filtering based on user inputs like state, DRG definition, and referral region.

## Dataset Information
- **Source:** Medicare 2017 Charge Data
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

## Key Insights
### 1. **Top Influencers of Average Total Payments**
   - **DRG Definition Impact**: Procedures under DRG 001 (e.g., heart transplants) are associated with significantly higher total payments, increasing by approximately $253.5K compared to other categories.
   - **Hospital Referral Regions**: Metropolitan regions like Chicago and Houston have higher referral volumes, correlating with elevated payments.

### 2. **Geographic Trends**
   - States such as **California** and **Texas** show notably higher average total payments, reflecting regional cost differences or higher service demand.

### 3. **Provider-Level Variations**
   - **Specialized Providers**: Facilities such as **US PAIN & SPINE HOSPITAL** and **WOMAN'S HOSPITAL OF TEXAS** report the highest total payments, driven by specialized care and patient demographics.

### 4. **Volume vs. Payments**
   - Total discharges do not always align with higher payments. High-payment DRGs often involve complex procedures rather than volume.

## Recommendations
### Short-Term Recommendations
1. **Standardize Reporting**: 
   - Implement uniform metrics for providers to ensure consistent reporting across regions.
   - Use DRG-specific benchmarks to identify payment outliers.

2. **Focus on High-Payment Regions**:
   - Investigate metro areas like Chicago and Houston for inefficiencies or disparities.
   - Promote equitable distribution of Medicare resources to underserved regions.

### Long-Term Recommendations
1. **Expand Longitudinal Data Analysis**:
   - Integrate data from multiple years to track trends in Medicare payments.
   - Compare evolving payment patterns for DRG definitions and provider regions.

2. **Develop Predictive Models**:
   - Use provider characteristics, DRG definitions, and discharges to forecast future Medicare payments.
   - Apply machine learning algorithms like Random Forest or Gradient Boosting to predict high-cost regions and procedures.

## Implementation
### Power BI Dashboard
- **Visual Elements**:
  - Key Influencers for identifying top factors affecting total payments.
  - Map to highlight state and regional disparities for average total payments
  - Dynamic Filters for user selection of `Provider State` and `Hospital Referral Region`.
  - Cards representing the total avergae coverage charges, average medicare payments, and average total payments.
  - Bar graph represeneing the number of hospital referalls by provider cities along with providers
 

<img width="1294" alt="Screenshot 2024-12-29 at 1 14 47 PM" src="https://github.com/user-attachments/assets/e04ce66d-27f3-4593-93d8-2ca351b6e2fe" />

## Analysis

I aimed to understand how provider-related characteristics, such as hospital referral region, DRG definition, and provider state, influence average total Medicare payments for medical services. One of the key findings was the significant variation in payments across different regions and providers. For instance, the US Pain and Spine Hospital in Houston, Texas, reported the highest average total payments of $72,000. This suggests that specialized procedures, patient demographics, and regional factors play a major role in driving up costs. Houston, with its more diverse medical market and fewer competing providers, likely has less negotiating power, leading to higher payments. On the other hand, regions like Lancaster, San Francisco, and Los Angeles showed significantly lower average total payments, which I believe can be attributed to competitive pricing strategies within larger regional networks. These areas tend to have a higher rate of insured individuals, which likely influences the pricing and payments that providers can charge.

Additionally, I explored how hospital referral patterns differ across cities. I found that Chicago had the most hospital referrals, while Washington had the least. This indicates that Chicago has a more fragmented healthcare system, where patients are frequently referred to specialists or other hospitals for specialized care. It seems that the higher number of referrals in Chicago reflects a system that focuses on specialized care across multiple providers. This can also indicate a lack of injury specific hospitals or a lack of trauma centers with enough resources to treat certain conditions. However, Washington’s healthcare system appears to be more integrated, where patients can typically receive the majority of their care within a single provider network or hospital. This difference in healthcare system models impacts total payments, as more referrals can lead to higher costs due to the need for additional services and care coordination. 

Lastly, there was a significant difference between average Medicare payments, which are about $11,000, and average total payments, which are $27,960. This disparity points to the broader financial challenges faced by hospitals, as Medicare payments are fixed and regulated by the government, while total payments often include contributions from private insurance, out-of-pocket expenses, or other sources. The higher total payments are crucial for hospitals to cover the full cost of care, particularly for services that are not fully reimbursed by Medicare or for patients who do not qualify for the program. This gap highlights the complex relationship between public and private payment structures and the financial sustainability of healthcare providers. In conclusion, my analysis reveals that the variation in Medicare and total payments is influenced by multiple factors, such as regional differences, provider characteristics, and the broader healthcare system models in place. These insights are essential for understanding how payment disparities arise and for addressing the financial challenges within the healthcare system.

## Future Work
1. **Time Series Trends**
   - I would like to extend analysis to include data from multiple years to identify trends and predict future payment patterns.

2. **Enhanced Predictive Modeling**
   - I want to develop and validate predictive models using deep learning for more robust forecasts while incorporating external data (e.g., patient demographics, socioeconomic factors) for meaningful insights.

3. **Integration with Policy Analysis**
   - I want to assess the impact of Medicare policy changes on provider payments and service delivery as well as identify policy interventions to optimize resource allocation.

## Conclusion
My analysis provides a comprehensive overview of Medicare payments and the key drivers behind these costs. By leveraging advanced analytics and visualization tools, I have been able to identify the main factors influencing the variation in Medicare payments, such as regional differences, provider practices, and the role of private insurance in supplementing Medicare reimbursements. Through this approach, I have uncovered valuable insights into how these factors interact and contribute to the overall cost structure within the healthcare system. In particular, I have highlighted areas where disparities exist between Medicare and total payments, offering actionable insights for stakeholders such as policymakers, healthcare providers, and insurers. These insights can help guide future decisions to improve cost efficiency, reduce payment disparities, and enhance the overall healthcare delivery model. By understanding these underlying drivers, stakeholders can better align their strategies to ensure more equitable and sustainable healthcare outcomes.
