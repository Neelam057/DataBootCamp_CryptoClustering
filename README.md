# Cryptocurrency Clustering with K-Means and PCA

## Overview

In this challenge, Python and unsupervised learning techniques are used to analyze cryptocurrency data. Specifically,**K-Means clustering** is applied to group cryptocurrencies based on their features, such as price changes over different time periods. We also optimized our clusters using **Principal Component Analysis (PCA)** to reduce the dimensionality of the data and improve clustering performance.

The goal of this project is to determine whether cryptocurrencies are more strongly affected by **24-hour price changes** or **7-day price changes** by visualizing their clusters.

---

## Table of Contents

- [Requirements](#requirements)
- [Steps](#steps)
  - [Step 1: Find the Best Value for k](#step-1-find-the-best-value-for-k)
  - [Step 2: Cluster the Cryptocurrencies with K-Means](#step-2-cluster-the-cryptocurrencies-with-k-means)
  - [Step 3: Optimize Clusters with PCA](#step-3-optimize-clusters-with-pca)
  - [Step 4: Find the Best Value for k Using PCA Data](#step-4-find-the-best-value-for-k-using-pca-data)
  - [Step 5: Cluster the Cryptocurrencies with K-Means Using PCA](#step-5-cluster-the-cryptocurrencies-with-k-means-using-pca)
  - [Step 6: Visualize and Compare the Results](#step-6-visualize-and-compare-the-results)

---

## Requirements

- `pandas` (for data manipulation)
- `matplotlib` (for plotting)
- `scikit-learn` (for clustering and PCA)
- `hvplot` (for interactive visualizations)
- `numpy` (for numerical operations)

---

## Steps

### Step 1: Find the Best Value for k
- **Objective:** Find the optimal number of clusters (`k`) for the cryptocurrencies.
- **Method:** Use the **Elbow Method** to determine the best `k` by plotting inertia values over a range of `k` values (1 to 11). The "elbow" in the plot indicates the optimal number of clusters.

### Step 2: Cluster the Cryptocurrencies with K-Means
- **Objective:** Perform K-Means clustering with the optimal `k` found in Step 1.
- **Steps:**
  - Initialize the K-Means model with the best `k`.
  - Fit the model to the scaled cryptocurrency data.
  - Predict the clusters and add them to the DataFrame.
  - Create a scatter plot showing `price_change_percentage_24h` vs. `price_change_percentage_7d`, with color-coded clusters.

### Step 3: Optimize Clusters with PCA
- **Objective:** Reduce the dimensionality of the data to 3 components using **Principal Component Analysis (PCA)** and optimize the clusters.
- **Steps:**
  - Create a PCA model to reduce the features to 3 components.
  - Calculate and display the explained variance of each component.
  - Transform the data into PCA space and create a new DataFrame.

### Step 4: Find the Best Value for k Using PCA Data
- **Objective:** Use the PCA-transformed data to find the best `k` for clustering.
- **Method:** Apply the Elbow Method to the PCA data to identify the optimal number of clusters.

### Step 5: Cluster the Cryptocurrencies with K-Means Using PCA
- **Objective:** Perform K-Means clustering on the PCA-transformed data.
- **Steps:**
  - Initialize the K-Means model with the best `k` for PCA.
  - Fit the K-Means model to the PCA data and predict the clusters.
  - Create a scatter plot using the first two principal components (`PC1` and `PC2`), color-coded by cluster labels.

### Step 6: Visualize and Compare the Results
- **Objective:** Compare the results of the clustering from the original scaled data with those from the PCA-transformed data.
- **Steps:**
  - Create composite plots to:
    - Compare the elbow curves for the original and PCA data.
    - Compare the clustering results (scatter plots) for the original and PCA data.
  - Visually analyze how reducing the number of features with PCA affects the clustering.

---
