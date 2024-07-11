# CryptoClustering

**Module 19 Challenge**

This module leverages Python and unsupervised learning to analyze if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Data Preparation

- The data from `crypto_market_data.csv` was normalized using the `StandardScaler()` module from scikit-learn.
- A DataFrame was created with the scaled data, setting the "coin_id" from the original DataFrame as the index.

## Determining the Best Value for k Using the Original Scaled DataFrame

To find the best value for k, the elbow method was used:

1. Created a list with k values from 1 to 11.
2. Created an empty list to store inertia values.
3. Used a for loop to compute the inertia for each k value.
4. Created a dictionary with the data to plot the elbow curve.
5. Plotted a line chart with all the inertia values to visually identify the optimal k value.
6. The best value for k was found to be 4.

## Clustering Cryptocurrencies with K-means Using the Original Scaled Data

Cryptocurrencies were clustered using the following process:

1. Initialized the K-means model with k=4.
2. Fitted the K-means model using the original scaled DataFrame.
3. Predicted the clusters to group the cryptocurrencies.
4. Created a copy of the original data and added a new column with the predicted clusters.
5. Created a scatter plot using hvPlot:
   - x-axis: "price_change_percentage_24h"
   - y-axis: "price_change_percentage_7d"
   - Colored graph points with the labels found using K-means.
   - Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

## Optimizing the Clusters with Principal Component Analysis

1. Transformed the original scaled DataFrame using PCA to reduce features to three principal components.
2. Determined the explained variance to see how much data accuracy was retained.
3. The total explained variance of the three principal components was 89.5%.
4. Created a new DataFrame with the PCA data and the "coin_id" set as the index.

## Determining the Best Value for k Using the PCA Data

1. Used the elbow method on the PCA data to determine the best value for k.
2. The best value for k was found to be 4, similar to the initial k value on the original scaled data.

## Clustering Cryptocurrencies with K-means Using the PCA Data

1. Initialized the K-means model with k=4.
2. Fitted the K-means model using the PCA-transformed DataFrame.
3. Predicted the clusters to group the cryptocurrencies.
4. Created a scatter plot using hvPlot:
   - x-axis: "PCA1"
   - y-axis: "PCA2"
   - Colored graph points with the labels found using K-means.
   - Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

![elbow plots](https://github.com/Andreanimako/CryptoClustering/assets/155989509/1c4cbc3e-9069-413c-9a35-8e13721b1d25)

![scatter plots](https://github.com/Andreanimako/CryptoClustering/assets/155989509/208cf0e1-1f6d-40f4-b249-0b41e75fb351)












