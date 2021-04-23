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
- Models were tuned to maximize recall for level 5 burnout in order to be conservative (ie minimize instances of incorrectly classifying an employee as level 4 burnout when in reality they had level 5 burnout)

### Conclusions
- The best performing model was XGBoost, with an overall accuracy of 73% and a recall for class 5 of 85% (out of all of the actual employees who had level 5 burnout, the model correctly classified 85% of them):

<img src="https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/model_compare.PNG" width="600" height="300"/>

![Matrices](https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/matrices_xg.png "Matrices")

- The most important feature in the determination of class was mental fatigue score, followed by resource allocation and designation:

![Feature Importances](https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/feature_importances_xg.png "Feature Importances")

- Preview of predictions on new employee data:

<img src="https://github.com/swzoeller/Employee-Burnout-Classification-Project/blob/main/images/predictions_preview.PNG" width="400" height="400"/>

#### Limitations
- Dataset only had employees that joined between 2008 and 2009 (No data on more recent employees)
- Limited features in dataset
- Blank (Nan) values were imputed using KNN Imputer, possibly skewing results

#### Next Steps and Recommendations
- Collect additional information on employees to use as predictors  (ie performance evaluations, age, marriage/family status, etc.)
- Examine relationship between burnout, loss of productivity, and attrition
- Identify and reach out to managers of all employees who scored a 5 in terms of burnout, and employees who scored a 4 and had high mental fatigue, high resource allocation and high designation




