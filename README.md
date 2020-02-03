# Association-rules-on-football-dataset
Association rules to identify winning playing strategies for team AS Roma

# The Business Problems and Our Approaches

## Defining the Business Problem
Every season is defined in the mind of the fans by the prior performances and future expectations of the club. This inseparable truth shapes all facets of the club from personnel changes (coaching and players) to financial performance. Financial performance of the club can be impacted by attendance, merchandise, sponsorships, and broadcasting revenue for example. This is only complicated further by the UEFA tournament relegation and promotion system. Each league has space for a fixed number of teams. The bottom three teams in a league get relegated (demoted) to a lower league while the top three get promoted to a higher league. The ultimate goal is to get your club into the UEFA Champions League. The financial implication of being relegated or promoted the in tournament are substantial. According to an ESPN article, “The Cost of Premier League Relegation Enough to Make Clubs Panic”, repeated relegations place teams into deep debt burdens with the risk of bankruptcy (Brewin, 2017). Conversely, being promoted to the Champion’s League, the next league above Serie A, a club receives $37.13 million with the ability to make additional millions for each win and rank in the final outcomes of the UEFA Champions League tournament according to UEFA (UEFA, 2018).

With twenty teams in Serie A competing, A.S. Roma has been consistently in contention for promotion to the UEFA Champions League. As seen in Exhibit 1 below, four of the last eight seasons A.S. Roma has been promoted to the Champions League else the club has just missed the promotion cutoff of rank three or higher. Considering the financial gain both in terms of participation/performance bonuses and its increased core revenue (attendance, merchandise, sponsorships, and broadcasting) what can A.S. Roma do to maximize it’s chances to be ranked in the top three spots in the Serie A?

## Approach
In order to provide actionable insights for A.S. Roma and it’s coaches in what attributes define being a top three Serie A team opposed to a next three ranked (rank four, five, and six) we have tiered our inquiry. First, our analysis digs into the season level and looks for the key characteristics defining being a top three team opposed to the next three team. Despite the results being obvious, they give direction on what to focus on at the match level analysis. Second, we dig into the characteristics of specific matches as defined by the season level generalities to identify how the top three teams are different than the next three. In particular the focus will be on attributes of teams having success against competition which A.S. Roma should be capable of winning. These associations will serve as guidance for coaching to improve A.S. Roma’s probability of being a top three team opposed to a next three.
![Exhibit 1: A.S. Roma Rank by Season in the Serie A League](https://github.com/sampadasathe/Association-rules-on-football-dataset/blob/master/exhibit_1.PNG)

## Overview of the Data

In order to answer sub-question one "What characteristics are associated with being a top three team in Serie A opposed to a next three team?"", we must transform the available table to be grouped by season and team. This gives us the ability to analyze team characteristics, performance, and split the data into two groups: top three and next three teams by season.

We first analyzed the tables to establish what available features are pertinent in distinguishing top and next three teams in a league. Three tables are helpful in accomplishing our desired table: *team*, *team_attributes*, and *match*. 

## General Analysis

Prior to running association rules to determine what team/season level characteristics seem to be associated with being in the top three teams in the Serie A league, you can notice in *Exhibit 2* the different distributions in wins, ties, and losses for top three teams versus next three teams for both home and away game. **The primary difference appears to be between a top three team and a next three team in their ability to win home games and not lose away games.**
![Exhibit 2](https://github.com/sampadasathe/Association-rules-on-football-dataset/blob/master/exhibit_2.png)

To verify this assumption holds true we will run association rule testing to see what team/season level characteristics seem to be attributed with being a top three versus a next three team. In order to limit the number of rules and maintain high confidence the rules are indeed related to being a next three or top three team in the league. We set sufficient support, confidence, and lift parameters to limit the number of rules to those most substantiated in the data. The code is seen below.

## General Findings and Conclusions

**What characteristics are associated with being a top three team in Serie A opposed to a next three team?**

The associations as seen in *Exhibit 3* and *Exhibit 4* (see below) are association plots. The words and green circles represent a characteristic of a team at the season level, the brighter the red color indicates the stronger the lift (odds of the association over random chance) of the rule, and the size of the circles should be disregarded. 

* In *Exhibit 3*, association rules with being a next three team, you notice that teams having an away win record being in the bottom 25th percentile, an away loss record in the top 75th percentile, a medium defensive ability to pressure opponents, and a normal defense formation width are associated with being a next three team. 

![Exhibit 3](https://github.com/sampadasathe/Association-rules-on-football-dataset/blob/master/exhibit_3.PNG)

* In *Exhibit 4*, association rules with being a top three team, you notice an association with being in the bottom 50th percentile in away losses, bottom 25th percentile in home losses, and a normal defense formation width are associated with being a top three team. However, some rules are not strong by themselves to define the difference between a top three and next three team. First, the defense team width being normal is the same for being both a top three and next three team therefore being irrelevant for distinguishing the two groups. Second, the defense pressure of “medium” as seen associating with a next three team does not have an opposite association to being a top three team. Meaning we would have expected the top three team to have a defense pressure class association different than a 'medium' ability. Thirdly, for the same reason as the second point the away win record of being in the bottom 25th percentile does not have an opposite analog for the top three teams. Therefore, the obvious association for distinguishing a top three and next three team is the team’s ability to not lose away games as next three teams are in the top 75th to 100th percentile in number of away losses while the top three teams are between the 25th to 50th percentile in number of away losses.

![Exhibit 4](https://github.com/sampadasathe/Association-rules-on-football-dataset/blob/master/exhibit_4.PNG)

## Contributors:
1. Michael Thompson
2. Piyush Gupta
3. Xiangke Chen
4. Ruikang Lan
5. Navneet Nimish
6. Sampada Sathe
