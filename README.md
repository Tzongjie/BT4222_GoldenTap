# Forecasting Stock Prices using LSTM & Sentiment Analysis on Tweets
- Using historical stock prices and machine learning models to predict closing stock prices
- To understand the influence of tweets on closing stock prices  

# Folder Structure
```
BT4222_GoldenTap
    |__ .gitignore
    |__ README.md (this file)
    |__ sentiment_analysis
        |__ project_twitter_scraping.ipynb
        |__ tweets_data
            |__ *.json
        |__ README.md
        |__ requirements.txt
    |__ sentiment_analysis
        |__ Data Scraping Cleaning.ipynb
        |__ Stock Prediction Model.ipynb
        |__ stock_data
            |__ *.csv
        |__ saved_models
            |__ *.h5
        |__ README.md
        |__ requirements.txt
    |__ requirements.txt (installs required packages from both analysis)
```

# Procedure to run
1. Download the tweets data from http://bit.ly/tweets_data
2. Place tweets_data in the sentiment analysis folder
3. Download the stock data from http://bit.ly/stocks_data
4. Place stock_data in the stock prediction folder
6. Run the sentiment analysis and stock prices analysis separately
