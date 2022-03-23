# political-orientation-prediction
Undergraduate Thesis & Project

# Overall Architecture
![Alt text](Methodology_Diagram.png?raw=true "Data_Extraction_Module")

# Data Extraction Module

![Alt text](Data_Extraction_Module.png?raw=true "Data_Extraction_Module")

Objectives of Module : 

- Twitter API (JSON output)
- List registered Democrats / Republicans, twitter crawling to extract twitter user tags and associated data
- Convert extracted JSON to processing format (Preferably CSV)

The Twitter API provides up to 200 tweets (per request) published by a user. Additionally, the API has a limit of 15 API calls per 15 minutes time window. 


Data collection to identify seed users, that is, people who were publishing content about the American election on Twitter. It is possible to obtain this identification through the API’s streaming method, which enables real-time collection of tweets. 


The objective of the real-time collection is to identify users who published tweets in English and did a retweet of a candidate’s tweet. The base hypothesis is that if a user retweeted a candidate tweet, it is highly probable that they alluded to the tweet's content to promote a political ideology.

# Tweet Analysis Module

Over 86,000 tweets were collected from 24 Democrats and 24 Republicans, and these tweets were :

- Tokenized
- Lemmatized
- Stripped of Stop Words
- Encoded with each token’s frequency distribution rank
- Padded for Keras input format (numpy array of 50 length, padded with 0s)
- Split into 80% Training, 20% Testing sets of data. 

Multiple algorithms were tested, and the choice finally fell upon the two : Bidirectional RNN LSTM and BERT and the two were compared.

# Networking Module

![Alt text](Networking_Module.png?raw=true "Data_Extraction_Module")

Objectives of Module : 

To leverage :
- Followers and Followee (score on % democrat / % republican).
- Distance factor (Erdos Number).
- Retweets (% democrat / % republican).
- Polarity of Source location of tweets (% democrat / % republican).
