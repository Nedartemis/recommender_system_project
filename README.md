# Movie Pairing Recommender System

## Choice of model

First, we choose to implement a kmeans recommender for its simplicity and its computational efficiency.
As seen in course, we would use only ratings for the recommendation.

Our plan was to develop another model (a NN encoder) which would use other features to compare performances.
Unfortunately, we did not complete our plan, and our notebook only presents the k-means.

## Framework

We chose sklearn for its simplicity.

## Features selection

As said earlier, we only selected ratings.

## Our recommendation algorithm

First, we combine our couples of users as one 'simulated' user (for exemple, we just combined their ratings).
We compute their cluster.
We compute the ratings of the cluster, which is, for each movie, the average of the ratings of every users in this cluster.
We have now a list of movie associated with a rating.

We can suggest a movie by taking the top ranked movie of the computed list. 

We could also compute the cluster of each user of the couple, get the ratings of their cluster and applying a 'mean' at this moment.
We tried but it did not improve the performances.

## Performances

We chose mean square error and r2 score as metrics.
They permit to evaluate the differences beetween the predicted ratings and the true ones.
Note that the ratings used for testing are not given to our algorithm.

We prefer r2 score because its results are more easily interpretable.
In fact, if the r2 score is far from 0, we know that our recommender system is better that a recommender system that would suggest movie that are in general good movie despite the preferences of the user

Unfortunately, our performances are low, almost the same as a dummy recommender.
On the other hand, we now know that the techniques chosen are not enough to build a good recommender system.