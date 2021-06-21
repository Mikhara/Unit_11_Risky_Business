# Unit_11_Risky_Business

By: Mikhara Ramsing

## Resampling

### Simple Logisics Regression (SLR)

Note that 3.33% of loan status are high risk loans ie bad loans. The classes are significantly imbalanced which will affect our accuracy score.

Overall, the SLR model provides 95% accuracy. However, as noted our data set is greatly class-imbalanced therefore precision and recall will provide a better measure of how good our SLR model is at predictions. 


Our SLR model has 91% Precision, this means when the model predicts a high risk loan, it is correct 91% of the time. From the imbalanced classification report, high risk loan has 86% precision which is lower level of precision compared to confusion matrix. However, model has precision score of 100% when it comes to low risk loans, providing an average of 99% precision for whole model.

Our SLR model has a recall of 86%, it correct identifies 86% of all high risk loans. From imbalanced classification report, high risk loan has 91% recall which is a higher level of recall compared to confusion matrix, which I think is explained by the fact that data is heavily imbalanced.

Based on the confusion matrix, the SLR model has pretty high Precision (91%) and Recall (86%) but in the imbalanced classification report, we see high risk loans has 86% Precision and 91% Recall. Let's see if we can improve this model's precision and recall through over, under and over and under sampling.

Note, from the imbalanced classification report, it appears that SLR model for low risk loans has perfect precision and recall hence perfect F1 score of 1 too.

### Oversample

Oversampling results in the SLR model maintaining its 95% accuracy. More interestingly, we see from the imbalanced classification report that recall for high risk has increased to 100% (from 91%) and as expected precision fell to 85% (from 86%). However with SMOTE oversampling, precision remains at 86% with recall at 100%.


This is a great result with the model correctly identifying 100% of all high risk loans with 86% precision (correct 86% of the time). The F1 score has also increased to 92% (from 89%).

### Undersample

Undersampling results in the SLR model maintaining increasing its accuracy to 99% however note heavy imbalanced classes.

Precision remains at 86% for high risk loans with a recall of 97% (this is lower than SMOTE oversampling of 100%) and F1 score of 91%. Undersampling does not result in a better fit of the model compared to oversampling the data. 


### Over and Under sample

While oversampling is providing great results, we may be in danger of overfitting our data or being affected by noisy data due to outliers. 

Using combination sampling provides us with 99% accuracy, 85% precision and 100% recall for high risk loans and an F1 score of 92%.

### Conclusion

SMOTTEEN provides a model that has greater accuracy (99%), 85% precision and same level of recall (100%) and F1 score (92%) for high risk loans as SMOTE, however, SMOTE has higher precision of 86% for high risk loans and 95% accuracy. Given class - imbalanced dataset, I would not weigh accuracy as much as precision metric hence would pick SMOTE model as best fit for predictions.

## Ensemble Learning

This data is heavily class imbalanced with only 0.51% of loan status being high risk loans. Thereby using ensemble learning by strategically generating random samples will improve model accuracy, precision and recall and F1 score.

### Balanced Random Forest Classifier (BRFC)

The BRFC provides 50% accuracy. The recall score for high risk loans is 100% however the precision is 0.01 and similarly the F1 score is 0.01 for high risk loans. This model is not a good fit. This is reflected in the classification matrix where there are 0 False positives and worringly 0 True Positives.

### Random Forest Classifier (RFC)

The RFC provides 67% accuracy. The recall score for high risk loans is 34% and precision is 73%, still not great but much bettwen than BRFC model. Higher F1 score of 47%

### Features

total_rec_prncp is the top feature for both BRFC and RFC model. 'total_rec_int' is second most important feature for BRFC whereas 'total_pymnt' is second most important feature for RFC with a higher importance of 7.7%. total_pymnt_inv' is third most important feature for both models.

## Conclusion

SMOTEN provides best fit model. Using ensemble learning, a ranfrom forest classifier provides better fit. 

