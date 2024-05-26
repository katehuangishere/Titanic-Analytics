# Titanic Analytics

## Project Overview
The project aims to construct predictive models to determine which types of people were more likely to survive the Titanic disaster. This is done by analyzing passenger data such as name, age, gender, etc. The project compares various supervised and unsupervised learning methods to identify the most effective approach.

## Data Description
The dataset contains 891 entries with the following attributes:
- PassengerId: A unique identifier for each passenger.
- Survived: Indicates survival status (1 for survived, 0 for did not survive).
- Pclass: Ticket class (1st, 2nd, or 3rd).
- Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked: Other passenger details including demographics and travel specifics.

## Data Preprocessing
1. Initial Setup: The index is set to PassengerId. The target variable is 'Survived'.
2. Handling Variables: Continuous variables (Age, Fare) and categorical variables (Pclass, Sex) were processed. Sex was transformed into a binary variable, and Embarked underwent One-Hot-Encoding.
3. Data Cleaning: Duplicate rows were removed, irrelevant columns (Name, Ticket, Cabin) were dropped, and missing ages were filled with the median value.
4. Scaling: Numerical variables were normalized and mapped into the range [-1, 1].
5. Splitting: The data was split into a training set (80%) and a test set (20%).

## Model Development and Evaluation
- Support Vector Machine (SVM)
  - Features/Target: Defined from preprocessed data.
  - Model Training: Both linear and nonlinear SVM models were trained.
  - Performance: Achieved accuracies of 78.77% (linear) and 80.44% (nonlinear).
- Logistic Regression
  - Configuration: Best parameters found were {'C': 1, 'penalty': 'l1'}.
  - Training and Testing: Model showed a balanced accuracy of approximately 80.45%.
- Gradient Tree Boosting (XGBoost)
  - Optimization: Employed GridSearchCV and KFold for tuning. Eval metrics included prediction error and accuracy.
  - Results: Not explicitly stated, but this model was later identified as the best performer.
- Decision Trees
  - Methodology: Decision trees allowed for easy interpretation and less data preprocessing.
  - Limitations: Prone to overfitting and sensitive to data changes.

## Clustering Analysis
- Methods Used: K-means and hierarchical clustering to evaluate data groupings.
- Observations: Clusters were well-separated though some classes showed overlapping features.

## Conclusions
- Best Model: XGboost with an accuracy of 82.12%.
- Key Factors: Gender, Pclass, Age, Fare, and Embarked location were significant in predicting survival.
