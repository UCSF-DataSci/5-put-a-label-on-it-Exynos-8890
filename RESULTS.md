# Assignment 5: Health Data Classification Results

This file contains your manual interpretations and analysis of the model results from the different parts of the assignment.

## Part 1: Logistic Regression on Imbalanced Data

### Interpretation of Results

In this section, provide your interpretation of the Logistic Regression model's performance on the imbalanced dataset. Consider:

- Which metric performed best and why?
- Which metric performed worst and why?
- How much did the class imbalance affect the results?
- What does the confusion matrix tell you about the model's predictions?

- The best metric is accuracy, and the worst is recall. This is because disease outcome is imbalance in the original dataset: most of the outcomes are 0.
- It affect sharply, because recall value is significantly low.
- From confusion matrix, we can see that most data focus on (1,1), indicating the imbalance.

**Definition of Imbalance Index: Accuracy - Recall.**

Explanation: This index evaluates the difference between accuracy and recall. On a balanced dataset, accuracy and recall should be similar. A large difference indicates that the model is not performing well on the minority class.

## Part 2: Tree-Based Models with Time Series Features

### Comparison of Random Forest and XGBoost

In this section, compare the performance of the Random Forest and XGBoost models:

- Which model performed better according to AUC score?
- Why might one model outperform the other on this dataset?
- How did the addition of time-series features (rolling mean and standard deviation) affect model performance?

- Accroding to AUC score, XGBoost model performed better,
- It depends on settings on hyper-parameter, because the difference on AUC score is slight.
- Without rolling, prediction is worse. So rolling is crucial to this kind of signal data.

## Part 3: Logistic Regression with Balanced Data

### Improvement Analysis

In this section, analyze the improvements gained by addressing class imbalance:

- Which metrics showed the most significant improvement?
- Which metrics showed the least improvement?
- Why might some metrics improve more than others?
- What does this tell you about the importance of addressing class imbalance?

- Recall value have a huge improvement, and precision dropped sharply.
- This is caused by SMOTE makes this dataset balance, but this kind of impute effect accuracy significantly.
- SMOTE increase recall but reduce accuracy. There would always be a trade-off.

## Overall Conclusions

Summarize your key findings from all three parts of the assignment:

- What were the most important factors affecting model performance?
- Which techniques provided the most significant improvements?
- What would you recommend for future modeling of this dataset?

- **Class imbalance** and **feature engineering (time-series features)** were the most important factors affecting model performance.
- **Addressing class imbalance (SMOTE)** significantly improved **recall**, while **time-series features** improved overall **prediction** performance (implied by better results with rolling).
- For future modeling, I recommend focusing on **handling class imbalance effectively** and exploring more **advanced time-series feature engineering** techniques. Further **hyperparameter tuning** for tree-based models could also be beneficial.
