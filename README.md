# This Too Shall Pass: Predicting Offensive Play-Calling in the NFL

In the NFL, all offensive plays besides specialized ones (punts, kneel-downs, etc.)  can be classified into one of two categories: run or pass.  The ability to predict whether a particular play by an opponent will be a run or a pass based on the in-game situation would be highly useful for defensive coaches, and could increase their chances of winning the game.  In this project, I leveraged machine learning classification models to predict whether an NFL play would be a run or a pass based on readily available pre-snap information.

## Design and Data

I used a large dataset from [Kaggle](https://www.kaggle.com/pepepython/spotify-huge-database-daily-charts-over-3-years?select=Database+to+calculate+popularity.csv) containing all the plays from the 2017 NFL season (of which ~32,000 were Runs or Passes).  I used Pandas to clean and process the data, as well as engineer a several extra features (binary features for the down, third and long, within field goal range, etc.).  Since I am more interested in the *intent* rather than the result of the play, I used the following definitions of "Run" and "Pass":

- Run: all designed runs.   If the quarterback dropped back to pass, but ended up scrambling for a gain of yards, I considered that to be a pass, since that was the intent of the play.

- Pass: all designed passes.  If a quarterback dropped back to pass and got sacked behind the line of scrimmage, I considered that to be a pass for the purposes of this model as well.

## Tools and Algorithms

I used Pandas for data exploration, cleaning and feature engineeering, and sci-kit learn to  train the machine learning models. (please see [this](https://github.com/andreilevin/Classification_project/blob/main/nfl-cleaning.ipynb) jupyter notebook  for the initial cleaning and [this one](https://github.com/andreilevin/Classification_project/blob/main/nfl-modeling2.ipynb)  for the main analysis.


## Communication

Using accuracy as the main metric, the goal was to improve on the baseline accuracy of 60.4%, which is generated from a naive classification of all plays as the "Pass" play majority class.  The best ML models achieved a test set accuracy of ~74%.  More information and ideas for further work can be seen in the slide deck [here](https://github.com/andreilevin/Classification_project/blob/main/AndreiPresentation.pdf).  

