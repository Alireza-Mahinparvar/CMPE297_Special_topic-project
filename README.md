# CMPE297 Special_topic-project

## Collaborative Filtering - Singular Value Decomposition project

## Group Members

* Shanmukh Krishna                 - 016005743
* Alireza Mahinparvar              - 014295437
* Satya Sai Roopa Sree Chiluvuri   - 016005795
* Yashwanth Kumar Nelakuditi       - 015918604

<b>Project description</b>

The rapid growth of data collection has led to a new era of information. Recommendation Systems are a type of information filtering systems as they improve the quality of search results and provide items that are more relevant to the search item or are related to the search history of the user. In this project, we'll be building a baseline Movie Recommendation System using TMDB 5000 Movie Dataset. For us the idea is to calculate the similarities between the movies in the dataset using similarity measures like cosine or pearson’s correlation. But with this we will face issues like scalability and sparsity. One way to handle this is to leverage a latent factor model to find the similarities between the items and users.

This is the point where Singular Value Decomposition (SVD) comes to the rescue. SVD decreases the dimension of the utility matrix by extracting its latent factors. Essentially, we map each user and each item into a latent space with dimension r. Therefore, it helps us better understand the relationship between users and items as they become directly comparable.


<b>Dataset</b>

The “ratings” dataset which we have used in our project is from Kaggle. Due to the limited computing capacity, we have used a shortened version of the dataset which named as ratings_small.csv
userid - a unique identifier for each user
movieid - a unique identifier for each movie
rating - rating of a movie given by a user
timestamp - time at which this rating has been given



