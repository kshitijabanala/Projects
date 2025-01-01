# Table of Contents

### 1. Project Overview
### 2. Data Preprocessing and Cleaning
### 3. Literature Review
### 4. Data Modeling
### 5. Model Performance
### 6. Conclusion
---



### 1. Project Overview

For utility and energy production companies, predicting energy usage helps to accurately forecast and manage resources better. New Jersey includes four utilities: Jersey Central Power & Light, Rockland Electric Company, PSE&G and Atlantic City Electric. These utilities provide power to various sections of the state. They require constant knowledge of how much power is being utilized and how much they will need to provide. This project aims to forecast energy usage for New Jersey’s utility companies using weather, date category, and energy usage data. The findings of my project showed the potential of using a LightGBM model for energy forecasting. Here I showed that the most significant features of predicting energy usage are temperature, humidity and pressure. Originally, I assumed that the winter and summer months would prove to be more significant than other features within the date category data. However, they were not as significant as weekday, which was the most significant from this data. Overall, we can hypothesize that energy usage is best predicted through temperature, pressure and humidity. This work can be used by future utilities and energy producers to estimate anticipated demand, ultimately leading to bettering environmental issues and decreasing energy overproduction.


![image](https://github.com/user-attachments/assets/70ba9158-b582-48e9-b537-b32b1afcc68b)


### 2. Data Preprocessing and Cleaning

First, I gathered a mix of data, including past and current energy consumption, weather data, economic indicators, air quality, and the financial status of residents. I cleaned and prepared this data to ensure it’s accurate and ready for analysis. Next, I created and tested different features and expanded upon features with non linear transformation example having both x and x^2 to capture the important factors affecting energy usage. I experimented with various models, like time series and machine learning techniques, to see which ones provide the best predictions. In addition, figuring out which error metrics produce the largest error by experimentation can be a valuable metric that can help determine room for improvement in terms of figuring out why the error is so large and minimizing the errors with the datasets.

#### Weather Data Description 

The data cleaning process for the New Jersey weather datasets involved using R programming for effective data wrangling and anomaly detection through mean value calculations. To address missing values, various imputation methods were employed, including averaging neighboring values and forecasting based on historical trends. Interpolation techniques were applied to create evenly spaced data series, enhancing the usability of forecasting models. Extreme values were carefully evaluated to determine if they were data entry errors or genuine anomalies, with forecasts generated both with and without these outliers to assess their impact. Additionally, the time span of the dataset was critically considered, focusing on current climate conditions while avoiding outdated patterns to improve prediction accuracy. This comprehensive approach aimed to ensure the relevance and reliability of the weather data for forecasting purposes.

#### Economics Data Description 

The economic datasets in our project encompass a wide range of information, including personal income (annual and quarterly), employment, CPI, personal consumption expenditures (PCE), and New Jersey resident population. These datasets are categorized by NAICS industry classifications and include various components such as wages, salaries, and personal income breakdowns. The data spans from 2014 to 2024, with some datasets providing monthly values and others offering annual or quarterly figures. Notably, the datasets contain several types of missing values: "(D)" for confidential information, "(T)" for estimated suppressed wages, "(NM)" for data not meaningful to the analysis, "(L)" for incomes below $50,000, and "NA" values. Initial data cleaning involved removing unnecessary columns such as GeoFIPS, GeoName, Region, TableName, and LineCode, as they contained repetitive or irrelevant information for the analysis of New Jersey-specific data. 

#### Energy Data Description 

The energy datasets in my project cover net generation for biomass, small-scale and utility-scale solar photovoltaic, wind, and customer accounts in New Jersey from 2006 to 2024. The data is organized monthly, with values in thousand megawatthours. Biomass generation ranged from 50 to 90, small-scale photovoltaic from 75 to 410, and utility-scale photovoltaic from 0.03 to 200 thousand megawatthours. Wind data spanned from 2006 to 2024, while customer accounts data covered 2008 to 2024. Missing values, primarily in the first week of each month in 2024, were removed using Python. Outliers were identified in the utility-scale solar dataset, with careful consideration given to their removal due to potential impacts on data analysis and visualization. Data preparation involved reformatting dates, calculating monthly arithmetic means for each energy sector, and creating comparative visualizations, including a combined bar graph for utility and small-scale photovoltaic energy.

### 3. Literature Review

I conducted extensive literature research on time series forecasting and boosted decision tree regression models, focusing on applications in energy forecasting. A key source for our project included "Practical Time Series Forecasting with R" and "A Working Guide to Boosted Regression Trees," which provided foundational knowledge on time series data handling and boosted regression trees. I also examined papers comparing regression models for load forecasting and explored XGBoost through a study on short-term load forecasting. The paper "Energy Consumption Forecasts by Gradient Boosting Regression Trees" was particularly influential, guiding our approach to model development, data preprocessing, and trend analysis. This research helped me understand the importance of weather and calendar data in energy forecasting, the potential impact of events like Covid-19 on data patterns, and the real-world applications of such models. I decided to use the LightGBM package for my initial model development, focusing on weather and calendar data before considering the inclusion of financial data. This literature review has shaped my project direction, highlighting the need for careful data preprocessing, trend analysis, and model comparison to develop an effective energy forecasting model for New Jersey.

### 4. Data Modeling
In my project, I initially explored various modeling techniques for analyzing energy data, including linear regression and neural networks. However, I ultimately decided to use LightGBM, a Boosted Decision Tree Regression model, due to its effectiveness in handling non-linear relationships, missing data, and complex interactions within our energy generation datasets (biomass, solar, wind). Although I encountered some implementation challenges related to dataset references, I actively working to resolve these issues. After I completed the dataset and addressed the initial problems, I optimized the model through hyperparameter tuning and consider incorporating additional financial data to enhance performance.

LightGBM emerged as the best choice for my project due to its numerous advantages over other techniques. Its speed and efficiency are significant, as it utilizes a histogram-based algorithm for node splitting, which reduces computational complexity. Additionally, LightGBM's leaf-wise tree growth strategy leads to faster convergence. The model is also optimized for memory usage, allowing it to handle large datasets with minimal memory requirements . Despite these speed improvements, LightGBM maintains high accuracy levels, effectively managing large-scale and high-dimensional data. Its scalability is enhanced by support for parallel and distributed GPU learning, making it suitable for complex features. Furthermore, LightGBM offers flexibility with customizable hyperparameters and the ability to handle missing data and outliers effectively. These combined features make LightGBM a powerful and efficient choice for my energy data analysis.

#### Datasets Visualizations

![image](https://github.com/user-attachments/assets/782a2051-47c6-4885-ab79-c32e6d924d80)

### 5. Model Performance

#### LightGBM Model

<img width="635" alt="image" src="https://github.com/user-attachments/assets/669c92fc-a8c9-41b2-8fb7-0e40f5fd8948" />

<img width="661" alt="image" src="https://github.com/user-attachments/assets/0b53b5ea-2b2c-49e8-81f1-a79eadf136d1" />

![image](https://github.com/user-attachments/assets/96c6c506-091b-4cd6-a1d9-d1fef64997b2)

![image](https://github.com/user-attachments/assets/02e0c199-11e8-4977-b03c-881a13cfde31)


### 6. Conclusion
My analysis of the feature importance results from the LightGBM load regression model has provided valuable insights into the key drivers of energy consumption for the four utility companies of PSEG, RECO, RCPL, and ACE along with their two utility classes, RSCP and CIEP. Atmospheric pressure emerged as the most significant factor, followed by temperature and humidity, highlighting the critical role of weather conditions in influencing energy demand. These findings emphasize the importance of selecting appropriate features for forecasting models to ensure accurate predictions. In conclusion, we aim to enhance the technical aspects of energy forecasting but also strive to deliver tangible benefits for the people of New Jersey, contributing to a more efficient and sustainable energy future.
