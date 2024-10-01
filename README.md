# Problem Statement

## Context
Jamboree, a leading test preparation and admissions counseling company, has introduced a feature on their website that allows students to estimate their probability of gaining admission to Ivy League colleges. This feature is designed to reflect the admissions landscape from an Indian perspective, helping students assess their chances based on academic and extracurricular profiles.

To enhance this tool, Jamboree seeks to better understand the key factors influencing graduate admissions. The objective of this analysis is twofold: 
1. Identify and analyze the factors that significantly impact admissions decisions.
2. Develop a predictive model to estimate a student's chances of admission based on these factors.
## Dataset Link
The dataset used for this analysis can be found on Kaggle: [Jamboree Education Linear Regression Dataset](https://www.kaggle.com/code/ankur561999/jamboree-education-linear-regression/input)
## How Can You Help?
Your analysis will provide insights into the importance of various factors such as GRE scores, TOEFL scores, CGPA, research experience, and more. This will assist Jamboree in refining their admissions prediction tool and guide students on how to improve their profiles for better admission chances.

## Concepts, Algorithm, and Technologies Used

### Language:
- **Python**

### Modules:
- **NumPy**: For numerical computations and array operations.
- **Pandas**: For data manipulation, cleaning, and analysis.
- **Matplotlib**: For static visualizations to explore data distributions and relationships.
- **Seaborn**: For enhanced data visualizations, especially for exploring relationships between variables.
- **Scikit-learn (sklearn)**: For implementing and evaluating machine learning models, including linear regression.
- **SciPy**: For performing statistical tests, such as the Goldfeld-Quandt test for homoscedasticity.

### Algorithm:
- **Linear Regression**: To model the relationship between the target variable (Chance of Admit) and predictor variables (GRE Score, TOEFL Score, CGPA, etc.). This includes both standard linear regression and Ridge regression (L2 regularization).

### Concepts:
- **Exploratory Data Analysis (EDA)**: To understand the data, check for missing values, detect outliers, and analyze distributions and relationships.
- **Correlation Analysis**: To identify the strength of relationships between different variables.
- **Assumptions of Linear Regression**: Ensuring assumptions such as linearity, no multicollinearity, normality of errors, and homoscedasticity.
- **Model Performance Evaluation**: Using metrics like R², Adjusted R², MAE, MSE, and RMSE to assess model performance.
- **Regularization**: Ridge regression to prevent overfitting.
- **Statistical Testing**: Using tests like the Goldfeld-Quandt test to verify homoscedasticity in the model.

## Insights

### Summarizing Insights

#### Exploratory Data Analysis (EDA) Insights

- **Dataset Overview**:
  - Rows/Samples: 500
  - Columns: 8 (7 features and 1 target)
  - No missing values or duplicates
  - All numeric columns (no encoding required)

- **Distributions**:
  - GRE scores, TOEFL scores, CGPA, and Chance of Admit follow a near-normal distribution.
  - SOP, LOR, and University Rating exhibit normal-like distributions.
  - 56% (280 out of 500 applicants) have research experience.

- **Correlations**:
  - High correlation between GRE Score, TOEFL Score, CGPA, and Chance of Admit.
  - Applicants with research experience tend to have higher scores and admission chances.

#### Linear Regression Insights

- **Model Performance**:
  - **Training R²**: 0.826, **Adjusted R²**: 0.82
  - **Test R²**: 0.797, **Adjusted R²**: 0.779
  - **MAE**: 0.04, **MSE**: 0.003, **RMSE**: 0.059

- **Error Distribution**:
  - Errors are left-skewed and not normally distributed.
  - Higher variance in low admission chances, suggesting a need for more data in this range.

- **Homoscedasticity**:
  - Initially appeared heteroscedastic but confirmed to be homoscedastic via the Goldfeld-Quandt test.

### Model Performance (sklearn)

- **Linear Regression (without Regularization)**:
  - **R²**: 0.797, **Adjusted R²**: 0.781, **MAE**: 0.04, **MSE**: 0.003, **RMSE**: 0.059
- **Ridge Linear Regression (L2-Regularization)**:
  - Results similar to non-regularized model, indicating minimal improvement.
- **Lasso Linear Regression (L1-Regularization)**:
  - Minimal improvement over non-regularized model.

## Conclusion
This analysis highlights the importance of GRE, TOEFL, CGPA, and research experience in predicting the chances of admission, with strong linear relationships and minimal multicollinearity present in the data.

## Recommendations

1. **Focus on High-Impact Features**:
   - GRE Score, TOEFL Score, and CGPA are highly correlated with the chance of admission. Encourage students to prioritize these areas.
   - Emphasize the importance of research experience, as it is associated with better admission chances.

2. **Tailored Student Support**:
   - Develop specialized resources for students with lower scores to improve their GRE, TOEFL, and CGPA.
   - Offer workshops or coaching for students to craft compelling SOPs and secure strong LORs.

3. **Data-Driven Decision Making**:
   - Focus on collecting more data, particularly from applicants with lower admission chances.
   - Regularly update the predictive model as new data becomes available.

4. **Targeted University Applications**:
   - Offer tailored advice on university selection to optimize chances of admission based on students' profiles.


