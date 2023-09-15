# Valmet Sensor Data Analysis

## Problem Statement

The objective of this analysis is to understand the factors influencing paper roughness (Sensor Name: Roughness) and develop a predictive model for it. Roughness is a critical quality measurement taken in the laboratory for each paper roll produced. However, the factory is interested in predicting roughness based on sensor data.

The primary goals are as follows:

1. Identify the key variables that impact Roughness.
2. Create a quantitative model that correlates Roughness with variables like 'Dry Weight,' 'Moisture 1,' 'Moisture 2,' 'Coat Weight 1,' 'Basis Weight,' and others.
3. Assess the accuracy of the predictive model.

## Approaches

Two distinct approaches were employed to address missing data and construct predictive models:

### Approach 1: Handling Missing Values

In this approach, we chose to remove all missing values from the 'Roughness' variable. The steps included:

1. Data preprocessing to manage missing data.
2. Utilizing Recursive Feature Elimination (RFE) to identify crucial features.
3. Employing Linear Regression to establish the predictive model.
4. Evaluating model performance through Mean Squared Error (MSE) and statistical metrics (R-Squared, P-Value).

### Approach 2: Interpolation of Missing Values

In this alternative approach, we opted to interpolate missing values in the 'Roughness' variable. The key steps involved:

1. Data preprocessing with interpolation techniques.
2. Implementing Recursive Feature Elimination (RFE) to select pertinent features.
3. Constructing a Linear Regression model.
4. Model evaluation based on Mean Squared Error (MSE) and statistical indicators (R-Squared, P-Value).

The outcomes of both approaches were analyzed to determine the most effective strategy for handling missing data and building a precise predictive model for paper roughness.

### Approach 3: Random Forest Regression

This approach yielded a relatively better outcome with an R-squared value of 0.7077 and MSE of 0.0297. Feature importances were also examined.


## Recommendations

Drawing from the insights and model outcomes, we can propose recommendations for enhancing paper roughness. Although it is not a very good fit of the moddel with very low **R-Squared** and high **P-Value**. 

Additionally, suggestions for refining the model's performance are also provided.

Here is the linear model equation:
<font color="blue"> 
$ \text{Roughness} = 4.38 - 0.000491 \times \text{Dry Weight} - 0.100099 \times \text{Moisture 2} - 0.018054 \times \text{Coat Weight 1} - 0.118931 \times \text{Filler Amount} + 0.000038 \times \text{Nipload} + 0.001608 \times \text{Press Control} + 0.000043 \times \text{Speed} - 0.004499 \times \text{Dryer Control 2} + 0.000149 \times \text{Water Flow} $</font>

But the **Random Forest Regression** gave a better model and the features coefficients are
Feature Importances:
- Dry Weight: 0.0882
- Moisture 1: 0.0594
- Moisture 2: 0.0863
- Coat Weight 1: 0.0623
- Basis Weight: 0.1296
- Coat Weight 2: 0.0575
- Filler Flume Consistency: 0.0788
- Dryer Control 1: 0.0335
- Filler Amount: 0.0080
- Nipload: 0.1725
- Press Control: 0.0402
- Speed: 0.1048
- Dryer Control 2: 0.0392
- Water Flow: 0.0397


It is acknowledged that there is potential for improvement, and the following options are considered:

1. **Feature Engineering**: Add new features that could better capture the relationships in the data.
2. **Non-Linear Models**: Explore the application of non-linear regression models for improved predictive performance.

