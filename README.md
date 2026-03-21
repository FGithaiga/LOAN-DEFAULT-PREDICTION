# LOAN-DEFAULT-PREDICTION

# INTRODUCTION

The loan default prediction project aims to analyze and predict the likelihood of customers defaulting on their loans using historical loan and customer data. Financial institutions face significant risks when issuing loans, as defaults can lead to substantial losses. By leveraging data science techniques, including data preprocessing, exploratory data analysis (EDA), and machine learning, this project seeks to identify patterns and factors that influence loan defaults.

# PROBLEM STATEMENT

Loan default is a critical challenge for banks and other financial institutions. Approving loans without proper risk assessment can lead to financial losses, affect liquidity, and increase operational costs. Traditional credit scoring methods may not fully capture the complex relationships between customer attributes and default risk.

# OBJECTIVES

1. Tounderstand the characteristics of customers who are more likely to default.

2. To build predictive models that can classify future loan applicants as potential defaulters or non-defaulters.

3. To provide actionable insights for decision-makers in financial institutions, enabling better risk management and loan approval strategies.

4. To improve loan approval decisions using data-driven insights.

5. To identify key factors that increase the risk of default, enabling targeted risk mitigation strategies.

# DATASET DESCRIPTION

The Loan Default Prediction dataset contains detailed information about loans issued by a financial institution. It can be utilized for predictive modelling to understand the factors contributing to loan defaults. The dataset comprises 255,347 entries and 18 columns covering various borrower demographics, financial details, and loan-specific attributes.

**Dataset Overview**

Filename: Loan_default.csv
Number of Entries: 255,347
Number of Columns: 18

**Columns**

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


# DATA PREPROCESSING
The dataset used in this project contains information on loans, including borrower demographics, financial details, and loan outcomes (default vs. non-default). Before modeling, several steps were performed to clean, transform, and prepare the data:

**1. Data Cleaning**

Checked for missing values. The dataset was complete with no missing entries, so no imputation was required.

Verified data types for each column to ensure consistency (e.g., numerical columns like Income and LoanAmount were correctly identified as numeric).

**2.Feature Selection and Engineering**

Identified relevant features that influence loan default, including Age, Income, LoanAmount, CreditScore, MonthsEmployed, and NumCreditLines.

Converted categorical variables into numerical form where necessary using encoding methods (e.g., one-hot encoding or label encoding).

Normalized/standardized numerical features to improve model performance and convergence.

**3.Handling Imbalanced Classes**

The target variable Default was imbalanced, with more non-default cases (0) than default cases (1).

Techniques such as resampling (oversampling the minority class or undersampling the majority class) were applied to balance the dataset and improve model performance.

**4.Data Splitting**

The dataset was divided into training and testing sets to evaluate model performance.

Common splits, such as 75% for training and 25% for testing, were applied to ensure the model could generalize well to unseen data.

**5.Visualization and Exploration**

Explored relationships between features and the target variable using scatter plots, boxplots, and correlation matrices.

Identified key patterns and outliers that informed feature selection and preprocessing choices.


# EXPLORATORY DATA ANALYSIS

Exploratory Data Analysis (EDA) was performed to understand the dataset, identify patterns, and uncover relationships between features and the target variable (Default). Key steps and insights include:

**Target Variable Analysis**

The Default variable is imbalanced, with more non-default cases (0) than default cases (1).

A bar plot of loan default status clearly shows that most borrowers repay their loans, while a smaller portion default.

**Numerical Feature Analysis**

Features like Income, LoanAmount, CreditScore, and MonthsEmployed were analyzed using histograms and boxplots.

Observed outliers in Income and LoanAmount, which may affect model predictions.

Defaulted loans tend to have lower CreditScore and higher LoanAmount relative to Income.

**Correlation Analysis**

A correlation heatmap was used to identify relationships between numerical features.

CreditScore showed a strong negative correlation with Default, indicating that borrowers with lower credit scores are more likely to default.

Some features, like Age and NumCreditLines, showed weaker correlations with default.

Categorical Feature Analysis

Categorical features were analyzed using count plots and cross-tabulations.

Certain employment or financial categories exhibited higher default rates, helping guide feature selection for modeling.

**Insights for Modeling**

Features with high predictive power include CreditScore, LoanAmount, Income, and MonthsEmployed.

The class imbalance needs to be addressed to prevent model bias toward the majority class.

Outliers and skewed distributions were noted for potential preprocessing, such as scaling or transformation.

Outcome: The EDA helped identify the most important predictors of loan default, detect data imbalances, and guide preprocessing decisions to improve model performance.

# MODELING
The processed dataset was used to build and evaluate multiple machine learning models to predict loan defaults:

**Logistic Regression:**

A baseline model to estimate the probability of default.

Performs well on linearly separable features, but struggles with imbalanced classes.

Decision Tree Classifier:

Captures non-linear relationships between features and loan default.

Easy to interpret but prone to overfitting without proper pruning.

**Random Forest Classifier:**

An ensemble of decision trees that improves accuracy and reduces overfitting.

Showed the best overall performance among the models.

**Evaluation Metrics:**

Accuracy: Around 68–70% across models.

Precision & Recall: High precision for non-default loans (0), moderate recall for default loans (1).

F1-Score: Balanced measure of model performance, highlighting challenges with imbalanced data.

# KEY FINDINGS

Most borrowers in the dataset do not default, creating an imbalanced target variable.

Lower CreditScore and higher LoanAmount relative to Income are strong indicators of potential default.

Employment length and number of credit lines show weaker but still relevant correlations with default risk.

Random Forest performed best, balancing precision and recall, making it the most reliable model for predicting defaults.

# RECOMMENDATIONS
1. For the Bank / Lender:

Focus on applicants with low CreditScore or high Loan-to-Income ratios for additional risk assessment.

Use predictive models like Random Forest to flag high-risk loans before approval.

2. For Model Improvement:

Collect more data to improve prediction of default cases.

Address class imbalance with techniques like SMOTE or weighted models to improve recall for defaults.

Regularly retrain models to capture evolving borrower behaviors and economic conditions.

3. For Stakeholders:

Use these insights to guide lending policies, reduce financial risk, and optimize loan approval strategies.
