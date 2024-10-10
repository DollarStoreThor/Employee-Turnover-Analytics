# Employee-Turnover-Analytics
The HR department wants to study the factors that contribute to employee turnover. As an ML developer, I performed an analysis using a clustering algorithm to identify which employees are most likely to leave, and suggest various retention strategies for targeted employees. 

![Data Descriptors](https://github.com/user-attachments/assets/8c76a718-a65f-449d-b85d-83f8e4342098)

# Goals

1.  Perform a data quality check and address the missing values, if any.                                                                                                        
2. Perform an EDA to understand what factors contributed most to employee turnover.
  -     Draw a heatmap of the correlation matrix between all numerical features and columns in the data.
  -     Draw the distribution plot of:
    
          1. Employee satisfaction by using column satisfaction_level
          2. Employee evaluation by using column last_evaluation
          3. Employee average monthly hours by using column average_monthly_hours
    
![Satisfaction vs Evaluation - Heatmap Years at Company](https://github.com/user-attachments/assets/708d2310-c9cc-4214-b0a2-06ea3a3324f1)
![Satisfaction vs Evaluation - Heatmap WorkAccident](https://github.com/user-attachments/assets/39602274-e6fb-4ed7-9abc-d8926de39a4c)
![Satisfaction vs Evaluation - Heatmap Turnover](https://github.com/user-attachments/assets/7913e71d-b52e-454c-83db-fb77869c980c)
![Satisfaction vs Evaluation - Heatmap Salary](https://github.com/user-attachments/assets/83da0e76-3931-48ac-8bc7-dc434759a836)
![Satisfaction vs Evaluation - Heatmap Promotion](https://github.com/user-attachments/assets/be76bb88-4ff3-4abe-8b39-d212348bde47)
![Satisfaction vs Evaluation - Heatmap Project Count](https://github.com/user-attachments/assets/7c6ab491-42ea-4705-b038-3d969e71f6f3)
![Satisfaction vs Evaluation - Heatmap Department](https://github.com/user-attachments/assets/9cf90ae9-799d-442b-87c7-4b4b07cfad19)

    

  -  Draw the bar plot of the employee project count of both employees who left and who stayed in the organization (use column number_project and hue column left) and give your inferences from the plot.                                                                                                                                                                        
![Correlation Heatmap of the all Orignal Dataset Features](https://github.com/user-attachments/assets/4cbd63d4-47ab-45a3-973a-ef5f9113dab4)

![Lasso Model Furtest Coefficents from 0 - Most Influential Features for Predicting Employee Retention](https://github.com/user-attachments/assets/ddbc8246-c1c3-4cc0-b7f9-fc2a68c116e4)
![13 Best Predictors of Employee Turnover from LassoCV Model - How these features Correlate with Eachother](https://github.com/user-attachments/assets/425addeb-19d1-4a9d-8e7f-a162c5ae93e4)

              
3.  Perform a clustering of employees who left based on their satisfaction and evaluation.

    - Choose columns satisfaction_level, last_evaluation, and left.
    - Cluster the employees who left the company using K-means clustering (3 clusters).
    - Based on the satisfaction and evaluation factors, give your thoughts on the employee clusters.

![Clusters of Employee Turnover](https://github.com/user-attachments/assets/d1c50e35-2633-495f-b3e5-487b1111a2d1)


4. Handle the left-class imbalance using the SMOTE technique.
  -  Pre-process the data by converting categorical columns to numerical columns by:
  -  
![Employee Turnover](https://github.com/user-attachments/assets/8586999c-1b98-43ff-bc2e-ddf56983da1b)


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
![Logistic Regression Model Performance - 5 Fold CV](https://github.com/user-attachments/assets/9dd17f3c-f191-4f51-8f88-315650dc5473)
![Logistic Regression Model Performance](https://github.com/user-attachments/assets/be26c695-a48b-4945-b291-2f1c0dd9869d)
![Confusion Matrix for Logistic Regresion](https://github.com/user-attachments/assets/41939741-9140-4d14-9dcf-79600c0bff90)



![Gradient Boosing Classifier Model Performance - 5 Fold CV](https://github.com/user-attachments/assets/1745af61-d470-48b8-82d8-8a27ea5cc4e8)
![Gradient Boosting Classifier Model Performance](https://github.com/user-attachments/assets/6b396576-2b5d-4600-a685-141798a5df90)
![Confusion Matrix for GBC](https://github.com/user-attachments/assets/004c3e70-3b56-465e-865a-9e1ff658c450)




![Random Forest Classifer Model Performance - 5 Fold CV](https://github.com/user-attachments/assets/a9df4c69-a5a0-4647-aa5b-d04aaef3c59b)
![Random Forest Classifier Model Performance](https://github.com/user-attachments/assets/c8cfa5f4-ff33-49eb-a256-a3fb62887884)
![Confusion Matrix for Random Forest](https://github.com/user-attachments/assets/1e3e0522-e6d5-446c-a557-0186aaf64a36)


![ROC Graph](https://github.com/user-attachments/assets/00954bb5-5e35-4e94-be4e-b07d739022de)

7. Suggest various retention strategies for targeted employees.
   
![Predicted Turnover Probability, Ground Truth, and Risk Class - Data Frame](https://github.com/user-attachments/assets/f09026f6-8b07-4555-a2e9-437a3f8582cf)

   
- Using the best model, predict the probability of employee turnover in the test data.
-Based on the probability score range below, categorize the employees into four zones and suggest your thoughts on the retention strategies for each zone.
-      Safe zone (Green) (score < 20%)
-      Low-risk zone (Yellow) (20% < score < 60%)
-      Medium risk zone (Orange) (60% < score < 90%)
-      High-risk zone (Red) (score > 90%)
  
![Count of Predicted Risk Classes](https://github.com/user-attachments/assets/fb7e1230-43b5-4e86-8496-ad149332dc89)
![Risk Classes](https://github.com/user-attachments/assets/f15806ba-2b3e-4178-9db9-35bd2f50eeb2)


![Risk Classes Violin vs Ground Truth](https://github.com/user-attachments/assets/3be6fc1b-a531-4bbc-b67c-6de39acdea1c)
![Risk Classes Boxen vs Ground Truth](https://github.com/user-attachments/assets/bd31c4ea-02b2-4755-ae2c-33ce37ebcc57)
![Risk Classes (Ground Truth)](https://github.com/user-attachments/assets/8bbb851c-f60a-47b9-93f4-08b407f226ec)

