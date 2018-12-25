# tweets-k-means
Tweets clustering K-means

Problem:

Implement the tweet clustering function using the Jaccard Distance metric and K-means clustering algorithm introduced above to cluster redundant/repeated tweets into the same clsuter. You are expected to do the K-means implementation by yourself, so please do not use any external library that has K-means implementation in your code.
Note that while the K-means algorithm is proved to converge, the algorithm is sensitive to the k initial selected cluster centroids (i.e., seeds) and the clustering result is not necessarily optimal on a random selection of seeds. In this assignment, we provide you with a list of K initial centroids that has been tested to generate good results.
Inputs to your K-means Algorithm:

(1) The number of clusters K=25.

(2) A real world dataset sampled from Twitter during the Boston Marathon Bombing event in April 2013 that contains 251 tweets. Tweet Dataset Download .

(3) The list of initial centroids is here: Initial Seeds . Note that each element in this list is the tweet ID (i.e., the id field in JSON format) of the tweet in the dataset.

What to Turn In :
(1) A result file that contains the clustering results. Each line represents a cluster. It is in the form of cluster_id: a list of tweet IDs that belongs to this cluster 
(2) The source code to finish this task.
