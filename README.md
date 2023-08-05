# CryptoClustering
### Description
>In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

### Info / Credits

- Project by 
    * `twilightbarkles` 

- `REPO:` https://github.com/twilightbarkles/CryptoClustering

## Introduction

This project consists of one technical product, including the following deliverables:

- Deliverable 1: Jupyter Notebook setup

- Deliverable 2: Exploratory Analysis

## Part 1-1: Jupyter Notebook setup

- Loaded the *crypto_market_data.csv* into a DataFrame
- View the summary statistics and plotted the data to preview the data

## Part 1-2: Prepare the data

- Used the *StandardScaler()* module from **scikit-learn** to normalize the data from the CSV file
- Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index
## Part 2-1: Find the Best Value for k Using the Original Scaled DataFrame

- Used the elbow method to find the best value for *k* using the following steps:
    - Created a list with the number of *k* values from 1 to 11
    - Created an empty list to store the *inertia* values
    - Created a *for* loop to compute the inertia with each possible value of *k*
    - Created a dictionary with the data to plot the elbow curve
    - Ploted a line chart with all the inertia values computed with the different values of *k* to visually identify the optimal value for *k*
    - Answered the following question: What is the best value for *k*?

## Part 2-2: Cluster Cryptocurrencies with K-means Using the Original Scaled Data

- Used the following steps to cluster the cryptocurrencies for the best value for *k* on the original scaled data:
    - Initialized the K-means model with the best value for *k*
    - Fitted the K-means model using the original scaled DataFrame
    - Predicted the clusters to group the cryptocurrencies using the original scaled DataFrame
    - Created a scatter plot using hvPlot as follows:
        - Set the x-axis as "PC1" and the y-axis as "PC2"
        - Color the graph points with the labels found using K-means
        - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point

## Part 2-3: Optimize Clusters with Principal Component Analysis

- Using the original scaled DataFrame, performed a PCA and reduced the features to three principal components
- Retrieved the explained variance to determine how much information can be attributed to each principal component, and then answered the following question:
    - What is the total explained variance of the three principal components?
- Created a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame

## Part 2-4: Find the Best Value for k Using the PCA Data

- Used the elbow method on the PCA data to find the best value for *k* using the following steps:

    - Created a list with the number of *k*-values from 1 to 11
    - Created an empty list to store the inertia values
    - Created a for loop to compute the inertia with each possible value of *k*
    - Created a dictionary with the data to plot the Elbow curve
    - Plotted a line chart with all the inertia values computed with the different values of *k* to visually identify the optimal value for *k*
    - Answered the following questions:
        - What is the best value for *k* when using the PCA data?
        - Does it differ from the best *k* value found using the original data?

## Part 2-5: Cluster Cryptocurrencies with K-means Using the PCA Data

- Used the following steps to cluster the cryptocurrencies for the best value for *k* on the PCA data:
    - Initialized the K-means model with the best value for *k*
    - Fitted the K-means model using the PCA data
    - Predicted the clusters to group the cryptocurrencies using the PCA data
    - Created a scatter plot using hvPlot as follows:
        - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d"
        - Color the graph points with the labels found using K-means
        - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point
    - Answer the following question:
    - What is the impact of using fewer features to cluster the data using K-Means?