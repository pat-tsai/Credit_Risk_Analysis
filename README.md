# Credit Risk Analysis

## Overview:
- The purpose of this analysis was to determine the impact of a variety of attributes on loan status (high risk vs. low risk). Attributes that weren't numerical datatypes in the original dataframe were encoded using Panda's `get_dummies()` function so these categorical attributes could be used in subsequent modeling


## Results 

Model results:
**When evaluating the model results it's important to keep in mind 3 key attributes: precision (fraction of relevant instances among retrieved instances), recall (sensitivity/fraction of total relevant instances retrieved), and index balanced accuracy.**

**1) Oversampling model: naive random oversampling

![ScreenShots](/resources/random_oversampling.PNG)

This model had 100% precision/62% sensitivity for determining low risk loans and 1% precision/ 67% sensitivity for high risk loans. Accuracy was 42% and 41% respectively.   

**2) SMOTE oversampling model

![ScreenShots](/resources/smote_oversampling.PNG)

This model had 100% precision/67% sensitivity for determining low risk loans and 1% precision/ 62% sensitivity for high risk loans. Accuracy was 42% for both groups. This model slightly outperformed the previous model, but prediction rates for high risk loans are not very high and misses almost 40% of threats.

**3) Undersampling

![ScreenShots](/resources/undersampling.PNG)

This model had 100% precision/41% sensitivity for determining low risk loans and 1% precision/ 68% sensitivity for high risk loans. Accuracy was 29% and 27% respectively. Performing undersampling on its own seems to have a negative effect on this dataset.

**4) Combination sampling

![ScreenShots](/resources/combination_sampling.PNG)

This model had 100% precision/56% sensitivity for determining low risk loans and 1% precision/ 79% sensitivity for high risk loans. Accuracy was 45% and 43% respectively. In this case, combination sampling outperforms undersampling and oversampling used seperately. 


**5) Balanced Random Forest

![ScreenShots](/resources/balanced_random_forest.PNG)

This model had 100% precision/88% sensitivity for determining low risk loans and 3% precision/ 71% sensitivity for high risk loans. Accuracy was 62% and 64% respectively. This model greatly outperforms all previous models. 

**6) Easy Ensemble

![ScreenShots](/resources/easy_ensemble.PNG)

This model had 100% precision/94% sensitivity for determining low risk loans and 9% precision/ 92% sensitivity for high risk loans. Accuracy was 87% for both groups. This final model has to best predictive accuracy for this dataset and outperforms all other models.


## Summary
In conclusion, the Easy Ensemble Classification model had the best accuracy for predicting whether a risk was a low risk loan. However, it's important to keep in mind the overall accuracy for this model for classifying both low risk and high risk loans was only 87%. This is because the model is not 100% sensitive, meaning it is unable to locate all relevant results. Furthermore, the model is not very precise at classifying high risk loans, so it may trigger many unwanted warnings/notices.
