## Project Background
News recommender systems are crucial to user interaction with news and information delivery services. In 2020, Tsinghua University and Microsoft researchers built the MIND dataset, a collection of 1 million user logs and 160,000 news articles displayed in Microsoft News, to better understand news recommender systems. By studying this dataset, we aim to answer various questions about the efficacy of Microsoft’s recommender system, how different types of users interact with Microsoft News, and whether the recommender system has obvious effects on user behavior. The overarching question we are most curious about is how recommenders treat new users, a phenomenon called the cold-start problem. How should an algorithm recommend articles to largely undefined users? We are particularly interested in this question because there is only sparse research on the topic, despite the fact that every user is a new user at some point in time. 

## MIND: MIcrosoft News Dataset
https://msnews.github.io

## Project Goals

### Main goal :
Gain insights into user engagement patterns and assess the effectiveness of news recommendations, with a specific focus on new users, their initial interactions, and the potential formation of echo chambers. By examining click-through rates, sentiment, content preferences, and user segmentation based on interests, we aim to identify trends that can enhance targeted recommendations, encourage diverse content exposure, and improve user retention across various news categories.

### Sub goals:
* Prepare and organize data for analysis
  * Clean and merge the behavior and news datasets
* Conduct exploratory analysis
  * Review previous research
  *  Explore user engagement patterns, such as categories watched, types of articles clicked, and recommendation timing
*  Analyze click-through rate (CTR) to better understand user-interaction
*  Perform sentiment analysis on news articles for users with no history but have recommedantions
  * Use Vader to analyze abstracts and titles to see if users tend to pick articles that are more positive, neutral, or negative
* Identify specific news sources and extract key words from article titles for analysis
* Classify users into subgroups(i.e political groups, etc)



[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/EqWXl6Ay)
