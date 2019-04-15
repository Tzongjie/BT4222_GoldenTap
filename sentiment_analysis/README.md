# Sentiment analysis of Tweets and how they influence stock prices
- Python code in jupyter notebook to scrape Tweets of NASDAQ and NYSE companies
- Apply sentiment analysis on Tweets to understand census's opinions on individual companies
- Identify sentiment patterns over a time period and compare with the stock prices to identify any influences

# How to run
- Use python3 to run
- Install the required packages with requirements.txt 
- Download the tweets_data folder and start running the code from Section 2 - Reading Data from JSON file in Google Drive
- Ensure that the DATA_FILEPATH is correct and that Google Drive has been mounted (if running using colab)  

# 1. Getting Data from Twitter
- Specify Twitter Account credentials to connect to Twitter API
- Import commonly used packages
- Mount personal Google Drive that contains the pre-scrapped Tweets dataset
- Declare data directory

## 1.1 Reading Company Data
- Reads in Company data from Google Drive. Objective is to get list of company names and their respective Symbols

## 1.2 Scraping Twitter Data
- Scrapes tweets with Twitter API and writes data into JSON for each company, to the directory declared above

# 2 Reading Data from JSON file in Google Drive (With tweets_data)
- Read in tweets from the JSON file previously wrtten in tweets_data
- Exclude companies that do not have tweets
- Remove duplicated tweets in case the same tweets have been scraped twice

# 3 Sentiment Analysis
- Analyse the sentiments of tweets and understand if it will influence the stock market prices

## 3.1 Preparing Data
- Remove duplicate tweets in case of scraping of the same tweet
- Sort the tweets by ascending order, first by Symbol then by date of tweet

## 3.2 Removing unwanted patterns in tweets
- Remove Twitter handles, URLs, punctuations, symbols 
- Convert all words to lowercase
- Remove words with only 1 character

## 3.3 Removing Stopwords
- Remove stopwords from all tweets

## 3.4 Lemmetizing Tweets
- Extract the Part-Of-Speech(POS) tags from each word and lemmatize based on the identified tag
- WordCloud plot to describe the tweets for each company (1 plot for all tweets, another for Apple tweets)
- WordCloud can be performed for all the available companies

## 3.5 Performing Sentiment Analysis
- Use TextBlob to extract sentiment of tweet
- Calculate the average sentiment value per day for each company 

## 3.6 Analysing Results
- Scrape company historical stock data and compare with the average sentiment value
- Calculate the Positive-Negative Ratio for per day for each company
- Compare the plot of Positive-Negative Ratio and the historical prices of the same company