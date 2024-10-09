# The Evolution of NBA Scoring

## Table of Contents

- [Introduction](#introduction)
- [Project Description](#project-description)
- [Data Source and Preparation](#data-source-and-preparation)
- [Tools](#tools)
- [Analysis](#analysis)
- [References](#references)

### Introduction

My name is Jagjot Atwal, and I’ve been a passionate fan of the NBA for over a decade now. Since I started watching the sport in 2013, a lot has been said about how NBA basketball has seemingly changed with respect to the sheer volume of points scored, and the methods by which these points are scored. It is for this reason that I have decided to research and analyze the trends and changes in scoring that have shaped the NBA into what it is today. The target audience for this project includes basketball fans, sports journalists, sports analysts, and anybody interested in learning more about the game of basketball. By analyzing scoring in the NBA over the span of multiple decades, I hope to gain some insight on how the game is changing, and the factors impacting these changes.

### Project Description

Over the last 25 years, there have been significant changes in scoring patterns in the NBA. Teams have seemingly been scoring more points than ever, and a discussion is to be had about why this is the case. Historically, the preferred method of scoring consisted of shooting from as close to the basket as possible, where shots are most likely to go in. Shooting from the mid-range (roughly 10-20 feet away from the basket), which is still relatively close, was also one of the most popular methods of scoring. However, recently the league has seemingly put the majority of their focus on shooting three-pointers, which are shots that are noticeably further away from the basket, but they are worth 3 points as opposed to the standard 2 points. Another aspect of scoring that has been talked about a lot lately is free throw shooting. In basketball, if a player is hit by the defender while shooting the ball, they are given 2 free shots worth 1 point each. Many fans have recently been outraged with the lack of physicality allowed in the game today, and are frustrated that players are shooting too many free throws now. However, is this really the case? Is scoring really all that different from what it used to be?

I ultimately decided to analyze and visualize how scoring has changed in the NBA because it has been a major topic of discussion in NBA circles for the past few years. Some initial curiosities that I wanted to address with my project were: Are teams/players scoring more points now than ever before? To what degree have teams been increasing their three-point attempt volume?  Are the best scorers getting more points from the free throw line than in years past? What areas on the court do offensive players in the league tend to favor today compared to in the past?

### Data Source and Preparation

In order to address the main questions I had about the evolution of NBA scoring, I needed to analyze how scoring has changed at both the team and individual level. I searched for publicly available data sets on Kaggle, and fortunately I was able to find three files that, when put together, contained almost all of the data I was hoping to find. These three files contained data dating back to 1947 regarding team stats per game, player counting stats per game, and player shooting stats throughout their careers. All of this data was scraped from Basketball-Reference, which is a website that compiles countless amounts of NBA data to one place, and it was subsequently uploaded to Kaggle by a user named Sumitro Datta. The Team Stats Per Game data set contains 29 fields and 1814 rows, the Player Stats Per Game data set contains 37 fields and 31135 rows, and the Player Shooting Stats data set contains 34 fields and 16050 rows (Datta, 2023). Luckily for me, all of these data sets were already well-prepared and clean, so the only thing I needed to do was form a relationship between the Player Stats and Player Shooting data sets using the Player ID field.

The only other data set I was hoping to find was one containing the exact location of every shot that each player had taken over the last few decades, and fortunately I was able to find this as well. User Sports Viz Sunday collected NBA shot location data spanning between 1997 and 2020 from the NBA Stats API and uploaded it to data.world. This data set contained 24 fields and over 4.7 million rows (Sports Viz Sunday, 2020). It was with this data set that I encountered the most challenges. I had personally never worked with a data set of this size, so I had trouble with optimizing its performance. I also was not able to form a relationship between this data set and the previously mentioned Team/Player Stats data sets, despite many attempts at doing so. Thankfully these limitations were not as crippling as they could have been, and I was still able to include everything that I had intended to, but I recognize that this may not always be the case.

### Tools

- Tableau: Form relationship between datasets and data visualization

### Analysis

As I stated earlier, my goal was to analyze/visualize how scoring has evolved in the NBA over the last few decades. In order to do this, I decided to focus my attention on four specific measures of scoring: points, field goal attempts, free throws, and three-pointers. First and foremost, I wanted to see if teams were scoring more points in recent years compared to years prior. To visualize this, I decided to use a line chart because they are most effective when searching for trends/patterns over a period of time.

![1  Team PPG by Year](https://github.com/user-attachments/assets/3a390f9b-e400-4252-b489-92fc8131267d)
Line chart showing the average number of points scored per game by NBA teams from 1997 to 2023.

As expected, it does appear that teams are scoring more points now than in years prior. In 1997, the league average points per game (PPG) for NBA teams was 96.9. However, in 2023, teams are now averaging 114.7 PPG, which is an increase of 17.8 PPG. Next, I wanted to see if a similar pattern could be seen at the individual player level instead of at the team level. To visualize this, I used Tableau to rank the top twenty individual scorers from each season ranging from 1997 to 2023, and created a box-and-whisker plot to compare the distributions of their scoring averages.

![3  Top Scorers by Year](https://github.com/user-attachments/assets/87eba86e-9ad9-4fa5-a331-8ea6c9808989)
Box-and-whisker plot comparing the PPG of the top 20 scorers in the NBA by year from 1997 to 2023.

Although the pattern isn’t as pronounced as that of the Team PPG by Year, it does appear that the best scorers in the league have been increasing their scoring output since 2017. For reference, in 1997 the top 20 scorers in the league had a median scoring average of 21.9 PPG and the lower hinge had a value of 21.1 PPG. However, in 2023 the top 20 scorers had a median scoring average of 28.0 PPG and a lower hinge value of 26.1 PPG. These numbers indicate an increase of 6.1 PPG and 5.0 PPG in the median and lower hinge scoring averages respectively, meaning that not only are teams scoring more points now than they were 25 years ago, but the best players are as well.

There are a number of factors that could have caused the heightened scoring averages in recent years, and the first one that I decided to test was field goal attempts (FGA), which are essentially just shot attempts. Similarly to the Team PPG by Year graph, I decided to use a line chart to visualize this because I am once again looking to observe any trends/patterns over time. 

![2  Team FGA by Year](https://github.com/user-attachments/assets/6c9fa777-ba6a-4d10-abe7-ab8167c0ffd3)
Line chart showing the average number of field goal attempts per game by NBA teams from 1997 to 2023.

At first glance, it does in fact appear that increased field goal attempts (FGA) are directly related to increased scoring, because they both share similar patterns. As FGAs increase, PPG does as well. However, it is unlikely that an increase in FGA is the only underlying cause of increased scoring because despite there being a jump in scoring of 17.8 PPG since 1997, there was only an increase of 9 FGA per game. This would imply that teams are now scoring nearly 2 more points per FGA, which is unrealistically efficient (StatMuse, 2023). Once again, I wanted to see if a similar trend could be seen at the individual level, so I used a box-and-whisker plot to compare the distribution of FGAs for the best scorers over this time period.

![4  Top Scorers FGA by Year](https://github.com/user-attachments/assets/bb1f0fe1-cd35-455a-b633-9e1b93c3cdf7)
Box-and-whisker plot comparing the FGAs of the top 20 scorers in the NBA by year from 1997 to 2023.

As expected, the similarities that were seen between the team and individual level scoring were also found between the team and individual level’s field goal attempts.  In 1997 the median number of FGAs for the top 20 scorers was 18.1, but in 2023 the median number of FGAs was 20.1. Once again, it is highly unlikely that players in 2023 are only taking 2 more FGAs than those in 1997, yet scoring 6.1 more PPG. These values would translate to 3 points per field goal attempt, which would be a level of efficiency that has never been seen in the history of the NBA (StatMuse, 2023). This means that although increased FGAs are likely contributing to the increased scoring averages we see today, there must be another factor causing teams and players to score more points now than ever before.

In recent years, NBA fans have been growing increasingly unhappy with the amount of free throws that players have been shooting compared to years past. Many fans have expressed their frustration with the increasing number of free throws being shot in the NBA because they believe it ruins the flow of the game. For this reason, I wanted to examine if an increase in free throw attempts (FTA) could be another factor causing both players, and teams as a whole, to average more points now than in the past. Once again, I used a line chart as my visual of choice because it is most effective when searching for trends/patterns over time.

![5  Team FTA by Year](https://github.com/user-attachments/assets/c994c721-16a0-4c31-b355-84ebf221377a)
Line chart showing the average number of free throw attempts per game by NBA teams from 1997 to 2023.

Contrary to popular belief, it appears that NBA teams are actually averaging less free throw attempts (FTA) per game in the modern era than they were in eras of the past. In the 14 years between 1997 and 2010, NBA teams averaged 25.2 FTA per game, but in the 13 years since, teams have only been averaging 22.9 FTA per game. This information comes as a surprise to me, as it dispels the narrative that the majority of today’s players are inflating their scoring averages by getting to the free throw line more than players of the past. To further visualize how many points players are scoring from the free throw line, relative to the rest of their points, I used a stacked bar chart that can be filtered by year.

![6  Top Scorers and FTM](https://github.com/user-attachments/assets/d08d4154-8ae8-48ee-9c28-b40e41cf75aa)
Stacked bar chart showing the number of points that the top 15 scorers scored from the free throw line (red) and everywhere else on the court (blue) in the 2023 NBA season.

An interesting pattern that can be seen in nearly every year is that of the top 15 scorers, there are consistently two or three players who score approximately 30% of their points at the free throw line. This percentage gradually bottoms out to roughly 15% to round out the list of the top 15 scorers in the league. The best players at drawing fouls and making free throws have always scored roughly the same percentage of their points from the free throw line, while the league as a whole is actually shooting less free throws now than before. This tells us that players scoring more points from the free throw line is not a direct cause of the overall increased scoring output seen in the NBA today.

When watching an NBA game in the year 2023, it is impossible to ignore the frequency with which teams attempt three-point shots. What was once perceived as just another useful skill to have in one’s game, has now become arguably the most valuable. With teams seemingly launching an unprecedented number of shots from beyond the three-point line, many fans assume that an increase in three-point attempts is the primary driving force behind the increased scoring output seen in the league today. To visualize the increase in three-point attempts by NBA teams since the 1979-1980 season, I used a line chart.

![7  Team 3PA by Year](https://github.com/user-attachments/assets/d1597d88-8950-40ea-a7bb-4990a737ca96)
Line chart showing the average number of three-point attempts per game by NBA teams from 1980 to 2023.

As expected, the line chart supports the idea that NBA teams have drastically increased their number of three-point attempts per game since the implementation of the three-point line in the 1979-1980 season (Matange, 2022). Throughout the years, with the exception of a brief period from 1995 to 1997 when the three-point line was temporarily shortened from 23ft 9in to 22ft uniformly, there hasn’t been a more pronounced rise in three-point attempts than what has occurred over the last decade (Matange, 2022). When comparing the trends of three-point attempts (3PA) per game to those of points per game (PPG) from 1998 to 2023, they are very similar. From 1998 to 2012, both PPG and 3PA per game were increasing very gradually, but from 2012 to 2023, they both started increasing at a rapid rate. This matching pattern between points and three-point attempts over the last 25 years helps solidify the notion that three-pointers are one of the major driving forces in the increased scoring output we see in today’s NBA. To further visualize how many three-pointers players are attempting now, relative to two-pointers, I used a stacked bar chart that can be filtered by year.

![8  Top Scorer's 2PA and 3PA](https://github.com/user-attachments/assets/7dac9757-4996-40fd-b444-8619194aed06)
Stacked bar chart showing the distribution of three-point attempts (orange) and two-point attempts (blue) in the league’s top scorers in the 2023 season.

Upon analyzing the chart, an expected trend emerges. Although the number of three-point attempts from the top scorers in the league have been slowly creeping up since the three-point line was introduced, 2016 appears to be when the three-point shot became a player favourite. Prior to 2016, the top 15 scorers in the league never averaged more than 3.9 3PA per game in a single season. However, in the eight-year span since 2016, they’ve averaged 6.3 3PA per game.

![9  Average Shot Distance by Year](https://github.com/user-attachments/assets/510f37f6-5256-47a6-9f81-356607c33d03)
Line chart showing the average distance (ft) of shots in the NBA from 1997 to 2023.

In general, the average shot distance in the NBA seems to follow a similar pattern to that of three-point attempts. Both shot distance and three-point attempts have reached their highest peaks in the last few years, and are on pace to continue growing. However, it is interesting that the average shot distance has only increased by 1.5 feet since 1998, despite teams shooting almost 3x as many threes (21.5 more three-point attempts per game). To further evaluate why there was only a 1.5-foot increase in shot distance over the last 25 years, I filtered the NBA Shot Locations data set down to the most popular locations, mapped them on a shot chart using X and Y coordinates, and filtered it by year.

![10  Shot Chart Comparison](https://github.com/user-attachments/assets/cb51919f-6312-4143-8b75-af18b1e56a7c)
Shot charts comparing the most popular shot locations for NBA players in 1999 and 2019.

Although I had understood how prominent the three-point shot had become, I was very surprised to discover how obsolete the mid-range area had become as a result. Of course, there are many teams and players who strategically prioritize shooting at the rim and from behind the three-point line, but I never realized just how widespread this gameplan had become. In 1999, teams attempted approximately 38% of their shots from the mid-range (10-23ft), whereas in 2019, teams attempted only 16% of their shots from the mid-range. This discrepancy in mid-range attempts explains how teams have nearly tripled their three-point attempts in this span, while only increasing their average shot distance by 1.5 feet. It has become a league-wide strategy to emphasize shot attempts that are 0-10ft away from the rim, or behind the three-point line.

Overall, in my analysis of the evolution of NBA scoring, several interesting findings have emerged. It is important to note that both teams and individual players have been producing abnormally high scoring averages in recent years, indicating an increase in scoring compared to previous eras. This can partially be attributed to an increase in field goal attempts, as an increase in points per game follows a similar trend to that of field goal attempts per game. However, the sheer volume of three-pointers attempted in recent years is likely the most significant factor contributing to the amplified scoring numbers we have seen in recent years. In the last 20 years alone, the number of three-point attempts per game has tripled, and shows few signs of slowing down. The majority of the league has seemingly abandoned the idea of scoring from the mid-range area of the court, and dedicated a large portion of their shot attempts to behind the three-point line, and at the rim, leading to more points being scored on average. On the contrary, despite many NBA fans complaining about players shooting more free throws in today’s game, the data suggests that the league as a whole is surprisingly shooting less free throws now than in years past. This makes it unlikely that free throws play a significant role in the inflated scoring numbers we’ve grown accustomed to seeing.

There are a number of potential reasons as to why teams have decided to adjust their focus on scoring mainly at the rim and from behind the three-point line. Analytically, these are the most efficient locations on the court to score from. With respect to three-pointers, it is as simple as the fact that they are worth 1 more point than any other shot on the court, and with the talent that is present in the league today, players are more than capable of scoring from these longer distances than ever before. With respect to shots at the rim, not only would players have a greater chance of scoring due to how close they are to the basket, but they would also have a greater chance of getting fouled near the rim, which would allow them to earn points at the free throw line. These two areas of the court are also very powerful together, because when you have good shooters at the three-point line, the defense has to spread out to guard them, which spaces the floor for other players to get close to the basket for efficient shots. The mid-range area of the court does not offer any of these benefits, so it’s understandable why teams would steer away from shooting there. However, the fact that it is nearing the point of extinction is concerning because it’s the very area where many of the greatest players of all time were most effective. Although there are still a handful of players that take advantage of the mid-range, it is yet to be determined if it will stand the test of time. As we’ve learned through the process of completing this analysis, the sport of basketball is constantly evolving, and I am excited to see where it goes next.

### References

Datta, S. (2023, April). NBA Stats (1947-present). Kaggle. https://www.kaggle.com/datasets/sumitrodatta/nba-aba-baa-stats/code?select=Player+Shooting.csv

Matange, Y. (2022, January 13). NBA history: The birth and evolution of the 3-point line. Sporting News Canada. https://www.sportingnews.com/ca/nba/news/nba-history-birth-evolution-3-point-line-stephen-curry-reggie-miller-ray-allen/zlqxs2380v7o1pn4oeumjhsmh

Sports Viz Sunday. (2020, June 17). NBA Shot Locations 1997-2020. data.world.
https://data.world/sportsvizsunday/june-2020-nba-shots-1997-2019/workspace/data-dictionary

StatMuse. (2023). Who has the highest career points per field goal attempt with at least 10 points per game. StatMuse. https://www.statmuse.com/nba/ask/who-has-the-highest-career-points-per-field-goal-attempt-with-at-least-10-points-per-game


