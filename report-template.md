# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Paul Braunger

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I needed to change all negative value predictions to zero.

### What was the top ranked model that performed?
The model with the tuned hyperparameters coming in at a kaggle score of 0.76169.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
I changed season and weather to categorical variables and I parsed the datetime column to month, day, minute, second, hour as well as name of day which I set to a categorical variable.

### How much better did your model preform after adding additional features and why do you think that is?
Performance increased from a kaggle score of 2.04866 to 0.76428, which is likely due to the autoML solution being able to see season and weather as categorical variables instead of an ordinal variable.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Performance increased from a kaggle score 0.76428 to 0.76169.

### If you were given more time with this dataset, where do you think you would spend more time?
I would have individually tested and tuned an SVR, RidgeRegression and Lasso algorithms to see if there is a more optimal outcome.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|time|num_bag_folds|num_stack_levels|score|
|--|--|--|--|--|
|initial|600|10|3|2.04866|
|add_features|600|10|3|0.76428|
|hpo|600|6|2|0.76169|

### Create a line plot showing the top model score for the three (or more) training runs during the project.



![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.



![model_test_score.png](img/model_test_score.png)

## Summary
Overall I was pleased with the outcome, I do wish there was more centralized documentation and the ability to unpack how the individual weighted ensembles are created to further inform parameter tuning.
