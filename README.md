# Are your Employees Burnt Out?

Classification Project - Flatiron Phase 3
Prepared and Presented by:  **_Sarah Zoeller_**

### Business Case   
Due to the COVID 19 pandemic, Large Co. employees have been working from home since April. The company has noticed a decrease in productivity, and suspects it may be due to employee burnout. Large Co. would like to create a model that can predict employee burnout based on various factors, in order to identify and provide support to the employees most affected by the current situation. 

### The Data
- Data sourced from [Employee Burnout Dataset](https://www.kaggle.com/blurredmachine/are-your-employees-burning-out) from Kaggle
- Labeled dataset included information on 22,750 employees and their respective burnout rates (split was 75/25 for training/testing)
- Predictors of burnout rates included: Years at Company, Gender, Company Type, Work From Home Setup Available, Designation, Resource Allocation, and Mental Fatigue Score
- To structure this as a classification problem, Burnout rates were converted to a scale of 1 to 5, with 5 being the highest level of burnout

### Modeling Process
- 9 vanilla classification models were ran as a baseline
- Models included:
  - Logistic Regression
  - KNN
  - Bayes Classification
  - Decision Trees
  - Ensemble Methods (Random Forest, Adaboost, Gradient Boosted Trees, XGBoost)
  - SVM
- The best performing models were further tuned to end with a final model (XGBoost) used to make predictions on new data

### Insights and Conclusions
- The best performing model was XGBoost, with an overall accuracy of 73% and a recall for class 5 of 85%:

