# Diabetes Risk and Management Dashboard Analysis

## Table of Contents
1. [Business Problem](#business-problem)
2. [Research Question](#research-question)
3. [Dataset Overview](#dataset-overview)
4. [Feature Engineering](#feature-engineering)
5. [Results](#results)
6. [Recommendations](#recommendations)
7. [Implementation](#implementation)
8. [Future Work](#future-work)
9. [Conclusion](#conclusion)

----

## 1. Business Problem
Diabetes is a growing public health challenge that significantly impacts individuals and healthcare systems worldwide. Understanding the key factors contributing to the development and management of diabetes is critical for designing effective prevention strategies, improving disease management, and reducing associated healthcare costs.

## 2. Research Question
What factors (quality of life, diet quality, blood pressure, cholesterol risk, socioeconomic status, and medication adherence) contribute most significantly to the development and management of diabetes?

## 3. Dataset Overview
### Data Cleaning
- The `DoctorinCharge` column was removed due to confidentiality concerns.

### Variables Information

### Patient Information
- **PatientID:** A unique identifier for each patient (6000 to 7878).

### Demographics
- **Age:** The patient's age (20 to 90 years).
- **Gender:** The patient's gender:
  - `0`: Male
  - `1`: Female
- **Ethnicity:** The patient's ethnicity:
  - `0`: Caucasian
  - `1`: African American
  - `2`: Asian
  - `3`: Other
- **SocioeconomicStatus:** Socioeconomic status:
  - `0`: Low
  - `1`: Middle
  - `2`: High
- **EducationLevel:** Education level:
  - `0`: None
  - `1`: High School
  - `2`: Bachelor's
  - `3`: Higher

### Lifestyle Factors
- **BMI:** Body Mass Index (15 to 40).
- **Smoking:** Smoking status:
  - `0`: No
  - `1`: Yes
- **AlcoholConsumption:** Weekly alcohol consumption (0 to 20 units).
- **PhysicalActivity:** Weekly physical activity (0 to 10 hours).
- **DietQuality:** Diet quality score (0 to 10).
- **SleepQuality:** Sleep quality score (4 to 10).

### Medical History
- **FamilyHistoryDiabetes:** Family history of diabetes:
  - `0`: No
  - `1`: Yes
- **GestationalDiabetes:** History of gestational diabetes:
  - `0`: No
  - `1`: Yes
- **PolycysticOvarySyndrome:** Presence of PCOS:
  - `0`: No
  - `1`: Yes
- **PreviousPreDiabetes:** History of pre-diabetes:
  - `0`: No
  - `1`: Yes
- **Hypertension:** Presence of hypertension:
  - `0`: No
  - `1`: Yes

### Clinical Measurements
- **SystolicBP:** Systolic blood pressure (90–180 mmHg).
- **DiastolicBP:** Diastolic blood pressure (60–120 mmHg).
- **FastingBloodSugar:** Fasting blood sugar levels (70–200 mg/dL).
- **HbA1c:** Hemoglobin A1c levels (4.0%–10.0%).
- **SerumCreatinine:** Serum creatinine levels (0.5–5.0 mg/dL).
- **BUNLevels:** Blood Urea Nitrogen levels (5–50 mg/dL).
- **CholesterolTotal:** Total cholesterol levels (150–300 mg/dL).
- **CholesterolLDL:** LDL cholesterol levels (50–200 mg/dL).
- **CholesterolHDL:** HDL cholesterol levels (20–100 mg/dL).
- **CholesterolTriglycerides:** Triglycerides levels (50–400 mg/dL).

### Medications
- **AntihypertensiveMedications:** Use of antihypertensive medications:
  - `0`: No
  - `1`: Yes
- **Statins:** Use of statins:
  - `0`: No
  - `1`: Yes
- **AntidiabeticMedications:** Use of antidiabetic medications:
  - `0`: No
  - `1`: Yes

### Symptoms and Quality of Life
- **FrequentUrination:** Presence of frequent urination:
  - `0`: No
  - `1`: Yes
- **ExcessiveThirst:** Presence of excessive thirst:
  - `0`: No
  - `1`: Yes
- **UnexplainedWeightLoss:** Presence of unexplained weight loss:
  - `0`: No
  - `1`: Yes
- **FatigueLevels:** Fatigue levels (0 to 10).
- **BlurredVision:** Presence of blurred vision:
  - `0`: No
  - `1`: Yes
- **SlowHealingSores:** Presence of slow-healing sores:
  - `0`: No
  - `1`: Yes
- **TinglingHandsFeet:** Presence of tingling in hands or feet:
  - `0`: No
  - `1`: Yes
- **QualityOfLifeScore:** Quality of life score (0 to 100).

### Environmental and Occupational Exposures
- **HeavyMetalsExposure:** Exposure to heavy metals:
  - `0`: No
  - `1`: Yes
- **OccupationalExposureChemicals:** Occupational exposure to harmful chemicals:
  - `0`: No
  - `1`: Yes
- **WaterQuality:** Water quality:
  - `0`: Good
  - `1`: Poor

### Health Behaviors
- **MedicalCheckupsFrequency:** Frequency of medical check-ups per year (0 to 4).
- **MedicationAdherence:** Medication adherence score (0 to 10).
- **HealthLiteracy:** Health literacy score (0 to 10).

### Diagnosis Information (Target Variable)
- **Diagnosis:** Diagnosis status for diabetes:
  - `0`: No
  - `1`: Yes

### 4. Feature Engineering
I modified the variables above as follows in order to make my analysis more meaningful. I converted the binary variables into categorical variables so that I could work with the context behind the 0 and 1 values. I also combined certain variables to create new variables, including **Risk Level** by creating BMI ranges and **Age Range** by creating Age ranges and categorizing these variables as specified below. 

#### Demographic Details
- **AgeRange:** Age group:
  - Young Adult: 20 ≤ Age < 35
  - Adult: 35 ≤ Age < 50
  - Middle-Aged: 50 ≤ Age < 65
  - Senior: Age ≥ 65
- **Sex:** Gender as Male/Female.
- **EthnicityDesc:** Ethnicity description (Caucasian, African American, Asian, Other).
- **SocioeconStatus:** Socioeconomic status (Low, Middle, High).
- **Education:** Education level (None, High School, Bachelor's, Higher).

#### Lifestyle Factors
- **SmokingStat:** Smoking status (Yes/No).
- **DietQual:** Diet quality score (0 to 10).
- **SleepQual:** Sleep quality score (4 to 10).
- **BMI Risk Level:**
  - Underweight: BMI < 18.5
  - Normal: 18.5 ≤ BMI < 24.9
  - Overweight: 25 ≤ BMI < 29.9
  - Obese: BMI ≥ 30

#### Medical History
- **DiabetesHist:** Family history of diabetes (Yes/No).
- **GestDiabetes:** History of gestational diabetes (Yes/No).
- **POS:** Presence of PCOS (Yes/No).
- **hypertension_presc:** Hypertension presence (Yes/No).

#### Clinical Measurements
- **BPCategory:** Blood pressure category (Normal, Elevated, High).
- **BloodSugarCategory:** Blood sugar category (Normal, Prediabetic, Diabetic).
- **RenalFunction:** Renal function (Normal, Mild Impairment, Severe Impairment).
- **CholesterolRisk:** Cholesterol risk (Optimal, Borderline, High Risk).

#### Medications
- **AntihypertensMeds:** Antihypertensive medication usage (Yes/No).
- **StatinsUse:** Statin usage (Yes/No).
- **AntiDiabeticMeds:** Antidiabetic medication usage (Yes/No).

#### Symptoms and Quality of Life
- **FreqUrination:** Frequent urination (Yes/No).
- **ExcessThirst:** Excessive thirst (Yes/No).
- **SuddenWeightLoss:** Sudden weight loss (Yes/No).
- **BlurryVision:** Blurred vision (Yes/No).
- **SlowHealSores:** Slow-healing sores (Yes/No).
- **TinglingLimbs:** Tingling in limbs (Yes/No).

#### Environmental and Occupational Exposures
- **HeavyMetalsExpose:** Heavy metal exposure (Yes/No).
- **OccExposureChem:** Chemical exposure (Yes/No).
- **Water:** Water quality (Good/Poor).

#### Health Behaviors
- **MedicationAdherence:** Medication adherence score (0 to 10).
---

## 5. Results

### Quality of Life
- **Key Finding**: Poor quality of life was associated with the highest rate of diabetes diagnoses (789 patients), while better quality of life significantly reduced diabetes prevalence.
- **Interpretation**: Poor quality of life, influenced by stress, sedentary lifestyles, and poor health, directly impacts diabetes risk.

### Diet Quality
- **Key Finding**: Patients with poor diet quality represented the largest group of diabetics (31.13%), while those with good diet quality had the lowest prevalence (20.76%).
- **Interpretation**: Poor diet, characterized by high sugar and fat intake, is a major modifiable risk factor for diabetes.

### Blood Pressure
- **Key Finding**: Normal blood pressure patients accounted for the highest diabetes prevalence (44%), followed by those with high blood pressure (40%).
- **Interpretation**: While blood pressure alone may not determine diabetes risk, its interaction with other factors like cholesterol and diet is significant.

### Cholesterol Risk
- **Key Finding**: Borderline cholesterol risk accounted for the largest share of diabetic patients (844), followed by high cholesterol risk (332).
- **Interpretation**: High cholesterol may worsen insulin resistance, increasing diabetes risk.

### Socioeconomic Status
- **Key Finding**: Diabetes was most prevalent in middle (41.51%) and low (29.64%) socioeconomic groups.
- **Interpretation**: Limited access to healthcare, nutritious food, and education in lower socioeconomic groups increases diabetes risk.

### Medication Adherence
- **Key Finding**: Diabetic patients showed the highest medication adherence rates, but adherence among prediabetic patients was lower, risking disease progression.
- **Interpretation**: Medication adherence is crucial for effective diabetes management and reducing complications.

To answer the research question, Diet quality and medication adherence are the most direct and modifiable contributors to diabetes prevention and management. A healthy, nutrient-rich diet provides a stable blood glucose level, increases insulin sensitivity, and reduces the complications of the disease, while the proper use of medications assures optimal blood glucose levels and reduces the risk of complications. These are very actionable factors that can easily be addressed through education and support. However, SES and quality of life are foundational in that they may impact access to health care, healthy foods, and essential medications. Individuals of lower SES more often have limited health care coverage and problems of food insecurity, while poorer quality of life, sometimes exacerbated by stress and mental health concerns, may impair one's ability to adhere to lifestyle changes and medications. Systemic interventions include educating about affordable healthy eating, subsidized healthcare, community support, and individualized care plans relevant to each patient's life. In the broader sense, systemic policies to help reduce these disparities and promote better outcomes include providing subsidies for healthy food and incentivizing exercise and stress management activities. These factors are related in that increasing SES can increase diet quality and medication adherence, and the treatment of mental health issues can positively impact motivation; thus, all holistic strategies can snowball into larger positive effects. A supportive environment for diabetes management and prevention would include education, policy reforms, and personalized health care, which ultimately would improve the long-term outcome and quality of life.

## 6. Recommendations

1. **Dietary Interventions**:  
   - Promote healthy eating through education and subsidized access to nutritious food for at-risk populations.

2. **Quality of Life Improvements**:  
   - Launch wellness programs focusing on stress management, physical activity, and mental health.

3. **Health Screenings**:  
   - Regularly screen for cholesterol, blood pressure, and blood sugar, particularly in high-risk groups.

4. **Socioeconomic Support**:  
   - Provide financial support and healthcare subsidies to low-income communities to reduce disparities.

5. **Medication Adherence Programs**:  
   - Develop programs to improve adherence among prediabetic patients and those newly diagnosed.

## 7. Implementation
**Data Exploration**: My Power BI dashboard provides insights into the following: 
   - Quality of Life
   - Diet Quality
   - Blood Pressure
   - Cholesterol Risk
   - Socioeconomic Status
   - Medication Adherence

![Screenshot 2025-01-04 at 7 37 41 PM](https://github.com/user-attachments/assets/decc89c8-d1de-4c6c-a39e-33a8d74e5745)


## 8. Future Work

### Advanced Statistical Analysis

1. **Predictive Modeling**
   - Develop predictive models using machine learning techniques like logistic regression, decision trees, and ensemble methods to estimate diabetes risk more accurately.
   - Evaluate models using cross-validation techniques to ensure generalizability.

2. **Multivariate Analysis**
   - Conduct multivariate regression to assess the combined impact of key variables such as diet quality, blood pressure, and socioeconomic status on diabetes risk.
   - Investigate interaction effects between variables like cholesterol levels and medication adherence.

3. **Time Series Analysis**
   - Analyze longitudinal data to track disease progression and identify early warning signs of diabetes onset.
   - Use autoregressive integrated moving average (ARIMA) models for temporal trends in clinical measurements.

4. **Hypothesis Testing**
   - Perform statistical tests (e.g., ANOVA, chi-square, t-tests) to determine significant differences among groups (e.g., diabetes prevalence across income levels).
   - Test the effectiveness of interventions like diet improvement on reducing diabetes prevalence.

5. **Cluster Analysis**
   - Use clustering techniques like k-means or hierarchical clustering to group patients based on similar characteristics (e.g., lifestyle, clinical measurements) and tailor interventions accordingly.

### Exploration of Additional Factors

- **Regional and Cultural Variations**
  - Incorporate geographic and cultural factors to understand regional disparities in diabetes prevalence.
  - Assess how local dietary patterns or genetic predispositions affect diabetes risk.

- **Genetic and Environmental Interactions**
  - Explore how genetic predisposition interacts with environmental exposures (e.g., heavy metals, pollutants) to increase diabetes risk.

- **Behavioral Insights**
  - Study behavioral factors such as stress levels, sleep patterns, and adherence to lifestyle interventions to improve diabetes management strategies.

## 9. Conclusion
This Power BI dashboard highlights the most significant contributors to diabetes development and management, including diet quality, quality of life, cholesterol risk, socioeconomic status, and medication adherence. Addressing these factors through targeted interventions can significantly reduce diabetes prevalence and improve outcomes for those living with the disease. 
