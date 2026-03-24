# PROJECT TITLE: LOAN DEFAULT PREDICTION

# INTRODUCTION

Loan default prediction is an important problem for financial institutions because it directly impacts profitability and risk management. When borrowers fail to repay their loans, banks and lending institutions suffer financial losses. Accurately identifying high-risk borrowers before loan approval can help institutions reduce defaults and improve lending strategies.

This project uses machine learning techniques to analyze borrower financial and demographic information and predict whether a borrower is likely to default on a loan. The project includes data preprocessing, exploratory data analysis (EDA), handling class imbalance, and building multiple predictive models to identify patterns associated with loan defaults.


# PROBLEM STATEMENT

Financial institutions often face significant losses due to borrowers failing to repay loans. Traditional credit assessment methods may not effectively capture complex relationships between borrower attributes and default behaviour.

This project aims to build predictive models that can accurately classify borrowers as potential defaulters or non-defaulters, enabling data-driven lending decisions.


# OBJECTIVES


1. To analyze borrower demographic and financial characteristics influencing loan default.

2. To understand the characteristics of customers who are more likely to default.


3. To explore and analyze loan data to identify patterns and relationships between borrower attributes and loan defaults.

4. To build machine learning models that can classify borrowers as potential defaulters or non-defaulters.

5. To build and evaluate machine learning models for loan default prediction.

6. To provide actionable insights that can support better loan approval decisions.


# DATASET DESCRIPTION

The dataset used in this project contains information about borrowers, their financial status, and loan details. It is designed to support predictive modeling for loan default risk.

**Dataset Overview**

Filename: Loan_default.csv

Number of Entries: 255,347

Number of Columns: 18

Number of Records: 255,347

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


# MACHINE LEARNING

The loan default prediction task involves predicting whether a client will default (positive class) or not (negative class) based on their financial and demographic features. Due to the imbalanced nature of the dataset (many more non-defaults than defaults), special techniques were applied to improve model performance on the minority class.

**1. Data Preparation**
The dataset was split into training (80%) and testing (20%) sets, stratified to preserve the class distribution.

Feature scaling was applied to ensure models that rely on distance metrics (e.g., Logistic Regression) perform optimally.

**Handling Class Imbalance**
SMOTE (Synthetic Minority Oversampling Technique) was used on the training data to generate synthetic examples of the minority class (defaults).

This prevents models from being biased toward predicting only non-defaults and improves recall for the positive class.

**3. Model Training**

Three baseline models were trained on the resampled data:

Logistic Regression – a linear model for binary classification.

Decision Tree Classifier – a tree-based model that splits features to separate classes.

Random Forest Classifier – an ensemble of decision trees that improves stability and reduces overfitting.

**4. Threshold Tuning**
Default classification threshold (0.5) was adjusted to 0.4 for all models.

This was done to increase recall for the positive class, prioritizing the detection of potential defaults over minimizing false positives.

**5. Model Evaluation**

Models were evaluated using precision, recall, F1-score, and confusion matrices.

Recall was prioritized due to the high cost of missing defaults.

Precision-Recall curves were plotted to compare model performance on the positive class.


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


