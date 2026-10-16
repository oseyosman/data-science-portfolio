# IT 540 Data Science — Final Project Report
## Analysis of Birth Outcomes and Prenatal Care Disparities by Michigan City (2014)

**Student**: Osman Yildiz  
**Course**: IT 540 Data Science, Walsh College  
**Date**: Fall 2025  

---

### 1. Introduction & Dataset Description
This study examines municipal disparities in maternal and infant health across the state of Michigan using public health data from 2014 provided by the Michigan Department of Community Health. The dataset contains records for municipalities across Michigan with vital birth statistics, including:
* **Total Births** per municipality
* **Demographic Breakdown**: Non-Hispanic White, Non-Hispanic Black, Hispanic
* **Adverse Outcomes**: Inadequate Prenatal Care (Kotelchuck Index), Low Birth Weight (<2,500g), and Teen Mothers (ages 15–19)

To ensure statistical reliability and prevent small-number volatility from skewing percentage rates, the dataset was filtered to municipalities recording at least 50 live births ($N = 367$ cities).

---

### 2. Research Questions (Part A)
1. **Primary Predictive Question**: Can we predict municipal rates of inadequate prenatal care in Michigan using demographic composition and birth outcome indicators?
2. **Exploratory & Inferential Sub-questions**:
   * What demographic characteristics exhibit the strongest correlation with inadequate prenatal care?
   * Can unsupervised learning identify distinct clusters of cities sharing similar maternal risk profiles?

---

### 3. Exploratory Data Analysis (Part B)
* **Distribution**: The distribution of total births per city is highly right-skewed, with a small number of major urban centers (e.g., Detroit, Grand Rapids, Warren) accounting for a large portion of all births.
* **Correlation Findings**:
  * Strong positive correlation ($r = 0.50$) between `% Non-Hispanic Black` population and `% Inadequate Prenatal Care`.
  * Positive correlation between `% Teen Mothers` and `% Inadequate Prenatal Care` ($r = 0.50$).
  * Mild positive correlation with `% Low Birth Weight` ($r = 0.35$).

---

### 4. Formal Statistical Models (Part C)

#### Model 1: Unsupervised K-Means Clustering
Using standardized features (`PctNonHispWhite`, `PctNonHispBlack`, `PctHispanic`, `PctInadequatePrenatal`, `PctLowBirthWeight`, `PctTeenMothers`), an elbow-curve analysis determined $k=4$ as the optimal number of clusters:
* **Cluster 0 ($N=107$)**: Predominantly White rural/small suburban towns with moderate inadequate care rates (28.6%).
* **Cluster 1 ($N=129$)**: Well-resourced suburban communities with the lowest inadequate care rates (24.2%).
* **Cluster 2 ($N=104$)**: Racially diverse mid-sized municipalities with elevated inadequate care rates (35.6%).
* **Cluster 3 ($N=27$)**: Urban centers with high minority representation and severe prenatal care deficits (44.4% inadequate care, 12.2% low birth weight).

#### Model 2: Multiple Linear Regression
A multiple linear regression model was trained using 70/30 train-test partitioning:
* **Training $R^2$**: 0.364 | **Training RMSE**: 7.80%
* **Test $R^2$**: 0.214 | **Test RMSE**: 8.07%
* **Coefficients (Standardized)**:
  * `% Non-Hispanic Black`: $+5.89$
  * `% Teen Mothers`: $+3.47$
  * `% Non-Hispanic White`: $+2.74$
  * `% Hispanic`: $+1.73$
  * `Total Births`: $-0.63$
  * `% Low Birth Weight`: $-0.98$

---

### 5. Interpretation & Limitations (Part D)
* **Did the model answer the question?** Yes. Demographic composition and teen pregnancy rates provide meaningful predictive signals for inadequate prenatal care.
* **Variance Explained**: The test $R^2$ of 21.4% demonstrates that while demographics are correlated with healthcare access, roughly 78.6% of the variance is driven by unmeasured variables.
* **Limitations**:
  1. *Observational Data*: Correlation cannot establish causality. Race is a social construct acting as a proxy for socioeconomic factors.
  2. *Omitted Variables*: Key confounding determinants such as median household income, insurance rates, public transit availability, and distance to the nearest OB/GYN clinic were not captured in this dataset.
  3. *Cross-sectional Limitation*: Data is restricted to a single calendar year (2014).

---

### 6. Conclusions & Public Health Applications (Part E)
* **Risk-Based Resource Allocation**: State health officials can deploy mobile healthcare clinics and prenatal nurse-visiting programs to cities identified in Cluster 3.
* **Integrated School Health Programs**: Because teen pregnancy was strongly linked with inadequate care, integrating prenatal counseling into high school wellness centers would have outsized positive returns.
* **Future Work**: Linking this dataset to US Census American Community Survey (ACS) income data and Michigan hospital geographic coordinates to build high-precision causal models.
