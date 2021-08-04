# Andrei's Classification Project MVP

The goal of my project is to predict whether an NFL play will be a pass play or a run play depending on various in-game features (down, distance, field position, time remaining etc.).  For my MVP, I used play-play-play data for all games from the 2017 season (see notebook nfl-cleaning.ipynb in this folder), and fitted a logistic regression model with no additional feature engineering as a first pass (see notebook nfl-modeling.ipynb in this folder).

My metric of choice is accuracy.  Since my full-year data contains 19,153 pass plays and 12,554 run plays, the baseline accuracy I'm trying to beat is simply the resultant pass play fraction, 0.604.

After scaling the features, I ran a logistic regression model and got a train accuracy of 0.736 and a test accuracy of 0.746 (hey, at least I'm not overfitting, right?)  Now, normally I wouldn't look at the test data until the very end of the project, but I just wanted something for the MVP -- won't be touching the test data again, I promise!

My training data confusion matrix looks as follows:  

```
 [[1678  845]
 [ 763 3056]]
```

This is interesting:  it means my model is twice as likely to misclassify run plays as pass plays as the other way around (thinking_face_emoji.png)

For my next steps, I first plan to do some feature engineering and hyperparameter tuning to improve the logistic regression model.  I also hope to fit a decision tree model and a random forest model.  I am interested in both model performance and interpretability, so I am curious which features end up being most important in the models.

Once I've chosen the most accurate model, I hope to make team-specific predictions and see if I can extract any insights from which team have the most "predictable" offensive play-calling.  Go Patriots!