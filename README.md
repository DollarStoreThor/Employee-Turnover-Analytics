# Employee-Turnover-Analytics
The HR department wants to study the factors that contribute to employee turnover. As an ML developer, I performed an analysis using a clustering algorithm to identify which employees are most likely to leave, and suggest various retention strategies for targeted employees. 


# Goals

1.  Perform a data quality check and address the missing values, if any.                                                                                                        
2. Perform an EDA to understand what factors contributed most to employee turnover.
  -     Draw a heatmap of the correlation matrix between all numerical features and columns in the data.
  -     Draw the distribution plot of:
    
          1. Employee satisfaction by using column satisfaction_level
          2. Employee evaluation by using column last_evaluation
          3. Employee average monthly hours by using column average_monthly_hours
  -  Draw the bar plot of the employee project count of both employees who left and who stayed in the organization (use column number_project and hue column left) and give your inferences from the plot.                                                                                                                                                                                                              
3.  Perform a clustering of employees who left based on their satisfaction and evaluation.

    - Choose columns satisfaction_level, last_evaluation, and left.
    - Cluster the employees who left the company using K-means clustering (3 clusters).
    - Based on the satisfaction and evaluation factors, give your thoughts on the employee clusters.

4. Handle the left-class imbalance using the SMOTE technique.
  -  Pre-process the data by converting categorical columns to numerical columns by:
    
    -   Separating categorical variables and numeric variables
    -   Applying get_dummies() to the categorical variables
    -   Combining categorical variables and numeric variables
    
-  Perform the stratified split of the dataset to train and test in the ratio 80:20 with random_state=123.
- Upsample the training dataset using the SMOTE technique from the `imblearn` module.
  
5. Perform 5-fold cross-validation model training and evaluate performance.

       - Train a logistic regression model, apply a 5-fold CV, and plot the classification report.
       - Train a random forest classifier model, apply a 5-fold CV, and plot the classification report.
       - Train a gradient boosting classifier model, apply a 5-fold CV, and plot the classification report.


6. Identify the best model and justify the evaluation metrics used.
-      Find the ROC/AUC for each model and plot the ROC curve.
-      Find the confusion matrix for each of the models.
-      Explain which metric needs to be used: recall or precision.

7. Suggest various retention strategies for targeted employees.
- Using the best model, predict the probability of employee turnover in the test data.
-Based on the probability score range below, categorize the employees into four zones and suggest your thoughts on the retention strategies for each zone.
-      Safe zone (Green) (score < 20%)
-      Low-risk zone (Yellow) (20% < score < 60%)
-      Medium risk zone (Orange) (60% < score < 90%)
-      High-risk zone (Red) (score > 90%)
