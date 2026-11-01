**NHL Team Performance Analysis (1990–2011)**

The professional ice hockey industry is highly competitive, with team success influenced by several factors, including offensive effectiveness, defensive strength, winning consistency and overall match performance. Analyzing historical performance data provides valuable insights into these factors and helps stakeholders understand competitive trends, evaluate team performance and identify areas for improvement.

This project focuses on analyzing historical hockey team statistics from 1990 to 2011, covering 35 teams and 40,331 games. Using data analytics and visualization techniques, the analysis examines key performance indicators, including total wins, losses, win rate, goals scored, goals conceded, overtime losses and goal difference. It also explores seasonal participation trends and compares team performance to identify the most successful and least successful teams across the period.

<img width="1626" height="803" alt="NHL Dashboard" src="https://github.com/user-attachments/assets/3707d7cc-6fff-47e0-be7c-8888a36a7ace" />

**Aim of the Analysis**

The primary aim is to transform historical hockey statistics into meaningful insights that reveal patterns of competitive dominance, offensive and defensive effectiveness, and changes in league participation. The findings are intended to support performance evaluation, competitive benchmarking and data-driven decision-making within the professional ice hockey industry.

**Objectives of the Analysis**

The primary objective of this project is to evaluate team performance across multiple seasons using key performance indicators to identify competitive trends, strengths and weaknesses.

The specific objectives are to:

1. Analyze Seasonal Performance: Examine win trends across seasons to identify changes in team competitiveness.

2. Identify Top-Performing Teams: Determine the five teams with the highest number of wins.

3. Assess Team Performance Challenges: Identify teams with the highest losses to highlight potential performance weaknesses.

4. Evaluate Offensive Performance: Determine the teams with the highest goals scored (GF).

5. Assess Defensive Performance: Identify teams with the highest goals conceded (GA).

6. Compare Team Participation: Analyze total games played by each team to provide context for performance comparisons.

7. Examine Overtime Performance: Evaluate overtime losses to understand how teams perform in closely contested matches.

8. Measure Overall Team Effectiveness: Use goal difference to assess the balance between attacking and defensive performance.

**Analytical Tool Used**

The analysis was conducted using Python and the Pandas library to scrape, extract and organize historical hockey team statistics from the web. The extracted data was subsequently imported into Microsoft Power BI, where data cleaning, transformation and preparation were performed to ensure consistency and analytical accuracy. Power BI was also used to develop interactive dashboards and visualizations, enabling the exploration of key performance indicators, seasonal trends and team comparisons. These tools provided a structured approach to transforming raw web data into meaningful insights that support performance evaluation and data-driven decision-making.

**2.0 Story of Data**

**Data Source:** The dataset used for this project was extracted from https://www.scrapethissite.com/pages/forms/ through web scraping techniques implemented in Python, providing historical hockey team statistics for subsequent data cleaning, transformation and analysis.

**Data Structure:** The dataset contains 5,600 data points relating to professional ice hockey team performance over 15 seasons. It is organized in a structured tabular format, with each row representing an individual team-season record and each column capturing a specific performance attribute. The key attributes include Team, Year, Wins, Losses, Overtime Losses (OT Losses), Win Percentage (Win %), Goals For (GF), Goals Against (GA), Goal Difference and Total Games Played. Collectively, these variables provide a comprehensive foundation for evaluating team performance, identifying seasonal trends, comparing offensive and defensive effectiveness, and assessing overall competitiveness across the teams analyzed.

**Story Data is Telling:** The dataset tells the story of competitive performance in professional ice hockey, revealing how teams perform across different seasons in terms of victories, defeats, scoring ability and defensive strength. Through seasonal trends and team comparisons, the analysis highlights the most successful teams, identifies those struggling to maintain competitive performance, and examines the relationship between goals scored, goals conceded and overall results. Ultimately, the data provides insights into team consistency, offensive effectiveness, defensive performance and competitive dominance, helping stakeholders understand what separates high-performing teams from their competitors.

**3.0 Data Splitting and Preprocessing**

**Data Cleaning:** To ensure data quality and establish a reliable foundation for analysis, the dataset was initially examined for empty rows, missing values and duplicate records. The validation process confirmed that there were no empty rows or duplicate records. Following this initial assessment, the dataset was imported into Microsoft Power BI, where further data cleaning, transformation and preparation were carried out using Power Query to ensure consistency and suitability for analysis.

**Data Transformation:** During the data transformation phase, additional measures and a calculated column were created using Data Analysis Expressions (DAX) in Power BI to support the analysis and generate key performance indicators. A new calculated column, Total Games, was introduced to determine the total number of games played by each team in each season. Additional measures were also developed to calculate the overall win rate and distinct number of teams represented in the dataset.

The new measures created include:

1. Win Rate (%)

Win Rate (%) =

DIVIDE(

SUM('Hockey Team'[Wins]),

SUM('Hockey Team'[Total Games]),

0

)

This measure calculates the proportion of games won relative to the total games played.

2. Team Count

Team Count =

DISTINCTCOUNT('Hockey Team'[Team Name])

This measure calculates the total number of unique teams represented in the dataset.

The calculated column created is:

3. Total Games

Total Games =

'Hockey Team'[Wins] +

'Hockey Team'[Losses] +

COALESCE('Hockey Team'[OT Losses], 0)

This column calculates the total games played by each team per season by summing wins, losses and overtime losses, treating blank overtime loss values as zero.

Together, these DAX calculations provide additional analytical dimensions and enable more accurate evaluation of team participation, winning performance and seasonal statistics.

**Data Splitting:** The dataset was divided into two main analytical categories to facilitate a more focused assessment and provide clearer insights.

**A. Category One - Independent value**

Team

Year

**B. Category Two - Dependent value**

Wins

Losses

OT Losses

Win %

Goals For (GF)

Goals Against (GA)

Goal Difference

Total Games

**Industry Context:** The dataset falls within the sports industry, specifically the Professional Ice Hockey (National Hockey League - NHL) sector. It focuses on team performance analysis, covering match outcomes, wins, losses, overtime losses, goals scored, goals conceded and goal difference across multiple seasons.

**Stakeholders:** The stakeholders of this project include the Team executives and management, coaches, technical staff and sports analysts, as they are most likely to use the findings directly for performance evaluation and strategic decision-making.

**Success to the Industry:** Success means building a competitive, consistent and financially sustainable team capable of achieving strong results over multiple seasons.

**4.0 Potential-Analysis**

Areas identified for potential analysis during the pre-analysis phase are outlined below.

1. Seasonal Win Performance Trend

2.Top 5 Teams with the highest wins overtime

3.Top 5 Teams with the highest losses overtime

4.Best Performing Team by Goals For(GF)

5.Team with most Goals Against(GA)

6.Team by Total Games played

7.Team by Overtime Loss(OT)

8.Team by Goal Difference

**Pre-Insights**

1. Seasonal Win Performance Trend: Evaluates changes in team victories across seasons to identify performance trends and shifts in competitiveness.

2. Top 5 Teams with the Highest Wins :Identifies the five most successful teams based on total victories, highlighting their competitive dominance.

3. Top 5 Teams with the Highest Losses: Highlights teams with the highest defeats, indicating potential weaknesses in overall performance.

4. Best Performing Team by Goals For (GF): Identifies the strongest attacking team based on total goals scored.

5. Team with the Most Goals Against (GA): Identifies the team with the weakest defensive record based on total goals conceded.

6. Team by Total Games Played: Compares team participation levels to provide context for evaluating cumulative performance statistics.

7. Team by Overtime Losses (OT): Identifies teams with the highest overtime defeats, highlighting patterns in closely contested matches.

8. Team by Goal Difference: Evaluates the balance between offensive and defensive performance to identify teams with the strongest overall goal margins.

**5.0 In-Analysis**

**· Analysis - Top 5 Teams by Overall Wins**

**Observation**

Detroit Red Wings lead the overall seasonal wins by 986 wins and 480 losses in 1466 games, followed by New Jersey Devils with 905 wins and 564 losses from 1469 games. Pittsburgh Penguins occupy the place with 839 wins and 642 losses in 1481 games, whereas, Philadelphia Flyers has 836 wins and 598 losses in 1434 games. Boston Bruins on the 5th place has 816 wins and 614 losses in 1430 games overall.

**Insights**

· Detroit's dominance highlights its strong historical performance, maintaining a clear lead over other teams in total victories.

· Investigate why Detroit Red Wings maintain the highest total wins, and how do their win rates compare with other top teams?

**· Analysis - Team Performance by GA/AF**

**Observation**

Detroit Red Wings lead the overall seasonal by 5726 goals for and 4489 goals Against followed by Pittsburgh Penguins with 5557 goals for and 5274 goals against, Philadelphia Flyers recorded 5799 goals for and 4762 goals against while Vancouver Canucks accounts for 5196 goals for and4933 goals against. Buffalo Sabres recorded 5076 goals for and 4694 goals against.

**Insights**

Why did the Philadelphia Flyers record the highest goals scored (5,799) among the listed teams?

What factors enabled the Detroit Red Wings to maintain a relatively low goals-against total (4,489)?

Why did the Pittsburgh Penguins concede more goals (5,274) than the other listed teams?

**· Analysis - Team with Highest Loss Total**

**Observation**

New York Islanders recorded the highest loss overtime of 819 losses followed by Edmonton Oilers with 758 losses, Tampa Bay with 732 losses, Los Angeles King with 707 losses and Toronto Maple Leaf with 695 losses.

**Insights**

Investigate whether these high loss totals result from defensive weaknesses, poor offensive output, inconsistent seasonal performance or simply a higher number of games played.

**· Analysis - Team by Goal difference**

**Observations**

The top 3 teams with the highest goal difference are Detroit Red Wings leading with 1237 GD followed by New Jersey Devils with 673 GD and Philadelphia Flyers with 437 GD while the 3 teams with the highest negative goal difference include Tampa Bay Lightning with (– 784), New York Islanders (-631) and Atlanta Thrashers (-549).

**Insights**

· What factors contributed to the Detroit Red Wings' significantly higher goal difference of +1,237?

· 2.What factors contributed to the Tampa Bay Lightning's substantial negative goal difference of -784?

**· Analysis - Seasonal Trend by Team Count**

**Observations**

Team participation increased from 21 teams in 1990 to 26 teams by 1993, remaining stable through the 1997 season. Participation subsequently grew to 30 teams by 2000 and remained unchanged through the 2011 season, indicating periods of league expansion followed by stability

**Insights**

What factors contributed to the increase in team participation between 1990 and 2000?

Which seasons recorded the most significant increases in the number of participating teams?

Investigate how league expansion influenced competitive balance, team performance and the overall development

**6.0 Post-Analysis and Insights**

**Overall League Performance**

Between 1990 and 2011, a total of 40,331 hockey games were played by 35 teams, resulting in 21,501 wins and 18,830 losses. This represents an overall win rate of 53.33%, with 136,225 goals scored across the period.

These figures provide an overview of the league's competitive performance and scoring activity.

**Top-Performing Teams by Wins**

The Detroit Red Wings recorded the highest number of victories, with 986 wins and 480 losses from 1,466 games. They were followed by the New Jersey Devils with 905 wins and 564 losses from 1,469 games.

The Pittsburgh Penguins ranked third with 839 wins and 642 losses, followed by the Philadelphia Flyers with 836 wins and 598 losses. The Boston Bruins completed the top five with 816 wins and 614 losses from 1,430 games.

These results highlight the strong historical performance of the Detroit Red Wings and their competitive advantage over other leading teams.

**Offensive and Defensive Performance**

The Philadelphia Flyers recorded the highest goals scored among the highlighted teams, with 5,799 goals for and 4,762 goals against. The Detroit Red Wings followed closely with 5,726 goals scored and 4,489 conceded, demonstrating a strong balance between offensive and defensive performance.

The Pittsburgh Penguins recorded 5,557 goals for and 5,274 against, while the Vancouver Canucks registered 5,196 goals for and 4,933 against. The Buffalo Sabres recorded 5,076 goals for and 4,694 against.

The findings suggest that strong offensive output, combined with effective defence, contributes significantly to overall team competitiveness.

**League Expansion and Team Participation**

Team participation increased from 21 teams in 1990 to 26 teams by 1993, remaining stable through 1997. The league subsequently expanded to 30 teams by 2000, maintaining this number through 2011.

This reflects two significant periods of expansion followed by sustained participation stability.

**Teams with the Highest Losses**

The New York Islanders recorded the highest number of losses, with 819 defeats, followed by the Edmonton Oilers with 758. The Tampa Bay Lightning recorded 732 losses, while the Los Angeles Kings and Toronto Maple Leafs recorded 707 and 695 losses, respectively.

These figures identify teams with comparatively high cumulative defeats and provide an opportunity to investigate their historical performance challenges.

**Goal Difference Performance**

The Detroit Red Wings recorded the highest positive goal difference at +1,237, followed by the New Jersey Devils at +673 and the Philadelphia Flyers at +437.

Conversely, the Tampa Bay Lightning recorded the lowest goal difference at -784, followed by the New York Islanders at -631 and the Atlanta Thrashers at -549.

The significant difference between the highest and lowest goal margins highlights variations in offensive effectiveness and defensive strength across the league.

**7. Charts and Visualizations**

<img width="563" height="324" alt="Screenshot 2026-11-01 142949" src="https://github.com/user-attachments/assets/e55501f9-9287-4d56-b1cb-5f0bd81da5dc" />

This column chart shows the total games played, total wins and total losses by the top performing teams between 1990–2011.

<img width="446" height="323" alt="Screenshot 2026-11-01 143020" src="https://github.com/user-attachments/assets/3e39ac52-5adf-4263-bcda-01c2641fb3e7" />

This bar-chart the teams with the highest total losses of all season and New York Islanders recorded the highest losses.

<img width="673" height="342" alt="Screenshot 2026-11-01 143037" src="https://github.com/user-attachments/assets/e01bf5bd-f55a-4c99-ae02-f225f58a180c" />

The line chart shows the total number of teams participation at each season from 1990–2011 and the highest record shows 30 teams which was steady from 2000–2011 and the lowest recorded participation is 21 teams in 1990.

<img width="390" height="336" alt="Screenshot 2026-11-01 143058" src="https://github.com/user-attachments/assets/ed1f2b4f-3c26-4ed2-a73e-64d75426decc" />

The table shows teams by their total number of goal difference where Detroit Red Wings lead by 1237 goals.

<img width="519" height="339" alt="Screenshot 2026-11-01 143146" src="https://github.com/user-attachments/assets/d748f724-c247-42c3-b9b8-4d867e95a07b" />

This bar chart shows the teams with the highest number of goals (GA/GF) and Detroit Red Wings lead the hart with 5727 goals for and 4489 goals against.

**8. Post Analysis Recommendations**

· Strengthen Performance Benchmarking: Teams should benchmark their performance against historically successful teams, particularly the Detroit Red Wings, to identify effective strategies and performance gaps.

· Address Persistent Losses: Teams with high cumulative losses should investigate seasonal performance patterns, identify recurring weaknesses and implement targeted improvement strategies.

· Monitor League Competitiveness: League administrators should continue monitoring participation, team performance distribution and competitive balance to support sustainable league development.

· Improve Defensive Capabilities: Teams with high goals-against figures and negative goal differences should prioritize defensive training, tactical adjustments and goalkeeper performance evaluation.

· Promote Consistent Performance: Coaches and management should monitor seasonal win rates, goal differences and other performance indicators to identify declining performance early and support timely interventions.

· Optimize Offensive Strategies: Teams should analyze the scoring patterns of high-performing teams, such as the Philadelphia Flyers, to identify opportunities for improving goal conversion and attacking effectiveness.

· Strengthen Player Development: Investment in player recruitment, training, fitness and talent development should be guided by measurable performance gaps and long-term team objectives.

**9. Conclusion**

The analysis demonstrates that professional ice hockey performance between 1990 and 2011 varied considerably across teams. The Detroit Red Wings emerged as the strongest historical performer in terms of total wins and goal difference, while the Philadelphia Flyers demonstrated exceptional offensive output. Conversely, the New York Islanders and Tampa Bay Lightning recorded notable performance challenges in terms of cumulative losses and negative goal differences. Overall, the findings highlight the importance of balancing offensive effectiveness, defensive strength and seasonal consistency. By leveraging historical performance data, team management, coaches and league administrators can make more informed decisions, identify performance gaps and develop strategies that promote sustained competitiveness.

**10. References**

https://www.scrapethissite.com/pages/forms/

flaticon.com
