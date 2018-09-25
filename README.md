# Subreddit Classification Project

### Repo Overview

#### File Tree
```bash
.
+-- README.md
+-- Assets
|   +-- coefficients.csv
|   +-- model_scores.csv
|   +-- model_1.png
|   +-- nb_waterfall.png
|   +-- logreg_waterfall.png
+-- Code
|   +-- starter-code.ipynb
+-- Data
|   +-- raw_reddit_scrape.csv
|   +-- reddit_scrape_cleaned.csv
+-- Requirements
|   +-- requirements.txt
```
___
### Description

The news cycle in the past few years and especially in the past few months has been dominated by the investigation of President Trump by Special Counsel Robert Mueller. Discussion and dissection of this investigation, as well as the actions of both President Trump and Mr. Mueller, have become a major cultural phenomenon. 

In this project, I investigated how people were responding to this phenomenon through the wesbite [Reddit]("https://www.reddit.com"). I selected two specific subreddits to investigate: 
- r/The_Donald is a subreddit that supports Trump
- r/The_Mueller is a subreddit that supports Mueller's investigation

Intuitively, I believed that users in the two subreddits would be discussing the same topics and using similar words to express very different sentiments. Using reddit's API, I collected posts from both subreddits in order to determine which features are most important in determining which subreddit a post came from.

More specifically, my goals in this project were two-fold:
1. Determine what the most important features, including meta data about the post and features extracted through NLP, are in deciding which subreddit a post came from
2. Build the most accurate prediction model I possibly could.

___
#### Data Collection

Data was collected for this project using the reddit API as well as the [PRAW]('https://praw.readthedocs.io/en/latest/').

#### Modeling Process

In this project I used multiple iterations of multiple classification algorithms to try and build the most successful model in terms of accuracy.
Models I attempted include:
- Multinomial Naive Bayes
- Logistic Regression
- Random Forests
- Bagging Models
	- Base estimator: Logistic Regression
	- Base estimator: Decision Trees
- AdaBoost Classifier

#### Results

I found that the titles alone were insufficient information for building a strong predictive model. However by adding more features I was able to create some extremely accurate models. My most effective model was created using an AdaBoost Classifier, which scored 99.3% accurate on a holdout set.
