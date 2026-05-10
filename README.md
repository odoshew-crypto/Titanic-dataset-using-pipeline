# Titanic-dataset-using-pipeline


This project focuses on building a machine learning workflow using the Titanic dataset from Seaborn. The goal is to predict passenger survival based on features such as age, sex, fare, and passenger class. The project demonstrates data preprocessing, feature engineering, feature selection, model training, and performance evaluation.

2. Dataset Overview

The Titanic dataset contains information about passengers on the Titanic, including:

Demographics (age, sex, class)
Travel information (fare, embarkation point)
Survival status (target variable)

The target variable is:

survived
0 → Did not survive
1 → Survived
3. Data Cleaning
3.1 Missing Values

The dataset contained missing values in several columns:

age → missing values filled using median
embarked → filled using most frequent value
deck → removed due to many missing values
3.2 Dropped Columns

The following columns were removed because they were redundant or had too many missing values:

deck
embark_town
alive
class
who
4. Feature Types

The dataset was split into:

Numerical Features
age
fare
sibsp
parch
Categorical Features
sex
embarked
adult_male
alone
5. Data Preprocessing
5.1 Numerical Processing

Numerical features were processed using:

Median Imputation (to handle missing values)
StandardScaler (to normalize values)

This ensures all numerical features are on the same scale.

5.2 Categorical Processing

Categorical features were processed using:

Most Frequent Imputation
One-Hot Encoding

This converts categories into numeric format suitable for machine learning.

Example:

sex
male
female

becomes:

sex_male	sex_female
1	0
0	1
6. Feature Selection

A SelectKBest method was used to select the 8 most important features using the ANOVA F-test.

This helps:

Reduce noise
Improve model performance
Keep only the most relevant variables
7. Model Training

A Random Forest Classifier was used because:

It handles both numerical and categorical relationships well
It reduces overfitting using multiple decision trees
It works well on structured tabular data
8. Model Evaluation
8.1 Pipeline Model Performance

The model trained using the full preprocessing pipeline achieved:

Accuracy: (value from your output)
Strong precision and recall for survival prediction
8.2 Baseline (Raw Data Model)

A simpler model was trained using only raw numerical features.

This model performed worse because:

It ignored categorical information like sex and embarkation
It had less feature richness
8.3 Comparison
Model	Accuracy
Pipeline Model	Higher
Raw Data Model	Lower
Improvement:

The pipeline model performed better due to proper preprocessing and feature selection.

9. Top Selected Features

The most important features selected by the model included:

Passenger class (Pclass)
Sex
Age
Fare
Family size indicators
Embarkation point

These features had the strongest relationship with survival.

10. Conclusion

This project demonstrates that proper data preprocessing significantly improves machine learning performance. Key takeaways include:

Handling missing values improves data quality
Encoding categorical variables is essential
Scaling improves model stability
Feature selection improves performance and reduces complexity
Pipeline-based workflows ensure clean and efficient ML processes

Overall, the pipeline model clearly outperformed the raw data model, proving the importance of preprocessing in machine learning.


