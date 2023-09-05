# Cryptocurrency Market Data Analysis

This repository contains Python code for analyzing cryptocurrency market data and performing K-Means clustering. The code aims to group cryptocurrencies based on their price change percentages over various time intervals.

## Code Overview

1. **Prepare the Data** : The code loads cryptocurrency market data from a CSV file and provides a glimpse of the data, including summary statistics. Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame. Data is standardized using `StandardScaler` and organized into a DataFrame for analysis.


2. **Find the Best Value for k Using the Original Scaled DataFrame**
- Created a list with the number of k values from 1 to 11.
- Created an empty list to store the inertia values.
- Created a for loop to compute the inertia with each possible value of k.
- Created a dictionary with the data to plot the elbow curve.
- Ploted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
   
3. **Cluster Cryptocurrencies with K-means Using the Original Scaled Data**
- Initialized the K-means model with the best value for k.
- Fit the K-means model using the original scaled DataFrame.
- Predicted the clusters to group the cryptocurrencies using the original scaled DataFrame.
- Created a copy of the original data and add a new column with the predicted clusters.
- Created a scatter plot using hvPlot as follows:
- Set the x-axis as "PC1" and the y-axis as "PC2".
- Colored the graph points with the labels found using K-means.
= Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.


4. **Optimize Clusters with Principal Component Analysis**
- Using the original scaled DataFrame, performed a PCA and reduce the features to three principal components.
- Retrieved the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
- Created a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

5. **Find the Best Value for k Using the PCA Data**
- Created a list with the number of k-values from 1 to 11.
- Created an empty list to store the inertia values.
- Created a for loop to compute the inertia with each possible value of k.
- Created a dictionary with the data to plot the Elbow curve.
- Ploted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

6. **Cluster Cryptocurrencies with K-means Using the PCA Data**
- Initialized the K-means model with the best value for k.
- Fit the K-means model using the PCA data.
- Predicted the clusters to group the cryptocurrencies using the PCA data.
- Created a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
- Created a scatter plot using hvPlot as follows:
- Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
- Colored the graph points with the labels found using K-means.
- Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

## Conclusion

This code demonstrates how to perform K-Means clustering on cryptocurrency market data, exploring different features and dimensionality reduction techniques. It helps in understanding the optimal number of clusters and provides insights into cryptocurrency market segmentation.

