# mep-tweet-clustering-classification
This repository provides my solution for the 3rd Assignment for the course of Practical Data Science for the MSc in Data Science at Athens University of Economics and Business.

Investigatign a dataset of tweets made by Members of the European Parliament.Data are collected by Darko Cherepnalkoski, Andreas Karpf, Igor Mozetič, and Miha Grčar for their paper Cohesion and Coalition Formation in the European Parliament: Roll-Call Votes and Twitter Activities.

## Data Preparation

Downloading the dataset from https://www.clarin.si/repository/xmlui/handle/11356/1071 and using the retweets.csv file.
Keeping only the records for which the language of the original tweet is in English.
Getting the text of the original tweet and adding it to the dataset as an extra column. Using the Tweeter API to get the text. 
Keeping only the records for which we can download the tweet text.
Groupping the records by the European group of the MEP that posted the original tweet and dropping groups with very few tweets.

## Clustering

Converting tweet text to bag of word matrices using CountVectorizer.
Using k-means to cluster the tweets based on their text.
Stripping accents, and converting everything to lowercase.
Setting min_df=10 and max_df=50 and also removing all English stopwords.
Using both the elbow method and the silhouette score to investigate the best number of clusters and to settle on the best number of clusters.
Visualizing the clusters using Yellowbrick's InterclusterDistance.
Investigating the clusters by finding the most important features in each cluster. 

## Classification

Training at least two algorithms to learn to classify an unseen tweet. 
The target variable is the political party of the original poster and the training features are the original tweet's text.
Splitting data into training and testing datasets.
Experimenting with the different algorithms with cross validation on the training dataset to find the best hyperparameters for the best algorithm. 
To gauge the efficacy of the algorithm, we present also the results of a baseline classifier, using scikit-learn's DummyClassifier.
