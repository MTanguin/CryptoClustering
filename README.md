
#### "Predicting Price Change Impact of Cryptocurrenciesthrough Unsupervised Learning"



# Background

Cryptocurrencies have gained significant attention in the financial world, and understanding their market behavior is of utmost importance. In this project, we will leverage Python and unsupervised learning techniques, specifically K-means clustering and Principal Component Analysis (PCA), to predict whether cryptocurrencies are affected by 24-hour or 7-day price changes. By clustering cryptocurrencies based on their price change patterns, we can gain insights into their market dynamics and potentially identify similar groups within the cryptocurrency market.

# Methods

1. Data Preparation:
   - Utilize the StandardScaler module from scikit-learn to normalize the data from the provided CSV file.
   - Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

2. Finding the Best Value for k Using the Original Scaled DataFrame:
   - Apply the elbow method to determine the optimal value for k, which represents the number of clusters.
   - Create a list of k values and an empty list to store the inertia values (within-cluster sum of squares).
   - Iterate through each k value to compute the inertia and store it.
   - Plot a line chart to visualize the inertia values and identify the best value for k.

3. Clustering Cryptocurrencies with K-means Using the Original Scaled Data:
   - Initialize the K-means model with the optimal value for k.
   - Fit the K-means model using the original scaled DataFrame.
   - Predict the clusters for the cryptocurrencies based on the original scaled DataFrame.
   - Create a scatter plot using hvPlot to visualize the clusters, with the x-axis representing the 24-hour price change percentage and the y-axis representing the 7-day price change percentage.
   - Color the graph points according to the predicted clusters and add the "coin_id" column to the hover information for identification.

4. Optimizing Clusters with Principal Component Analysis:
   - Perform PCA on the original scaled DataFrame to reduce the feature space to three principal components.
   - Retrieve the explained variance to assess the information attributed to each principal component.
   - Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

5. Finding the Best Value for k Using the PCA Data:
   - Use the elbow method on the PCA data to determine the optimal value for k.
   - Create a list of k values and an empty list to store the inertia values.
   - Compute the inertia for each k value and store it.
   - Plot a line chart to visualize the inertia values and identify the best value for k.

6. Clustering Cryptocurrencies with K-means Using the PCA Data:
   - Initialize the K-means model with the optimal value for k based on PCA data.
   - Fit the K-means model using the PCA data.
   - Predict the clusters for the cryptocurrencies based on the PCA data.
   - Create a scatter plot using hvPlot to visualize the clusters, with the x-axis representing the 24-hour price change percentage and the y-axis representing the 7-day price change percentage.
   - Color the graph points according to the predicted clusters and add the "coin_id" column to the hover information for identification.


## RESULTS


![Alt text](Images/clustering_comparison.png)



![Alt text](Images/elbows_comparison.png)




## SUMMARY


Based on the information provided, the same dataset was used for both the K-means algorithm and the PCA and K-means algorithm combination. The K-means algorithm was applied to the dataset to partition it into K clusters based on similarity of the data points. Then, the PCA algorithm was applied to the dataset to reduce the dimensionality of the dataset, and the K-means algorithm was applied again to the reduced dataset to partition it into K clusters.


The Inertia, Dunn Index, Silhouette Score, and Calinski-Harabasz Index  metrics were used to evaluate the quality of clustering results (see Crypto_Clustering.ipynb,"Evaluate the quality of the clustering results").

The Silhouette Score measures the compactness and separation of the clusters, with a score ranging from -1 to 1. A score closer to 1 indicates better clustering performance. In this case, both algorithms achieved a Silhouette Score of 70% and 74%, respectively, which suggests good performance in clustering. However, the PCA and K-means combination solution had a slightly higher score, indicating better separation and compactness of the clusters.

The Inertia measures the within-cluster sum of squared distances from each point to its centroid. A lower value indicates better clustering performance. In this case, the PCA and K-means combination algorithm achieved a lower Inertia value of 93.77, compared to 123.19 the K-means algorithm alone. This suggests that the PCA and K-means algorithm combination was able to create more compact clusters.

The Calinski-Harabasz Index measures the ratio of between-cluster variance to within-cluster variance. A higher value indicates better clustering performance. In this case, the PCA and K-means algorithm combination achieved a higher CH Index score of 33.05, compared to 25.26 to the other one. This suggests that the PCA and K-means combination algorithm was able to create more separated clusters.

Overall, it appears that both algorithms performed well in clustering, but PCA and K-means algorithm combination had slightly better performance, with better separation and compactness of the clusters. The k value of 3 was used for both algorithms, and it seems to have resulted in well-separated and compact clusters.




Sources:

https://courses.bootcampspot.com/courses/2799/assignments/42910?module_item_id=803895

https://scikit-learn.org/stable/modules/clustering.html#clustering

https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html

https://scikit-learn.org/stable/modules/generated/sklearn.metrics.calinski_harabasz_score.html#sklearn.metrics.calinski_harabasz_score


