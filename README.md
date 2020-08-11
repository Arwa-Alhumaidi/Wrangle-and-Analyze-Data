# Wrangle and Analyze Data Project
Udacity Data Analyst Nanodegree - Project 4

# Introduction
This project is part of Udacity’s Data Analyst Nanodegree program, and it’s about wrangling and analyzing data. The dataset that I will be wrangling is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs.

WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. The account was started in 2015 by college student Matt Nelson, and has received international media attention both for its popularity and for the attention drawn to social media copyright law when it was suspended by Twitter for breaking these aforementioned laws. It is frequently posting humorously about the rate pictures of dogs, and almost always the giving rating over 10 with a funny description.
I will show some of the insights and visualizations that I noticed them when I wrangled data on the tweets for this account (@WeRateDogs).

### The method of data wrangling is split into three important sections: 
- Gathering data. 
- Assessing data. 
- Cleaning data.

# What Software Do I Need?
- You need to be able to work in a Jupyter Notebook on your computer.
- The following packages (libraries) need to be installed: pandas, NumPy, requests, tweepy, json, matplotlib, seaborn. You can install these packages via conda or pip.
- You need to be able to create written documents that contain images and you need to be able to export these documents as PDF files.

# Key Points
Key points to keep in mind when data wrangling for this project:
- We only want original ratings (no retweets) that have images. Though there are 5000+ tweets in the dataset, not all are dog ratings and some are retweets.
- Fully assessing and cleaning the entire dataset requires exceptional effort so only a subset of its issues (eight (8) quality issues and two (2) tidiness issues at minimum) need to be assessed and cleaned.
- Cleaning includes merging individual pieces of data according to the rules of tidy data.
- The fact that the rating numerators are greater than the denominators does not need to be cleaned. This unique rating system is a big part of the popularity of WeRateDogs.
- We do not need to gather the tweets beyond August 1st, 2017. We can, but note that we won't be able to gather the image predictions for these tweets since we don't have access to the algorithm used.

# Gathering Data
I gathered the data from three different sources:
1. The WeRateDogs Twitter archive: I downloaded this file (twitter_archive_enhanced.csv) manually from Udacity’s website.
2. The tweet image predictions: this file (image_predictions.tsv) is hosted on Udacity’s servers and I downloaded programmatically using the Requests library.
3. Twitter API: by using the tweet IDs in the WeRateDogs Twitter archive, query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file.

# Assessing Data
After gathering the data, I assessed them visually and programmatically for quality and tidiness issues. In the end of assessing process, I detected and documented many points about quality and tidiness issues as following:

## Quality Issues
### twitter_archive 
- Delete retweets to keep the original tweets because we want only original ratings that have images.
- The data type of (tweet_id) column should be converted to string.
- The data type of (timestamp) column should be converted to date.
- Remove the rows and columns that we don't need them.
- The numerator and denominator columns have invalid values.
### image_predictions
- Remove duplicate in (jpg_url).
- The data type of (tweet_id) column should be converted to string.
- Capitalize the first letter of (p1, p2, p3) columns values.
- p1,p2 and p3 have (_ and -) instead of space.
- Remove columns that we don't need them.
### df_tweet
- The data type of (tweet_id) column should be converted to string.

## Tidiness Issues
- Merge the three dataframes into one dataframe.
- Melt (doggo, floofer, pupper, puppo) columns into one column.

# Cleaning Data
The third process of wrangling the data is cleaning. First, I made copies of the DataFrames. Second, I started to clean quality issues, then tidiness issues. In every issue, there were three key steps: define, code and test.

# Files
- act_report: Communicates the insights and displays the Visualizations produced from the wrangled data.
- image_predictions.tsv: Data downloaded using Requests library and URL.
- tweet_json.txt: Data gathered from twitter API.
- twitter_archive_enhanced.csv: File downloaded from Udacity.
- twitter_archive_master.csv: The clean DataFrame.
- wrangle_act.ipynb: The main file containing all the gathering, wrangling and analyzing work.
- wrangle_report: Briefly describes my wrangling efforts.

# Resources
- Twitter API
- Files downloaded from Udacity
- https://en.wikipedia.org/wiki/WeRateDogs
