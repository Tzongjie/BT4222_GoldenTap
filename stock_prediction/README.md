# LSTM Model for predicting stock closing prices
- Python code in jupyter notebook to scrape daily historical stock prices of an identified list of NASDAQ and NYSE companies
- Python code in jupyter notebook to build a LSTM Model that trains and predicts on the closing prices of stock firms.
- Employ the LSTM Model to learn the patterns of historical stock prices of an industry with the identified optimal window lag period
- Evaluate the model prediction performance

# How to run
- Use python3 to run
- Install the required packages with requirements.txt
- Download the stock_data folder into this subfolder and unzip it if it isn't already
- As the stock data are already scraped, you don't need to run the code from 'Data Scraping Cleaning.ipynb'. You only need to run the code for the 'Stock Prediction Model.ipynb' on jupyter environment

# 1. Getting Data from Yahoo Finance [don't need to run]
- Imports commonly used packages for scraping stock data from Yahoo Finance

## 1.1 Reading Company Data
- Reads in 'companylist.csv' to get the list of company names and their respective symbols for the objective to retrieve historical stock data of stock firms.

## 1.2 Scraping Stock Data
- Scrapes daily historical stock data of each company using pandas_datareader and saves each firm's daily historical stock data as csv files in the name format of '<stock_symbol>.csv' into the stock_data folder

## 1.3 Cleaning the Datasets
- Cleans datafiles in stock_data folder to only retain dataset that has 3 years' worth of records for each stock firm
- Outputs an additional file called 'updated_companylist.csv' to only include the company stock symbols that were remained in the folder after cleaning. This list will be used in the 'Prediction Stock Model' jupyter notebook.

# 2 Prediction Stock Model
- Imports commonly used packages for scraping stock data from Yahoo Finance
- Builds a LSTM model that predicts future closing prices of IT stock firms

## 2.1 Preprocessing the Data
- Reads in 'updated_companylist.csv' to get the list of company stock symbols remaining. This list is used in the data preprocessing and training and testing of the LSTM model
- Sets the datasets to contain window_size information
- Split each firm's data into train and test sets

## 2.2 Building the LSTM Model
- Imports keras package for building LSTM models
- Sets the hyperparameters of the model. Tuning is also carried out in this section
- Fits the model with the training data
- Saves each model while tuning. Our final model is named 'final_model.h5'

## 2.3 Predicting Future Stock Prices
- Uses the trained model to test and predict the future stock prices
- Compare the performance by plotting the time series
- Calculates the average mean squared error (MSE) and root mean squared error (RMSE) of the model to track the performance of the model
