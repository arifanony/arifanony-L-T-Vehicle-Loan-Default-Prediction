# Vehicle Loan Default Prediction
This  project was done after i gain my knowledge on Data Science in Great Lakes University (GREAT LEARNING)

## Business Problem
- Financial institutions incur significant losses due to the default of vehicle loans. This has led to the tightening up of vehicle loan underwriting and increased vehicle loan rejection rates. This warrants a study to estimate the determinants of vehicle loan default. The need for a better credit risk scoring model is also raised by these institutions.
- Analyzing this will help the financial institutions to minimize the loan default rates, which helps us gain a customer base by providing the loans to correct persons.  

## Project Overview
- The objective of the problem is to accurately predict the probability of loanee/borrower defaulting on a vehicle loan in the first EMI (Equated Monthly Instalments) on the due date.
- Performed EDA to understand the relation of target variable with the other features.
- Statistical Analysis techniques like ANOVA for numerical and Chi-square for the categorical variables were performed to find the significance of the features with respect to the target.
- Base Models were built in Logistic Regression, Random Forest, KNN and LightGBM with Kfold cross-validation.
- Created new features like age at the time of disbursement, disbursement month, etc.
The dataset represents Vehicle Loan Default of L&T financial institution. 

## Dataset Description
The dataset represents Vehicle Loan Default of L&T financial institution. There are 2,33,134 records and 42 columns
Following Information regarding the loan and loanee are provided in the datasets:
- Loanee Information (Demographic data like age, Identity proof etc.)
- Loan Information (Disbursal details, loan to value ratio etc.)
- Bureau data & history (Bureau score, number of active accounts, the status of other loans, credit history etc.)

## EDA
Univariate, Bivariate and Multivariate Analysis were performed to bring out important aspects of data into focus for further analysis. Some of the highlights from EDA are listed below.

![Loan Default](/Images/loan_default1.PNG "Loan Default")
![LTV](/Images/LTV_with_target.PNG "LTV")
### Inference
- The count of non defaulters is more than defaulters where 0 (78.29%) is a non defaulter and 1 (21.71%) is a defaulter in the Loan Default countplot.
- From the distribution plot, it is clear that as the LTV increases the persons probability of defaulting the loan also increases. 
Therefore higher the LTV higher are the chances of a person defaulting the loan.


![Bivariate](/Images/Bivariate_Analysis.png "Bivariate Analysis between Disbursed Amount and Asset Cost")

### Inference 
- As the disbursed amount increases the asset cost too increases and there are no defaulters as the disbursed amount increases. 

![Bivariate_2](/Images/Bivariate_CNS.PNG "Bivariate Analysis between CNS Score and CNS Score Description")
### Inference 
- As the risk increases the score decreases. The person who has a higher score might tend to be a non defaulter while the person having a low score might be a defaulter.

## Statistical Data Analysis
### ANOVA for Numerical Columns
- Since our target variable is dichotomous and to find whether the feature is significant or not, we did a oneway-anova test to find out the significance of the feature.

![ANOVA](/Images/oneway_anova.PNG "ANOVA Test")
- All our variables have rejected the null hypothesis and the hypothesis is in favor of alternate hypothesis which states that the mean of two groups are not equal which will help in splitting our target variable. 

### ChiSquare for Categorical Columns
- The Chi-Square test of independence is used to determine if there is a significant relationship between two nominal (categorical) variables.
![Chi Square](/Images/chisquare.PNG "Chi Square Test")
- From the test, we can see Pan flag, Unique_id, mobileflag and Sec.Overdue.Accts have failed the test and so they are insignificant variables to the target variable.

## Evaluation Metric
- ROC AUC-Score was chosen as the metric for the models.

## Models
Here we are trying Linear, distance and tree-based models in the conviction which splits the target variables at its best. Since the metric of interest for the problem statement is AUC, from the below output we can conclude that tree based generally outperforms linear based models hence we would be using tree-based model for our further analysis.
- **Logistic Regression ROC AUC SCORE:** 0.55
- **KNN ROC AUC SCORE:** 0.52
- **Random Forest ROC AUC SCORE:** 0.60
- **KNN Classifier ROC AUC SCORE:** 0.55

<!-- ## Final Model
By comparing ROC and Accuracy score results of models and then we choose the best model as LightGBM, having the best evaluation scores.

![LightGBM](/Images/Lgbm.PNG "Score for LGBM") -->

## Conclusion
- In this project Vehicle loan defaulters in the first EMI for L&T have been determined. The best performing models were ensemble-based models.
- The data seems to exactly mimic the real-life scenario which is very evident since there many zero values present which corresponds to first-time customers.

## References
1. https://www.chicagofed.org/~/media/publications/economic-perspectives/2008/ep-3qtr2008-part2-agarwal-etal-pdf.pdf 
2. https://www.paisabazaar.com/car-loan/6-factors-that-affect-car-loan-interest-rates/

