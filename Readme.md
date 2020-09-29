Project 3: Clustering Movies for Recommendation
--------------------------------------------------------

In this project, I have used the following datasets:
1. movies.csv
2. ratings.csv
3. tags.csv

I have used sentiment analysis on the tags dataset and combined the three datasets. Using the combined dataset, I have applied K-Means Clustering to create a recommendation cluster based on already watched movie.

Exploratory Data Analysis:
-------------------------------

I have performed some distribution plotting of the ratings and movie genre datasets which gave some good insights into which rating value or which genre were more prominent in the datasets. So, the rating distribution is skewed to the right with more values tending towards a rating of 4.0. And, from the genre distribution, I could find that 'Drama' and 'Comedy' genres were higher in number.

Feature Engineering:
-------------------------

I have used a MultiLabelBinarizer to encode the movie genre as that might be useful for clustering. Also, I have used the TextBlob package to perform a sentiment analysis on the review tags where -1 represents negative, +1 represents positive and 0 represents neutral sentiment. Finally, I have merged the movies, ratings and tags datasets to input into the KMeans clustering object.

Imputation:
-----------------

When using outer join during merging, few of the tuples had NaN values. For, rating column, I have used the mean and for the sentiment column I have used the neutral value 0 to imput the missing values.

Clustering:
-------------

I have used the KMeans clustering algorithm. After trying different values for the number of clusters, I have come to realize that the fewer clusters we have, the more number of movies are recommended. At that point, it becomes highly likely that we might end up with bad recommendations towards the end. However, for any number of recommendations, we should be able to sort the first n number of recommendations according to our desire.