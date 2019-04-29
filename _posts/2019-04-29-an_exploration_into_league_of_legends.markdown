---
layout: post
title:      "An Exploration Into League of Legends"
date:       2019-04-29 15:04:00 +0000
permalink:  an_exploration_into_league_of_legends
---


League of Legends is a Multiplayer Online Battle Arena (MOBA) video game that has become one of the most popular games in the world. Over 27 million people play the game daily across the globe for fun and rank, as well as 13 professional leagues with teams owned by other professional sports organizations. With the rise in popularity of E-Sports in the mainstream media and across global cultures, League of Legends has become the community’s poster child over the last 5 years.

For those who have never heard of the game, or don't know how it works, this video is a great introduction: https://www.youtube.com/watch?v=BGtROJeMPeE. 

Sports analytics is still relatively new for the world of E-Sports. With access to thousands of game information via Riot, the owners of League of Legends, we now have the capabilities to analyze how games are won and develop strategies for both professional and public player success.

What I attempted to explore through data exploration and predictive modeling was to understand the components that are needed for teams to win throughout the duration of the game. To win a game of League of Legends, you need to destroy your opponent’s Nexus before they destroy yours. You have three lanes on the map in which to obtain this objective. In each lane lies three turrets and one inhibitor that stands between you and winning. So, the raw gist of the game is to destroy one lane’s worth of turret’s and inhibitors to get to the enemy Nexus and destroy it. Beyond these main objectives of the game, there are underlying pieces that can give teams an advantage of achieving them first that aren't so obvious. 

I want to first analytically determine the fundamental concepts of the game beyond these main objectives that can help players become more efficient and could increase a player's chances of winning. Then I want to see how well I can predict the outcome of public games via these stats and stats I will create going through this analyses. This analysis is a look at over 150,000 public games played from players across the globe.

The first step I took to try and understand the game a little better was to create correlation matrices with the main variable of comparison being whether a team won or not. The public data I retrieved contains multiple game stats for each game, as well as which team won. By comparing each game stats correlation to winning, I can start to understand what factors are important. To take the analysis further, I created the correlation matrices based on game durations. I wanted to see as the game progressed, what factors were more important to winning.

After reviewing the matrices and comparing them, I found a few key conclusions. One was that the highest correlations to winning for games that last less than twenty minutes were accumulating gold, and not dying. Gold is the main essence of how players can gain advantages of their opponents. By accumulating gold more efficiently than your opponent, you start to create item advantages. Gold is usually acquired in the early parts of the game from a few sources. One being destroying minions, and one is destroying enemy champions. After the early game is over, the correlations towards winning start shifting to turret kills and inhibitor kills. Like mentioned above, these objectives are the main part of the game. This turns into a macro strategy type game, in which teams need to work together to figure out:

    1) How can we destroy the enemy turrets and inhibitors?
    
    2) How can we defend our base?
    
    3) How can our team composition be used to our advantage to winning?
    
    4) What neutral objectives should we focus on that can help us win?


Although we saw a shift in higher correlations towards winning, the same stats were always in the top few stats.

When it came to trying to predict the outcomes of games before they started, this was a pretty challenging task. Our baseline statistic is that the blue team wins about 51% of the time, so any model that can predict higher than this is technically better than guessing. I broke the predictive modeling portion into two types of modeling:

How well can we predict the outcome of a game just by knowing what champion each player selected
How well can we predict the outcome of a game by know how well each champion fares against their opponent

Modeling the first scenario, I ran a few classification algorithms to see how well they would do. I ran a logistic regression, random forest, naive bayes, and XGBoost. Based on these algorithms, the model could only make the predictions with 54% accuracy as a maximum. This is not quite the improvement we were hoping for. Luckily, our second scenario fared better. By adding in features related to champion win rates overall and win rates against their lane opponents, we were able to run the same classification models as above, and achieve a 62% accuracy.

