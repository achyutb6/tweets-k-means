# Tweets Clustering using k-means

Twitter provides a service for posting short messages. In practice, many of the tweets are very
similar to each other and can be clustered together. By clustering similar tweets together, we can
generate a more concise and organized representation of the raw tweets, which will be very
useful for many Twitter-based applications (e.g., truth discovery, trend analysis, search ranking,
etc.)

In this assignment, you will learn how to cluster tweets by utilizing Jaccard Distance metric and

K-means clustering algorithm.
Objectives:
- Compute the similarity between tweets using the Jaccard Distance metric.
- Cluster tweets using the K-means clustering algorithm.

Introduction to Jaccard Distance:
The Jaccard distance, which measures dissimilarity between two sample sets (A and B). It is defined as the difference of the sizes of the union and the intersection of two sets divided by the size of the union of the sets.
For example, consider the following tweets:
Tweet A: the long march
Tweet B: ides of march
> |A Ç B | = 1 and |A U B | = 5, therefore the distance is 1 – (1/5)
In this assignment, a tweet can be considered as an unordered set of words such as {a,b,c}. By
"unordered", we mean that {a,b,c}={b,a,c}={a,c,b}=...
A Jaccard Distance Dist(A, B) between tweet A and B has the following properties:
- It is small if tweet A and B are similar.
- It is large if they are not similar.
- It is 0 if they are the same.
- It is 1 if they are completely different (i.e., no overlapping words).

Here is the reference for more details about Jaccard Distance:
http://en.wikipedia.org/wiki/Jaccard_index
Hint: Note that the tweets do not have the numerical coordinates in Euclidean space, you might want to think of a sensible way to compute the "centroid" of a tweet cluster. This could be the tweet having minimum distance to all of the other tweets in a cluster.

Exercise:
Implement the tweet clustering function using the Jaccard Distance metric and K-means clustering algorithm to cluster redundant/repeated tweets into the same cluster. You are free to
use any language or package, but it should be clearly mentioned in your report.
Note that while the K-means algorithm is proved to converge, the algorithm is sensitive to the k
initial selected cluster centroids (i.e., seeds) and the clustering result is not necessarily optimal on
a random selection of seeds. In this assignment, we provide you with a list of K initial centroids
that have been tested to generate good results.
Inputs to your K-means Algorithm:
(1) The number of clusters K (default to K=25).
(2) A real world dataset sampled from Twitter during the Boston Marathon Bombing event in
April 2013 that contains 251 tweets. The tweet dataset is in JSON format and can be downloaded
from http://www.utdallas.edu/~axn112530/cs6375/unsupervised/Tweets.json
(3) The list of initial centroids can be downloaded from: http://www.utdallas.edu/~axn112530/cs6375/unsupervised/InitialSeeds.txt
Note that each element in this list is the tweet ID (i.e., the id field in JSON format) of the tweet in the dataset.

How to run your code:
The TA should be able to run your code as follows:
tweets-k-means <numberOfClusters> <initialSeedsFile> <TweetsDataFile> <outputFile>
- <numberOfClusters> is the number of Clusters and
- <initialSeedsFile> is a text file containing value of the initial seed data.
- <TweetsDataFile> is the data file containing Tweets in JSON format
- <outputFile> is the output file explained below.

The default value for <numberOfClusters> should be 25 and for the <initialSeeds> to be the file provided to you containing number of seeds.

Output:
Your code should also output to a file called tweets-k-means-output.txt. It should contain
following:
<cluster-id> <List of tweet ids separated by comma> For example,
1 323906397735641088, 900906397735641088, ..
It should also contain the SSE value, which is defined below.
Validation:
The usual method of evaluating the goodness of clustering will be used. It is the Sum of Squared
Error (SSE) function, defined as:
where mi is the centroid of the ith cluster.
You should write a method/function to compute the SSE of clustering i.e. it should be separate from main method. This value should be written in the output file.
.

What to Turn In for :
(1) A result file that contains the clustering results. Each line represents a cluster. It is in the form of cluster_id: a list of tweet IDs that belongs to this cluster. Also include the overall SSE value.
(2) The source code in any of the following languages - Java, Python, C#, Ruby. Be sure to
include a README file indicating how to build and compile your code.
(3) A report file that contains details on how to compile your code, and any other relevant details.
* Idea and data courtesy of Dong Wang, University of Notre Dame *
