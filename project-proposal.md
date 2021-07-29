# Andrei's Classification Project Proposal

In the NFL, all offensive plays besides specialized ones (punts, kneel-downs, etc.)  can be classified into one of two categories: run or pass.  The ability to predict whether a particular play by an opponent will be a run or a pass based on the in-game situation would be highly useful for defensive coaches, and could increase their chances of winning the game.  My plan is to use a large dataset of detailed NFL play-by-play data from Kaggle (originally scraped from NFL.com: ~400,000 plays over 10 years) in order to give this classification problem a shot: https://www.kaggle.com/maxhorowitz/nflplaybyplay2009to2016

Some available features that I think could have predictive power:  down, distance, field position, time remaining (in the quarter? in the half? in the entire game?), formation (shotgun or 'other'), points ahead/behind, timeouts remaining, home or away.  I am also wondering if including the quarterback, team, and opponent would be helpful (only if we're looking at data from a single season, I reckon).

As far as engineered features, the main one that I think it would make sense to add to the analysis is the cumulative ratio of run to pass plays (over the course of all the preceding plays in the game) for the team on offense.  However, I am afraid this ratio will be very noisy for the first few plays of the game, and I am also worried about the fact that teams usually script their first drive of the game beforehand, rather than making the play decisions in the moment.

Edge cases could also require special attention, such as goal-line, end-of-half, and end-of-game situations. Any advice is welcome!