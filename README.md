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

# Conclusions and Summary

- We believe that this is a scientific step towards more research into the leverageable aspects of twitter data in Computational Political Science. 
- The twitter social graph can further be made more effective if a reliable cached version of twitter data could be found that is easy to traverse, considering that the rate limiting on twitter API makes any kind of social networking algorithm ineffective as of now. 
- The handling of tweet content analysis and classification can further be improved to handle spam accounts. It is also to be noted that sarcasm is yet to be handled by our model and additions could be made to account for this. 
- Works on detecting sarcasm have emerged and this is a perfect opportunity to employ various NLP tasks, as our model is readily adaptable to any kind of social network that allows messaging or publishing of opinions and links such as friends or followers, such as Facebook, Twitter and Reddit.
