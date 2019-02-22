---
layout: post
title:      "NBA Stats that Translate to Team Success"
date:       2019-02-22 11:36:30 -0500
permalink:  nba_stats_that_translate_to_team_success
---


There are numerous game statistics recorded for each NBA game. These statistics cover almost every aspect of each game and can essential tell most of the story on how a game was won. Statistics that are captured range from things like total baskets made, total shots attempt, assists, steals, turnovers, rebounds, and many more. Which of these statistics has the most important in determining who comes out the winner of a game? Do some statistics stand out as more important than others? Has the importance of these individual statistics changed over the seasons as the professional game has evolved? The below analysis is my attempt to answer these questions.

My approach to answering these questions can be broken into a few steps. I pulled the game statistics from all regular season NBA games for the past four years. I am going to start by creating a classification model to predict the outcome of games. If I can come up with a model that better predicts the outcome compared to a baseline accuracy, I can then analyze the importance of each statistic in determining the model. I will then rerun the model we created for every season separately to see how the statistic importance has changed over the years in best predicting the outcome of basketball games. We can use these important measures to come up with in-game strategies and practice drills that reinforce what truly influences the outcome of a game.

I decided to use a correlation heat map to compare all the game statistics against each other to determine which ones I wanted to use in our classifier model. I first looked at every game statistic's positive correlation with total team points scored as a baseline, because I think that the more points you score, the higher the chances of winning a game. I then took those stats that showed positive correlations to total points and compared them against each other to determine collinearity. After that, I was able to narrow down our list of statistics to ten.

After our statistics/features were determined, I ran them through multiple classification models. I used a bagging classifier, a decision tree classifier, and a random forest classifier. For my first run-throughs, I did not tweak any hyperparameters within the models and only used their defaults. All three models ended up predicting our testing set with between 65% and 70% accuracy. I knew that these models were doing better than guessing because if we were to guess that all home teams would win, we would be right 58% of the time, which was our starting baseline. I decided to then continue one with using our decision tree model, because it was close with accuracy with the other models, and by tweaking its hyperparameters, I believe we can improve on the model without running the risk of overfitting.

I used the GridSearchCV library in sklearn to run multiple decision trees based on different hyperparameter options. The resulting recommended hyperparameters for our decision tree resulted in improving our model's accuracy by about 4%, to around 70% accuracy. I felt that the model was in a good spot that I could start using it to predict each season to start analyzing each statistics importance in determining the winner of a game.

After analyzing our statistic's importance for each year's modeling, I determined a couple of conclusions. For one, the most important statistic in determining the outcome of a game is defense. The was made evident that defensive rebound ranked as the highest importance. Defense rebound counts go up as a defense limits their opponents to one shot per possession, and it's evident that the opponent missed a shot if the defense gets a rebound. Next, the three-point shot is becoming more important as every season has progressed. Finally, fouls and blocked shots are the least important in determining the outcome of a game.


