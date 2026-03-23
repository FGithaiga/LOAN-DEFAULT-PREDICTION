# PROJECT TITLE: LOAN DEFAULT PREDICTION

# INTRODUCTION

Loan default prediction is an important problem for financial institutions because it directly impacts profitability and risk management. When borrowers fail to repay their loans, banks and lending institutions suffer financial losses. Accurately identifying high-risk borrowers before loan approval can help institutions reduce defaults and improve lending strategies.

This project uses machine learning techniques to analyze borrower financial and demographic information and predict whether a borrower is likely to default on a loan. The project includes data preprocessing, exploratory data analysis (EDA), handling class imbalance, and building multiple predictive models to identify patterns associated with loan defaults.


# PROBLEM STATEMENT

Financial institutions often face significant losses due to borrowers failing to repay loans. Traditional credit assessment methods may not effectively capture complex relationships between borrower attributes and default behaviour.

This project aims to build predictive models that can accurately classify borrowers as potential defaulters or non-defaulters, enabling data-driven lending decisions.


# OBJECTIVES

<<<<<<< HEAD
1. To analyze borrower demographic and financial characteristics influencing loan default.
=======
1. To understand the characteristics of customers who are more likely to default.
>>>>>>> 43a59af17253c487d11197514533cc0800c78750

2. To explore and analyze loan data to identify patterns and relationships between borrower attributes and loan defaults.

3. To build machine learning models that can classify borrowers as potential defaulters or non-defaulters.

4. To build and evaluate machine learning models for loan default prediction.

5. To provide actionable insights that can support better loan approval decisions.


# DATASET DESCRIPTION

The dataset used in this project contains information about borrowers, their financial status, and loan details. It is designed to support predictive modeling for loan default risk.

**Dataset Overview**

<<<<<<< HEAD
File Name: Loan_default.csv
=======
Filename: Loan_default.csv

Number of Entries: 255,347

Number of Columns: 18
>>>>>>> 43a59af17253c487d11197514533cc0800c78750

Number of Records: 255,347

<<<<<<< HEAD
Number of Features: 18

The dataset includes demographic, financial, and loan-specific attributes that can influence the likelihood of default.

**Features in the Dataset**

LoanID – Unique identifier for each loan

Age – Age of the borrower

Income – Annual income of the borrower

LoanAmount – Total loan amount issued

CreditScore – Credit score of the borrower

MonthsEmployed – Number of months the borrower has been employed

NumCreditLines – Number of open credit lines

InterestRate – Interest rate of the loan

LoanTerm – Duration of the loan in months

DTIRatio – Debt-to-income ratio

Education – Education level of the borrower

EmploymentType – Employment status

MaritalStatus – Marital status

HasMortgage – Indicates whether the borrower has a mortgage

HasDependents – Indicates whether the borrower has dependents

LoanPurpose – Purpose of the loan

HasCoSigner – Indicates whether the loan has a cosigner

Default – Target variable (1 = Default, 0 = No Default)
=======
LoanID: Unique identifier for each loan (object)

Age: Age of the borrower (int)

Income: Annual income of the borrower (int)

LoanAmount: Amount of loan issued (int)

CreditScore: Credit score of the borrower (int)

MonthsEmployed: Number of months the borrower has been employed (int)

NumCreditLines: Number of open credit lines the borrower has (int)

InterestRate: Interest rate of the loan (float)

LoanTerm: Term of the loan in months (int)

DTIRatio: Debt-to-income ratio of the borrower (float)

Education: Education level of the borrower (object)

EmploymentType: Employment status of the borrower (object)

MaritalStatus: Marital status of the borrower (object)

HasMortgage: Indicates if the borrower has an existing mortgage (object)

HasDependents: Indicates if the borrower has dependents (object)

LoanPurpose: Purpose of the loan (object)

HasCoSigner: Indicates if the loan has a cosigner (object)

Default: Target variable indicating if the borrower defaulted (1) or not (0) (int)
>>>>>>> 43a59af17253c487d11197514533cc0800c78750


**DATA PREPROCESSING**

Before building machine learning models, the dataset was cleaned and prepared to ensure reliable analysis and model performance.

**Data Cleaning**

The dataset was inspected for missing values and inconsistencies. No missing values were found in the dataset, so no imputation was required. Data types were also verified to ensure that numerical and categorical variables were correctly identified.

**Feature Preparation**

The identifier column (LoanID) was removed since it does not contribute to predictive modeling. Categorical variables such as Education, EmploymentType, MaritalStatus, LoanPurpose, and other categorical features were converted into numerical format using encoding techniques to allow machine learning algorithms to process them.

**Handling Class Imbalance**

The target variable Default showed an imbalance, with significantly more non-default cases than default cases. This imbalance can bias machine learning models toward predicting the majority class. To address this issue, resampling techniques were applied to balance the dataset and improve the model’s ability to detect default cases.

**Data Splitting**

The dataset was divided into training and testing sets to evaluate model performance on unseen data. Approximately 75% of the data was used for training, while 25% was used for testing.


# EXPLORATORY DATA ANALYSIS (EDA)

Exploratory Data Analysis was conducted to better understand the dataset and identify relationships between features and loan defaults.

**Target Variable Distribution**

The analysis showed that the dataset is imbalanced, with a significantly higher number of non-default loans compared to default loans. This indicates that most borrowers successfully repay their loans.

**Numerical Feature Analysis**

Key numerical variables such as Income, LoanAmount, CreditScore, and MonthsEmployed were analyzed using histograms and boxplots.

**Important observations include:**

Borrowers with lower credit scores tend to have a higher probability of default.
Higher loan amounts relative to income are associated with increased default risk.
Some variables, such as Income and LoanAmount, contain outliers that may influence model predictions.
Correlation Analysis

A correlation heatmap was used to examine relationships between numerical features.

**The analysis showed that:**

CreditScore has a strong negative relationship with loan default.
Borrowers with lower credit scores are more likely to default.
Other features such as Age and NumCreditLines show weaker correlations with the target variable.
Categorical Feature Analysis

Categorical features were explored using count plots and distribution comparisons. Certain employment types and loan purposes showed slightly higher default rates, suggesting that borrower profile characteristics can influence loan repayment behavior.


# MODELING

Several machine learning models were built and evaluated to predict loan defaults.

**Logistic Regression**

We used Logistic Regression as a baseline classification model. It estimated the probability of a borrower defaulting based on the input features. While it performed reasonably well, it struggled to correctly classify the minority default class due to class imbalance.

**Decision Tree Classifier**

The Decision Tree model captured non-linear relationships between variables and provided interpretable decision rules. However, without careful tuning, decision trees may overfit the training data.

**Random Forest Classifier**

Random Forest, being an ensemble method that combines multiple decision trees, produced the best overall performance. It improved predictive accuracy and reduced overfitting by averaging predictions across multiple trees.

# MODEL EVALUATION

The models were evaluated using several performance metrics:

Accuracy – Measured overall correctness of predictions.

Precision – Indicated how many predicted defaults were actually defaults.

Recall – Measured how well the model detects actual defaults.

F1 Score – Balanced precision and recall.

Overall model accuracy ranged between 68% and 70%, with Random Forest providing the best balance between performance metrics.

# KEY FINDINGS

Several important insights emerged from the analysis:

1. The dataset contains a significant class imbalance, with more non-default loans than default loans.

2. CreditScore is one of the strongest predictors of loan default.

3. Borrowers with high loan amounts relative to their income show a higher likelihood of default.

4. Random Forest demonstrated the best predictive performance among the tested models.

5. Detecting default cases remains more challenging due to the imbalance in the dataset.

# RECOMMENDATIONS

**1. For Financial Institutions**
Pay closer attention to borrowers with low credit scores and high debt-to-income ratios, as they present higher default risk.
Implement predictive models such as Random Forest to assist in loan risk assessment and approval decisions.

**2.For Stakeholders**
Use these insights to guide lending policies,reduce financial risk,and optimize loan approval strategies.

**3.For Students**
They should apply more advanced imbalance handling techniques such as SMOTE.
Perform hyperparameter tuning to further improve model performance.
Explore additional features such as borrower transaction history or repayment behavior.

<<<<<<< HEAD
=======
Collect more data to improve prediction of default cases.

Address class imbalance with techniques like SMOTE or weighted models to improve recall for defaults.

Regularly retrain models to capture evolving borrower behaviors and economic conditions.

3. For Stakeholders:

Use these insights to guide lending policies, reduce financial risk, and optimize loan approval strategies.
>>>>>>> 43a59af17253c487d11197514533cc0800c78750
