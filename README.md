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

* userid - a unique identifier for each user
* movieid - a unique identifier for each movie
* rating - rating of a movie given by a user
* timestamp - time at which this rating has been given


![image](https://user-images.githubusercontent.com/100038612/206074108-55ee463d-603e-417d-be60-213854217acf.png)


### Workflow of the project

![image](https://user-images.githubusercontent.com/100038612/206075782-26753178-9746-4f90-b0f6-70cf8fc9e5d5.png)


###Algorithms implemented

<b>Collaborative filtering:</b>

As we all know collaborative filtering basically finds the similarity between the items and give out the most similar item. The two most common types of collaborative filtering are

<b>User-based filtering:</b>

These systems recommend products to a user that similar users have liked. For measuring the similarity between two users we can either use pearson correlation or cosine similarity.  As you can see blow as example each row represent users and each column is movie and each cell represents rating user gives to cell
In above we see for finding similarity for user E we need to use user B,C,D because A, F does not share rating common with E.


![image](https://user-images.githubusercontent.com/100038612/206075992-2fbc257c-31ec-4f1c-afe3-393ddc7baff8.png)


<b>Item-based filtering:</b> 

Item-based CF recommends items based on their similarity with the items that the target user rated. Likewise, the similarity can be computed with Pearson Correlation or Cosine Similarity. In item based recommendation we will fill the blanks vertically and not horizontally like user based. It solves the problem posed by dynamic user preference because it is more static however this method has scalability and sparsity issues.

![image](https://user-images.githubusercontent.com/100038612/206076288-7f773a0d-4f17-4fc5-beac-f9887c900f53.png)


### SVD

One way to handle these issues is to leverage a latent factor model to find similarities.
SVD decreases the dimension of the utility matrix by extracting its latent factors. We map each user and each movie into a latent space with dimension r where they become directly comparable. 
Singular Value Decomposition of an mxn complex matrix M is a factorization of the form 
                                                                                     M = UΣVT

Where U is mxm complex unitary matrix 
	Σ is mxn rectangular diagonal matrix    
	VT is conjugate transpose of V
  
  
  ![image](https://user-images.githubusercontent.com/100038612/206076427-fa821174-f0df-4b08-bb9f-99c93f60859e.png)


### SVD++

SVD++ is an extended version of SVD where it  improves precision and recall of the recommender  system. 

“++” means incorporating implicit feedback.

![image](https://user-images.githubusercontent.com/100038612/206076507-9035902b-7146-4617-86d3-6dfbef2ba199.png)


Where the yj terms are a new set of item factors that capture implicit ratings. Here, an implicit rating describes the fact that a user u rated an item j, regardless of the rating value.

<b> Hyper Parameter Tuning </b>

To find the optimal parameter values from a given set of parameters in a grid, we used a cross validation technique, GridSearchCV.

METRICS :

* Root Mean Square Error ( RMSE )  : It is frequently used to measure the differences between values predicted by a model and the values observed.

* Mean Absolute Error ( MAE ) :  It measures the difference between the measured values and true values.

We used RMSE  and MAE to measure the performance of the modes

### Results 

![image](https://user-images.githubusercontent.com/100038612/206076823-7de88a41-ba55-424d-99e6-9b6bd408edd5.png)


![image](https://user-images.githubusercontent.com/100038612/206076869-45cdd285-895b-4823-a70b-3aee1694c965.png)


### Other Algorithms used

     We also tried other algorithms such as KNNWithMeans, NMF,  BaselineOnly etc.,


![image](https://user-images.githubusercontent.com/100038612/206077134-2319194c-28ed-4d97-a0f0-1563b2ba7b2a.png)


### Conclusion

In conclusion, we have  evaluated results by implementing various models such as SVD and SVD++ along with hyper parameter tuning to find the best predictor among them.

### Future Scope

* SVD is a very popular technique that can be found in other libraries as well. So we can use the SVD present in other libraries and perform the same operations and can compare the results obtained by other SVD’s.
* The input used in this project is a dense matrix. This can be converted into a sparse matrix and perform the predictions and observe the results obtained.


### Systems requirements to install and run the project:
1. Install python
   You can install the latest python version from here.
2. Installing jupyter
   Installation for python and Jupyter notebook is easy. By going to website below
   Download Python | Python.org you can install python software on your compute. Also by 
   Following this website Project Jupyter | Installing Jupyter you can install Jupyter notebook 
   That fits your system. Please make sure to install pip module on your command line as well
   by entering the command “python get-pip.py”.
3. Installing libraries
   In your jupyter notebook please type the below commands to install the libraries.
      - pip install surprise
      - pip install pandas
      - pip install numpy
      - pip install pickle

<b> Dataset Link</b>
https://www.kaggle.com/code/erikbruin/movie-recommendation-systems-for-tmdb/data












