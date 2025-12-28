Assessing Significant Morphological Factors Associated with the Development of Breast Cancer

Breast cancer is a major global public health concern, where early and accurate diagnosis is essential for improving treatment outcomes and survival rates. However, diagnostic uncertainty often leads to unnecessary biopsies or missed diagnoses. This project evaluates the association between morphological tumor characteristics and the likelihood of developing malignant or benign breast cancer using statistical analysis and machine learning methods.

The analysis leverages the Wisconsin Diagnostic Breast Cancer (WDBC) dataset and integrates descriptive statistics, exploratory data analysis, non-parametric hypothesis testing, correlation analysis, and logistic regression modeling to identify key morphological features associated with breast cancer diagnosis and support data-driven clinical decision-making. 

breast_cancer_applied_stats_Gro…

Introduction

Breast cancer remains one of the most prevalent cancers worldwide, and timely diagnosis plays a critical role in effective treatment and improved survival outcomes. Morphological features derived from fine needle aspirate (FNA) images offer valuable insight into tumor structure and behavior, yet interpreting these features accurately remains challenging.

This study focuses on evaluating whether morphological characteristics of breast tumors are significantly associated with the likelihood of developing malignant or benign breast cancer. By applying statistical testing and machine learning techniques, the project aims to enhance diagnostic precision, support risk stratification, and contribute toward improved patient care through evidence-based analytical approaches. 

breast_cancer_applied_stats_Gro…

Research Question and Hypothesis
Research Question

Do morphological characteristics of breast tumors have an association with the likelihood of developing malignant or benign breast cancer?

Hypotheses

Null Hypothesis (H₀):
There is no significant association between morphological characteristics and the likelihood of developing malignant or benign breast cancer.

Alternative Hypothesis (H₁):
There is a significant association between morphological characteristics and the likelihood of developing malignant or benign breast cancer.

Dataset Description

Dataset: Wisconsin Diagnostic Breast Cancer (WDBC)

Source: UCI Machine Learning Repository

Records: 569 instances

Features: 30 numerical morphological features

Outcome Variable: Diagnosis (Malignant / Benign)

The dataset consists of numerical features extracted from fine needle aspirate (FNA) images of breast masses. It is well-structured, free of missing values and duplicates, and contains mean values representing tumor morphology. 

breast_cancer_applied_stats_Gro…

Variables

Numerical Features:
Radius, texture, perimeter, area, smoothness, compactness, symmetry, fractal dimension (mean values)

Categorical Feature:
Diagnosis (Malignant / Benign)

Feature Engineering Assumption

A new categorical variable, tumor_size, was created using quartile ranges of radius_mean to enhance visualization and subgroup analysis. This categorization was based on assumption due to the absence of measurement units and supporting literature for the mean-based variables. 

breast_cancer_applied_stats_Gro…

Methodology
Data Import

The dataset was imported into R using the read.csv() function and prepared for analysis.

Data Cleaning

Cleaned column names

Verified absence of null and duplicate values

Confirmed dataset dimensions and structure using dim(), head(), and tail()

Outlier Treatment

Box plots were used to identify outliers

Outliers were treated using the 3-sigma rule to minimize skewed influence

Descriptive Statistics

Summary statistics (mean, median, quartiles) were computed for all numerical variables

Diagnosis variable was confirmed as categorical

Normality and Distribution Assessment

Diagnosis values were encoded numerically (M = 1, B = 0) for testing

Shapiro-Wilk tests revealed non-normal distributions across variables

Skewness analysis indicated right-skewed distributions, justifying the use of non-parametric tests 

breast_cancer_applied_stats_Gro…

Exploratory Data Analysis and Visualization

Exploratory analysis was performed using box plots, histograms, scatterplots, and density plots to assess the relationship between tumor morphology and diagnosis.

Key Observations

Malignant tumors tend to have larger tumor size measurements

Clear distributional differences were observed between benign and malignant cases

Perimeter mean demonstrated strong discriminatory power between diagnostic groups

Figures
Figure 2. Tumor Size Distribution

Figure 3. Boxplot of Tumor Characteristics by Diagnosis

Figure 4. Density Plot of Perimeter Mean

Correlation Analysis

A Spearman correlation matrix was generated to evaluate relationships among morphological features.

Findings

Strong positive correlations were observed between:

radius_mean

perimeter_mean

area_mean

compactness_mean

High correlation (≈0.99) between radius and area suggests potential multicollinearity, impacting individual predictive contributions 

breast_cancer_applied_stats_Gro…

Figure 5. Spearman Correlation Heatmap of Tumor Features

Statistical Testing
Mann–Whitney U Test

Non-parametric Mann–Whitney tests were conducted for all numerical features.

All features showed p < 0.05, indicating significant association with diagnosis

Exception: fractal_dimension_mean, which did not show a significant association

Chi-Square Test

A chi-square test was conducted between tumor_size and diagnosis.

Malignant tumors: p < 2.2e-16

Benign tumors: p < 2.2e-16

These results indicate a statistically significant association between tumor size category and diagnosis. 

breast_cancer_applied_stats_Gro…

Machine Learning Model
Logistic Regression

A logistic regression model was implemented to classify breast cancer diagnosis.

Demonstrated high predictive accuracy

Correctly ranked malignant cases with approximately 99.16% probability

Strong alignment between predicted probabilities and observed diagnoses

Figure 7. ROC Curve for Logistic Regression Model

Results and Conclusion

The null hypothesis was rejected, confirming a significant association between morphological features and breast cancer diagnosis

Key predictive features include:

Radius

Texture

Perimeter

Area

Smoothness

Compactness

Symmetry

fractal_dimension_mean did not significantly correlate with diagnosis

Logistic regression demonstrated strong diagnostic discrimination

These findings support the importance of morphological characteristics in breast cancer risk assessment and highlight their role in improving diagnostic accuracy and clinical decision-making.
