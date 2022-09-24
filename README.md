# Predicting Offensive Play-Calling in the NFL

### Project Presentation [Slides](https://github.com/andreilevin/Classification_project/blob/main/AndreiPresentation.pdf): 

[![AndreiPresentation.pdf:](https://raw.githubusercontent.com/andreilevin/Classification_project/main/cover_screenshot.jpg)](https://github.com/andreilevin/Classification_project/blob/main/AndreiPresentation.pdf)

## Summary

In the National Football League (NFL), all offensive plays besides a few specialized ones like punts and kneel-downs can be classified into one of two categories: run or pass.  The ability to predict whether a particular play by an opponent will be a run or a pass based on the in-game situation could be highly useful for defensive coaches charged with stymying the opposing offense.  Offensive coaches, too, could examine the predictability of their own play-calling and see if that is something they could potentially decrease without sacrificing effectiveness.  In this project, I leveraged machine learning classification models to predict whether an NFL play would be a run or a pass based on readily available pre-snap information.

I used a large dataset from [Kaggle](https://www.kaggle.com/maxhorowitz/nflplaybyplay2009to2016?select=NFL+Play+by+Play+2009-2018+%28v5%29.csv) containing all the plays from the 2017 NFL season (of which ~32,000 were runs or passes).  I used Pandas to clean and process the data, as well as to engineer a several extra features (a "third and long" feature, a "within field goal range" feature, binary features for the down, etc.).  Since I was more interested in the *intent* rather than the *result* of the play, I used the following definitions of "run" and "pass":

- Run: all designed runs.   If the quarterback dropped back to pass, but ended up scrambling for a gain of yards, I considered that to be a pass, since that was the intent of the play.

- Pass: all designed passes.  If a quarterback dropped back to pass and got sacked behind the line of scrimmage, I considered that to be a pass for the purposes of this model as well.

## Tools 

* Pandas for data exploration, cleaning and feature engineeering
* Scikit-learn to train the machine learning models
* Matplotlib and Seaborn for plotting 

## Conclusions

The project goal was to improve upon the baseline accuracy of 60.4% (the majority "pass" class prevalence).  My best models achieved an accuracy of ~74% on unseen data.  While this sounds like an improvement, it's actually only barely better than a classification scheme I called the "Naive Belichick Classifier":  predict "pass" whenever the offense lines up in shotgun formation and predict "run" otherwise.  To improve significantly upon this would require more extensive feature engineering, other model architectures (Gradient Boosted Trees and Neural Nets spring to mind), or perhaps simpler ideas like training separate models on the set of shotgun and non-shotgun plays.  If I don't come back and revisit this project at some point, I hope someone else will!

