# Twitter-Data-Analysis-Project

# Overview
This project involves analyzing a dataset of tweets to extract various insights based on a specific search term. We will compute metrics such as the number of tweets per day, unique users, average likes, distribution of tweets by place IDs, and tweets posted by the hour of the day. Additionally, we identify the user who tweeted the most about the given term.

# Data Sources
The dataset consists of two TSV files (correct_twitter_201904.tsv and correct_twitter_202102.tsv), which contain various tweet-related information, including tweet text, author IDs, creation timestamps, number of likes, and geographical place IDs.

# Project Objectives
For a given search term (e.g., "Britney"), we aim to analyze the following:

 1. **Tweets per Day:** The number of tweets that contain the search term, aggregated by day.
 2. **Unique Users:** The number of distinct users who tweeted using the search term.
 3. **Average Likes:** The average number of likes received by tweets containing the search term.
 4. **Place IDs:** A count of the top 10 most common place IDs (locations) associated with tweets containing the term.
 5. **Tweets by Hour:** The distribution of tweets by the hour of the day (from 0 to 23).
 6. **Top User:** The user who posted the most tweets containing the search term.

# Methodology
1. **Data Loading**
We use the pandas library to load and combine the two datasets. After loading, the datasets are concatenated into a single DataFrame for analysis.

2. **Data Filtering**
We search for tweets containing the given term (e.g., "Britney") using case-insensitive string matching on the 'text' column. The filtered subset is then analyzed further.

3. **Analysis and Metrics**

 1. **Tweets per Day:** We group the tweets by the created_at timestamp (converted to a date format) and count the number of tweets posted each day.
 2. **Unique Users:** We use the nunique() method to count the distinct author_id values.
 3. **Average Likes:** We calculate the mean of the like_count column for the filtered tweets.
 4. **Place IDs:** We count the occurrences of place_id and display the top 10 most frequent locations.
 5. **Tweets by Hour:** By extracting the hour from the created_at timestamp, we can group the tweets by the hour of the day and count the number of tweets posted in 
 each hour.
 6. **Top User:** We find the user with the highest number of tweets by using value_counts() on the author_handle column.

4. **Visualization**
We use matplotlib to generate visualizations for:

 1. **Tweets per Day:** A bar chart showing the number of tweets posted each day.
 2. **Tweets by Hour:** A bar chart showing tweet frequency by the hour of the day.
 3. **Top Place IDs:** A bar chart displaying the top 10 most frequent place IDs.

5. **Sample Output**
Upon running the code with the term "Britney", we get the following output:

 1. **Tweets per day:** A DataFrame showing the number of tweets per day.
 2. **Unique users:** A count of distinct users who posted tweets with the term.
 3. **Average likes:** The mean number of likes per tweet containing the term.
 4. **Top place IDs:** The top 10 locations (place IDs) associated with the tweets.
 5. **Tweets by hour:** A distribution of tweets posted by the hour of the day.
 6. **Top user:** The user who tweeted the most about the term, along with their tweet count.

# How to Run
Install the required libraries:
bash
Copy code
pip install pandas matplotlib
Load the dataset into a Pandas DataFrame.
Call the analyze_tweets() function with the DataFrame and the search term.
The function will return a dictionary containing the results and display visualizations.

# Conclusion
This analysis provides useful insights into the activity and engagement around a specific search term on Twitter. By understanding tweet frequency, user engagement, and geographical distribution, we can derive meaningful conclusions and identify key trends.
