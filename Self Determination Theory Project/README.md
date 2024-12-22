## Table of Contents

### 1. Project Overview
### 2. Literature Review
### 3. Methodology
### 3. EDA Steps
### 4. ANOVA Statistcial Analysis
### 5. Methodology
### 6. Results

### Project Overview

<p align="center">
  <img src="https://github.com/user-attachments/assets/63e2d676-2d2a-42a8-8f8f-fa08de1be7a6" alt="image" width="700">
</p>

# Self-Determination Theory and Workplace Well-Being

Evidence shows that **Self-Determination Theory (SDT)** is a robust and effective framework for understanding human motivation and well-being, particularly in workplace settings (Deci, 2000). This study builds on that foundation by utilizing data from the **Midlife in the United States (MIDUS)** study, which included a total of **2,344 participants**.

## Central Research Question
Does workplace autonomy, workplace relatedness, and general competence, as conceptualized in Self-Determination Theory, influence employees’ positive affect?

### Operationalization of Variables
- **Autonomy**: Operationalized through *“decision authority”*.
- **Relatedness**: Measured via *“coworker support”*.
- **Competence**: Assessed through *“persistence in goal striving”*.

Each variable was represented as a composite scale comprising several relevant questions/items for each construct. Based on composite mean scores out of 5 for each construct, the factors were re-categorized into three levels: **low**, **medium**, and **high**.

### Measurement of Positive Affect
Positive affect was measured by self-reported ratings of emotions such as:
- Cheerfulness
- Satisfaction
- Feeling calm
- Peacefulness
- Feeling full of life  

These ratings were recorded on a **scale of 1 to 10**.

### Literature Review
Prior investigations studying Self-Determination Theory (SDT), a well-established theory of motivation that has been widely applied across various domains such as health, sports, education, and the workplace (Ntoumanis, 2021). SDT emphasizes the importance of three basic psychological needs which are autonomy, competence, and relatedness, and they are essential for motivation and growth. The main theory behind SDT is that when people’s psychological needs are met in their environment, their motivation becomes more autonomous. A study that was conducted by the National Institute of Health (NIH) where they aimed to investigate how the basic psychological needs impact task performance. Participants were tasked with folding origami puzzles, with some groups receiving support for competence and relatedness, and others not. The results showed that both competence and relatedness enhanced task performance, with competence having a stronger effect. In the second part of the study, participants played Boggle under varying conditions of reward and need support, with performance measured by the number of words found. Similar to the first study, competence support enhanced performance, and intrinsic motivation was a key mediator in the relationship between both competence and relatedness support and task outcomes. According to the NIH, “Both studies confirmed that the need for competence had the strongest positive influence on performance.” (Szulawski, 2021). Since previous literature has shown relatively strong support for SDT, my focus wasn’t only to see if SDT factors impacts positive affect, but also if are any nuanced patterns that previous studies haven’t looked for or found. That said, I will be working from both a confirmatory data analysis (CDA) and exploratory data analysis framework (EDA).

## Methodology
The study employed a **quasi-experimental**, unbalanced design using a **three-way analysis of variance (ANOVA)**.

## Data Cleaning and Recoding
To assess the influence of **workplace autonomy**, **relatedness**, and **competence** on employees' positive affect, the following steps were conducted:

- **Autonomy**: Operationalized through the construct of *“decision authority”* variable in MIDUS.
- **Relatedness**: Operationalized through the construct of *“coworker support”* variable in MIDUS.
- **Competence**: Operationalized through the construct of *“persistence in goal striving”* variable in MIDUS.

Each variable was measured as **composite scales** consisting of several relevant questions in the MIDUS dataset.  

### Positive Affect
Positive affect was operationalized using self-reported items of positive emotions in a MIDUS validated construct of positive affect (**B1SPOSAF**), which included:
- Cheerfulness
- Satisfaction
- Feelings of calm and peacefulness  

Ratings were measured on a **scale from 1-10**. Please see **Appendix A** for detailed item descriptions.

### Recoding
- All three variables—**autonomy**, **relatedness**, and **competence**—were recoded into **categorical levels**:
  - **Low**: Scores < 2.5
  - **Medium**: \( 2.5 \leq \text{scores} < 3.5 \)
  - **High**: Scores ≥ 3.5

- A contingency table confirmed that all 27 combinations of treatments (**3 levels in autonomy × 3 levels in relatedness × 3 levels in competence**) were represented in the data, with no zero cells for any treatment combinations.

- Since ANOVA prioritizes having all treatment combinations, this step ensured the validity of proceeding with the analysis.

## Preliminary Analysis
- Initially, **sex (male/female)** was included as a **block**, where a **partially incomplete block design (ANCOVA)** was considered.
- However, an interaction between sex and the primary factor was detected. To satisfy model assumptions and maintain validity, the blocking factor was removed.

## Study Design
This study is a **quasi-experimental design**:
- Participants were **not randomly assigned** to the levels of the independent variables and were instead surveyed according to specific criteria.  
- Unlike experimental studies, this approach precludes making causal inferences.  

### Covariates
- Covariates, such as financial status, were considered for inclusion. However, many potential covariates were **categorical variables** in the MIDUS dataset.  
- As a result, covariates were omitted from the final study design.

### Unusualness Threshold
An **unusualness threshold of 0.12** was used due to:
- The low-stakes nature of the findings.
- The focus on identifying new potential trends in the data.

## Data Preparation and Analysis
- All data preparation and analysis were conducted in **R**.

### EDA Steps
![image](https://github.com/user-attachments/assets/518401d2-0fc2-4ad1-88db-79fc4da6b3e7)

![image](https://github.com/user-attachments/assets/f0f03267-4ceb-48b4-a668-edcf6aa26cfb)

![image](https://github.com/user-attachments/assets/0d14ae27-0fe8-4852-aeb9-7d2cf6778c23)

![image](https://github.com/user-attachments/assets/a13402a5-1dfc-4585-8405-c80edc289ff1)

![image](https://github.com/user-attachments/assets/e7342dff-64a3-4116-8272-609932b83e93)

![image](https://github.com/user-attachments/assets/3fd02574-3d17-47f6-ba06-3278f452e186)

![image](https://github.com/user-attachments/assets/67e73100-782f-4e85-8892-173b19046dd8)

![image](https://github.com/user-attachments/assets/f9420104-94c6-4d4e-8041-15541a3fb227)

- **Main Effects**:
  - **Autonomy**: \( p = 0.1036 \)
  - **Relatedness**: \( p $\leq$ 0.0001 \)
  - **Competence**: \( p < 0.001 \)
- **Interactions**: No significant interactions were found.

### Interpretation of Results
These findings indicate that autonomy, relatedness, and competence independently contribute to positive affect. Each factor supports well-being without depending on the presence of the others.

![image](https://github.com/user-attachments/assets/738cc2a4-7684-4da7-902b-851d89327e93)

![image](https://github.com/user-attachments/assets/b7227072-3d08-4939-8f8e-5cdeea9416df)

![image](https://github.com/user-attachments/assets/d95be288-40b6-4285-b920-16cbeb29b8e8)

![image](https://github.com/user-attachments/assets/b509d65c-d3f1-4ced-ac11-f3014256e04e)

![image](https://github.com/user-attachments/assets/72e43996-1cc0-4d51-972e-0e8af3221903)

![image](https://github.com/user-attachments/assets/5e99c116-3d09-4787-b683-0ba1a9de7edc)








