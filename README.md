# CryptoClustering Challenge

## Introduction
The CryptoClustering Challenge involves analyzing the price trends of various cryptocurrencies using Python and unsupervised learning techniques. The objective is to determine whether cryptocurrencies are influenced by 24-hour or 7-day price changes. The challenge requires utilizing data preprocessing, clustering, and dimensionality reduction techniques to group similar cryptocurrencies based on their price behavior.

## Purpose
The main goal of this challenge is to apply unsupervised machine learning methods, specifically **K-means clustering** and **Principal Component Analysis (PCA)**, to categorize cryptocurrencies. By determining clusters of cryptocurrencies, the analysis aims to identify patterns and trends within the market, potentially uncovering groupings of coins based on price movement patterns over short and medium terms.

## Steps Involved

### 1. Prepare the Data
The first step involves loading the cryptocurrency data from a CSV file and preparing it for further analysis. The data must be normalized to ensure that all variables are on the same scale. This is done using the `StandardScaler()` module from the **scikit-learn** library.

- Normalize the data using `StandardScaler`.
- Create a new DataFrame with the scaled data.
- Set the "coin_id" column from the original DataFrame as the index of the new scaled DataFrame.

### 2. Find the Best Value for k Using the Elbow Method
To determine the optimal number of clusters, the elbow method is used. The elbow method involves plotting the inertia (a measure of how tightly grouped the clusters are) for different values of `k` and identifying the point where the inertia decreases most sharply.

- Generate a list of `k` values ranging from 1 to 11.
- Create an empty list to store the inertia values for each `k`.
- Use a for loop to compute the inertia for each `k` value.
- Plot the inertia values on a line chart to visualize the "elbow" point.
- Identify the optimal `k` value where the inertia shows the most significant change.

### 3. Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Once the best `k` value is identified, the **K-means clustering algorithm** is applied to group the cryptocurrencies into clusters.

- Initialize the K-means model with the best `k`.
- Fit the K-means model to the scaled data.
- Predict the clusters for each cryptocurrency.
- Add the predicted clusters as a new column in the original DataFrame.
- Create a scatter plot to visualize the clusters, with 24-hour price changes on the x-axis and 7-day price changes on the y-axis. The points on the scatter plot are colored based on their predicted cluster labels.

### 4. Optimize Clusters with Principal Component Analysis (PCA)
To further optimize the clustering process, **Principal Component Analysis (PCA)** is performed to reduce the dimensionality of the data. By reducing the data to three principal components, the explained variance of the principal components is analyzed to determine how much information is retained.

- Perform PCA on the scaled data and reduce the features to three principal components.
- Calculate the explained variance of the three components and determine the total explained variance.
- Create a new DataFrame with the PCA-transformed data, setting the "coin_id" column as the index.

### 5. Find the Best Value for k Using the PCA Data
The elbow method is applied once again, this time using the PCA-transformed data, to find the optimal number of clusters.

- Generate a list of `k` values from 1 to 11.
- Create an empty list to store the inertia values for each `k`.
- Use a for loop to compute the inertia for each `k` value.
- Plot the inertia values on a line chart to identify the optimal `k` value for the PCA data.
- Compare the best `k` value for the PCA data with the one found using the original scaled data to determine if they differ.

### 6. Cluster Cryptocurrencies with K-means Using the PCA Data
Using the optimal `k` value found from the PCA data, the K-means clustering algorithm is applied again.

- Initialize the K-means model with the best `k` value for the PCA data.
- Fit the K-means model to the PCA-transformed data.
- Predict the clusters for the cryptocurrencies based on the PCA data.
- Add the predicted clusters as a new column in the DataFrame with the PCA data.
- Create a scatter plot with the first two principal components on the axes and color the points by cluster labels.

## Summary
The CryptoClustering challenge leverages unsupervised learning techniques to analyze cryptocurrency data and categorize coins based on their price movements. By using clustering algorithms like K-means and dimensionality reduction through PCA, the analysis can provide insights into the behavior of various cryptocurrencies, helping identify patterns or groupings that may be influenced by recent price changes.
