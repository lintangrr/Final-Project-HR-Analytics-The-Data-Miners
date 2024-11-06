# HR Analytics : Predicting Employee Promotion 🧑‍💼👩‍💼

## ⛏️ The Data Miners Group ⛏️
- Lintang Rizki Ramadhani
- Army Putera Parta
- Nur Ilmalani Harahap
  
## Project Overview 🔍
A company wants to identify employees with high promotion potential by analyzing historical promotion data alongside factors like performance ratings, training participation, awards, length of service, and demographic information. This predictive approach aims to streamline the promotion process, allowing HR to focus on high-potential candidates, reduce manual evaluation time, and ensure top-performing employees are rewarded appropriately.

The project has two primary goals:

- Develop a Predictive Model to Determine Promotion Likelihood
- Identify Key Factors Influencing Promotions

## Project Details 📝
### Data Collection
Dataset source : [Kaggle](https://www.kaggle.com/datasets/arashnic/hr-ana/data)
<div style="justify-content: center;">

| Feature              | Description                                                   |
|----------------------|---------------------------------------------------------------|
| employee_id          | Unique ID for employee                                        |
| department           | Department of employee                                        |
| region               | Region of employment (unordered)                              |
| education            | Education Level                                               |
| gender               | Gender of Employee                                            |
| recruitment_channel  | Channel of recruitment for employee                           |
| no_of_trainings      | No of other trainings completed in previous year on soft skills, technical skills, etc. |
| age                  | Age of Employee                                               |
| previous_year_rating | Employee Rating for the previous year                         |
| length_of_service    | Length of service in years                                    |
| awards_won?          | If awards won during the previous year then 1, else 0        |
| avg_training_score   | Average score in current training evaluations                 |
| is_promoted          | Recommended for promotion                                     |

</div>

### Exploratory Data Analysis (EDA)

Exploratory Data Analysis (EDA) is essential for understanding the dataset, identifying patterns, and preparing features for modeling. This project’s EDA focused on univariate and bivariate analyses to extract  meaningful insights from the data.

### Data Preprocessing

Data preprocessing is a crucial step in building a reliable predictive model. In this project, the following steps were taken to prepare the dataset for training the promotion prediction model:
  - Handling Missing Values
  - Encoding Categorical Data
  - Feature Scaling
  
### Modelling and Evaluation
**1. Modeling with Default Parameters**

Initially, we built baseline models using default hyperparameters. This step provided a starting point and allowed us to establish benchmark metrics for comparison. Models that will be used :
- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- XGBoost Classifier
- GradientBoosting Classifier

**2. Modeling with Oversampling**
   
  Given the imbalance in the target variable, we applied oversampling techniques to the training set to improve the model's ability to identify the minority class. This step aimed to address class imbalance and improve model performance on the positive class. 

**3. Hyperparameter Tuning**
   
  We performed hyperparameter tuning to enhance the model’s performance by optimizing key parameters. This step involved experimenting with various parameter combinations to find the best configuration for improved F1 scores.

**4. Threshold Adjustment**
   
  Finally, we adjusted the decision threshold to achieve a balance between precision and recall, optimizing the F1 score.

## Key Findings 💡
- **Best Classification Model**

Best model for predicting employee promotion is XGBoost with SMOTE and Threshold Adjustment.

- **High Screening Efficiency for Non-Eligible Employees**

The model demonstrates a 99% recall for non-promotable employees (class 0), meaning it accurately identifies and screens out 99% of employees who are not eligible for promotion. This high screening efficiency allows HR to focus resources on a smaller pool of high-potential candidates, significantly reducing the time and effort spent on non-eligible employees.
- **Moderate Success in Identifying Promotable Employees**

The model achieves a 40% recall for promotable employees (class 1), effectively identifying 40% of the total employees who truly deserve a promotion. While this recall rate means that some promotable employees might be overlooked, it still provides HR with a substantial list of high-potential candidates for review, streamlining the overall selection process.
- **High Precision for Promotion Predictions**

With a precision of 78% for promotable employees, the model's promotion predictions are accurate 78% of the time. This suggests that, when the model does flag an employee as eligible for promotion, there is a strong likelihood that they genuinely meet the criteria. However, approximately 22% of employees predicted to be eligible may not meet all the promotion criteria, indicating room for refining the model's selection accuracy.
- **Key Factors Influencing Promotion Decisions**
  
  - Award Wins: Employees who have won awards are more likely to be promoted, suggesting a strong link between recognitions and promotion decisions.
  - Previous Year Rating: Higher performance ratings from the previous year play a significant role in promotion eligibility, highlighting the importance of consistent performance.
  - Department (Sales & Marketing): Employees in the Sales & Marketing department show a higher promotion rate, indicating that department-specific factors may impact promotion decisions.
