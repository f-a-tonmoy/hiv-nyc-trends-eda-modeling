# HIV Trends in New York City (2016 - 2021)

📊 Analysis of HIV and AIDS diagnosis trends in New York City using NYC Open Data, with a focus on temporal patterns, geographic disparities, and demographic differences. The project applies exploratory data analysis, statistical testing, and machine learning models to better understand persistent public health inequities.

---

## 📌 Overview

HIV and AIDS remain important public health challenges in New York City. Although overall diagnosis rates have declined in recent years, the burden of disease is not evenly distributed across boroughs, neighborhoods, or demographic groups.

This project aims to:
- Examine long-term trends in HIV and AIDS diagnoses  
- Quantify geographic and demographic disparities  
- Test whether observed changes are statistically significant  
- Compare linear models with tree-based machine learning approaches  

The analysis is intended to support data-driven public health insights rather than clinical prediction.

---

## 🗂️ Data Source

- **NYC Open Data**
- Publisher: NYC Department of Health and Mental Hygiene (DOHMH)  
- 🔗 Link: https://tinyurl.com/2tp2zrkr

### 📄 Dataset Characteristics
- Annual records from 2010–2021  
  (Primary analysis focuses on 2016–2021 due to missing earlier years)
- Aggregated by year, borough, neighborhood, sex, and race/ethnicity
- Includes counts and rates per 100,000 population for:
  - HIV diagnoses
  - AIDS diagnoses
  - Concurrent HIV/AIDS diagnoses (late-stage detection)

---

## 🧹 Data Preparation

Key preprocessing steps included:
- Removing duplicate records  
- Converting numeric fields stored as text  
- Cleaning categorical variables and formatting inconsistencies  
- Handling suppressed and missing values  
- Filtering data based on analysis scope (citywide, borough, neighborhood)

The final dataset is analysis-ready and suitable for statistical modeling and machine learning.

---

## 📊 Exploratory Data Analysis (EDA)

EDA was conducted across three primary dimensions.

### ⏱️ Temporal Trends
- Overall decline in HIV and AIDS diagnoses from 2016 to 2020  
- Sharp dip in 2020, likely due to COVID-19 testing and reporting disruptions  
- Partial rebound in 2021  

### 📍 Geographic Patterns
- The Bronx consistently exhibits the highest diagnosis rates  
- Queens and Staten Island show the lowest overall rates  
- Several Bronx neighborhoods repeatedly appear among the most affected  

### 👥 Demographic Disparities
- Males have substantially higher diagnosis rates than females  
- Black and Latino/Hispanic populations experience the highest burden  
- Disparities persist across nearly all boroughs and years  

---

## 📐 Statistical Analysis

The following hypothesis tests were performed:

- **One-sample t-test**  
  Tested whether the decline in HIV diagnoses in 2020 was significantly lower than pre-pandemic years.

- **Paired t-test**  
  Evaluated whether Bronx HIV diagnosis rates were consistently higher than the NYC average.

- **Two-sample t-test (Welch)**  
  Assessed whether Queens had a higher proportion of concurrent HIV/AIDS diagnoses compared to higher-burden boroughs.

---

## 🤖 Modeling

### Linear and Polynomial Regression
- Used to assess overall time trends  
- Identified a statistically significant linear decline in total HIV diagnoses  
- Polynomial terms did not meaningfully improve model fit  

### Tree-Based Models

#### Decision Tree Regression
- Provided interpretable splits across demographic and geographic variables  
- Highlighted neighborhood and race/ethnicity as key drivers  
- Moderate predictive performance (R² ≈ 0.48 after pruning)

#### Random Forest Regression
- Achieved stronger and more stable performance  
- R² ≈ 0.65 for HIV rate prediction  
- Feature importance emphasized race/ethnicity and sex  
- Demonstrated good generalization when predicting an unseen year (2021)

Predicting AIDS diagnosis rates proved more challenging, with lower R² values across all models.

---

## 🔍 Key Findings

- HIV and AIDS diagnoses in NYC have declined overall, but disparities remain  
- The Bronx consistently experiences the highest burden  
- Black and Latino/Hispanic populations and males are disproportionately affected  
- Neighborhood-level variation explains more than borough-level averages  
- Tree-based models outperform linear models for this dataset’s structure  

---

## ⚠️ Limitations

- Limited number of consistently reported years  
- Sparse data for some demographic and neighborhood groups  
- Surveillance data reflects reporting practices rather than random sampling  
- Models underperform for rare, high-rate neighborhoods  

---

## 🚀 Future Work

- Incorporate socioeconomic and healthcare access variables  
- Explore spatial and geographically weighted models  
- Apply gradient boosting methods  
- Extend analysis with additional post-pandemic years  
- Improve modeling of rare high-burden observations  

---

## 🛠️ Tools and Technologies

- **Language:** R  
- **Libraries:** tidyverse, ggplot2, rpart, randomForest, caret  
- **Methods:** EDA, hypothesis testing, regression, decision trees, random forests, cross-validation

---

## 📄 Report

A full written report with figures and detailed methodology is included in this repository.

---

## 👥 Authors

- Fahim Ahamed  
- Anthony Sinopoli  
- Fatima Nasyr
