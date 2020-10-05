### [Text Mining Hackathon](https://2020.whyr.pl/hackaton/) Challenges

# Table of contents

- [Winners](#winners)
- [Hacker News Analysis](#hacker-news-analysis)
- [Your role](#your-role)
- [Criteria](#criteria)
- [Descriptions of challenges](#descriptions-of-challenges)
- [Datasets](#datasets)

# Winners

# Challenge 1 - Predictions

<img src="https://raw.githubusercontent.com/WhyR2020/hackathon/master/img/1.jpg" alt="main" />

- [Video](https://youtu.be/DYc6H1UWnXI)
- [Slides](https://github.com/WhyR2020/hackathon/blob/master/solutions/challenge1.pptx)

# Challenge 2 - Segmentation

<img src="https://raw.githubusercontent.com/WhyR2020/hackathon/master/img/2.jpg" alt="main" />

- [Video](https://youtu.be/Qzt9RwdRtJk)
- [Slides](https://github.com/WhyR2020/hackathon/blob/master/solutions/challenge2.pptx)
- [Code](https://github.com/mwkyuen/whyR_challenge2/)

# Challenge 3 - Churn

<img src="https://raw.githubusercontent.com/WhyR2020/hackathon/master/img/3.jpg" alt="main" />

- [Video](https://youtu.be/FpQkolfxgZM)
- [Slides](https://github.com/WhyR2020/hackathon/blob/master/solutions/challenge3.pptx)
- [Code](https://github.com/dszokolics/hackathon-2020)

# Challenge 4 - Text Analysis / Revealing the content

<img src="https://raw.githubusercontent.com/WhyR2020/hackathon/master/img/4.jpg" alt="main" />

- [Video](https://youtu.be/mkLc53uuGQ8)
- [Slides](https://github.com/WhyR2020/hackathon/blob/master/solutions/challenge4.pptx)
- [Code](https://github.com/kornelro/whyr_hack)


# Hacker News Analysis

## What is [Hacker News](https://news.ycombinator.com/newswelcome.html)?

A social forum under https://news.ycombinator.com/ focusing on computer science. It allows users to post articles, questions, job offers and a show-off of their projects. Under each category users are able to comment on each item (an article, a question, a job offer or a show-off). The portal maintains clear guidelines https://news.ycombinator.com/newsguidelines.html on how and what to submit that makes the content of the forum up to high quality standards of the open access conversations.

## Hacker News API

Hacker News provides a rich [API](https://github.com/HackerNews/API) that allows it to collect data about the traffic on the site, that includes comments, user actions and posts. Thanks to the API we will be able to build up insights about trends and mine knowledge about the Hacker News community.

A useful R client [szymanskir/hackeRnews](https://github.com/szymanskir/hackeRnews) made it possible to prepare data for this language-agnostic [Text Mining Hackathon](https://2020.whyr.pl/hackaton/) at [Why R? 2020 conference](https://2020.whyr.pl).

# Your role

A language agnostic competition devoted to text mining where every machine learning practitioner can find challenges to test his/her team!

Imagine your current role is being responsible for facing business needs to understand the traffic and the audience of Hacker News. Get into the shoes of a business analyst at the forum!

Help your business team to understand characteristics of users and patterns of behaviors that they follow. What articles need to be added to boost the audience size? What triggers the amount of actions taken on the website? How we can improve the number of positive comments. What are the most polarizing topics found in published articles? Can you group users in meaningful segments? What drives users to churn? What makes them comment?

## Solutions

At this hackathon you can scale the level of difficulty and the area of challenges on your own. Depending on skills and the time that you have you can tune the fun on your own!

Please send your solutions for every challenge as a separate (max 5 min) video. Each video presenting the solution should be published online and you should fill [this form](https://forms.gle/D8eskXZka9HGQVC88) with a team’s name and the url to the video (form closes at 2020-09-24 5:30 pm UTC). When making a video that presents a solution keep in mind below criterias. For the challenge 1 please submit a short video presenting how you come up with predictions and please send predictions to kontakt_at_whyr.pl no later than 2020-09-24 5:30 pm UTC. You can also add a url to the presentation or the dashboard that you made to present your insights.

**You already should realize that the deadline for solutions is 2020-09-24 5:30 pm UTC.**

Check out the last chapter about [going one level higher](#going-one-level-higher)

# Criteria

- Whether there are at least 3 people in the team?
- Is the presentation based on HackeR News data?
- Is the solution a result of the teamwork?
- Is the solution hosted in a public place?
- Is this solution useful for the imaginary business team at Hacker News or has potential/clear business applications/story?
- Is there a clear business problem/story that you are explaining?
- How attractive is the use case?
- How well are you able to present your solution?
- Is the solution explainable?
- Does the used solution have any statistical validation?


Presented solution should be submitted as a video. It is nice to have if a solution is based on a presentation or a dashboard. For challenges 2-4 the winning solution will be chosen based on insightfulness and usefulness of identified patterns. For challenge 1 the winning solution will be chosen based on a cost function however we would like to know how did you get into such predictions?

# Descriptions of challenges

## Challenge 1 - “Warm up predictions”

Based on historical data of **stories** appearing on Hacker News in 2020 predict

- The number of new articles to appear between 2020-09-25 00:00 UTC - 2020-09-26 00:00 UTC
- The total number of new comments under stories published between 2020-09-25 00:00 UTC - 2020-09-26 00:00 UTC
- The highest number of points obtained by a single article (recorded at 2020-09-26 00:00 UTC) for articles published after 2020-09-25 00:00 UTC

Try to minimize the final cost function: 

```{R}
abs((predicted_n_articles-actual_n_articles)/actual_n_articles) +
abs((predicted_n_comments-actual_n_comments)/actual_n_comments) +
abs((predicted_highest_number_of_points-actual_highest_number_of_points)/actual_highest_number_of_points)
```
## Challenge 2 - “Segmentation”

Based on historical data of some **comments** create meaningful segments of users. Can you propose any statistical measures of goodness of fit to describe the quality of the segmentation solution?

Below we present some inspirations for potential characteristics that may eventually differentiate segments:

- What is the sentiment of comments made by each group?
- What are the common words-association within each group based on comments?
- What are the keywords of titles of articles under which comments are made?
- What amount of comments is done by which segment?
- What are the characteristics of each group? 
- What articles do they comment about and what do they write about? 
- What is the high-level summary of groups? 

Please keep in mind a segmentation solution should have balanced segments sizes and meaningful stories behind the groups of users.

## Challenge 3 - “Churn”

Based on historical data of some **comments** execute a churn analysis so that business can understand what patterns and activities drive users to churn.

The below set of questions might inspire you to craft the story:

- When should we consider a user to have churned?
- What is the typical length of history/live of a user?
- Do users tend to be active only during specific periods of time or are most users active all over the history of the portal?
- What factors make some users “live” longer or shorter?

## Challenge 4 - “Revealing the content”

Ok, let’s tackle articles : ) Based on the below data of **content** find out what are the key topics described in articles?

When building an analysis that helps to understand the corpus of text, you can consider below questions

- What are the key topics described in articles? 
- Which topics are the most popular in terms of points and comments? 
- Can you divide articles in groups with meaningful characteristics and the story? 
- Can you map topics with groups of users?
- Which topics were popular during which time periods/intervals? 
- What are the most polarizing topics in terms of the sentiment?

## Going one level higher

Each challenge can be submitted in one of 2 forms: regular (with data provided by organizers) or extended (with data gathered by the team thanks to the API). You can extend each task by using the data for questions, job offers or show-offs. If API can't deliver enough data, maybe you can webscrap data from the portal? If you decide to go with an extended path you will be compared only to the teams that took the extended part for this particular challenge.

# Datasets

> To make the event more challenging and to make the competition more realistic, in terms of business realities, the **comments** and **content** articles will get updated/extended from a time to time. The **articles** dataset will not be updated.


### Articles

```{R}
library(jsonlite)
articles <- fromJSON(readLines('data/articles.json'))
```
<img src="https://raw.githubusercontent.com/MarcinKosinski/hackathon/master/img/articles.png"
     alt="articles" />

### Comments

```{R}
library(jsonlite)
comments_recent <- fromJSON(readLines('data/comments_recent.json'))
```

<img src="https://raw.githubusercontent.com/MarcinKosinski/hackathon/master/img/comments.png"
     alt="articles" />
     
### Content

Available in pieces under this [Dropbox url](https://www.dropbox.com/s/u0uzdu0ioyvmh0n/content.rar?dl=0).
We decided to split the file into smaller ones so that you can at least read some of the articles if you can't get the full file straight.
     
```{R}
library(readr)
content <- read_csv('data/content.csv')
```

<img src="https://raw.githubusercontent.com/MarcinKosinski/hackathon/master/img/content.png"
     alt="articles" />