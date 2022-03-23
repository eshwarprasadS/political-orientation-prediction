# political-orientation-prediction
Undergraduate Thesis & Project

# Data Extraction Module

![Alt text](Data_Extraction_Module.png?raw=true "Data_Extraction_Module")

Objectives of Module : 

- Twitter API (JSON output)
- List registered Democrats / Republicans, twitter crawling to extract twitter user tags and associated data
- Convert extracted JSON to processing format (Preferably CSV)

The Twitter API provides up to 200 tweets (per request) published by a user. Additionally, the API has a limit of 15 API calls per 15 minutes time window. 


Data collection to identify seed users, that is, people who were publishing content about the American election on Twitter. It is possible to obtain this identification through the API’s streaming method, which enables real-time collection of tweets. 


The objective of the real-time collection is to identify users who published tweets in English and did a retweet of a candidate’s tweet. The base hypothesis is that if a user retweeted a candidate tweet, it is highly probable that they alluded to the tweet's content to promote a political ideology.
