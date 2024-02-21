# CryptoClustering
Matthew Idle
University of Minnesota Data Analytics and Visualization Bootcamp
September 2023 - March 2024

This challenge was easier than the Tableau Challenge that oddly enough put me through the ringer. The starter code was prety well commented, so there really wasn't much to add to it without muddying the waters. I did set the KMeans random_state parameter to random_state=7, to make the centroid initialization more deterministic and troubleshooting easier. The book cited below by Aurélien Géron helped explain the prinicples in more detail. There were five or so questions along the way, and the answers are provided in the jupyter notebook.

References:
Géron, Aurélien. Hands-on Machine Learning with Scikit-Learn, Keras and Tensorflow: Concepts, Tools, and Techniques to Build Intelligent Systems. O’Reilly Media, 2019. 
 “Scikit-Learn.” Scikit, scikit-learn.org/stable/index.html. Accessed 21 Feb. 2024. 
 
Also used chat gpt for general questions







Provided Challenge Description:
In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

Before You Begin
Create a new repository for this project called CryptoClustering. Do not add this homework to an existing repository.

Clone the new repository to your computer.

Push your changes to GitHub.

Files
Download the following files to help you get started:

Module 19 Challenge filesLinks to an external site.

Instructions
Rename the Crypto_Clustering_starter_code.ipynb file as Crypto_Clustering.ipynb.

Load the crypto_market_data.csv into a DataFrame.

Get the summary statistics and plot the data to see what the data looks like before proceeding.

Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the scaled DataFrame should appear as follows:

The first five rows of the scaled DataFrame

Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best value for k using the following steps:

Create a list with the number of k values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
Answer the following question in your notebook: What is the best value for k?
Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the original scaled DataFrame.
Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
Create a copy of the original data and add a new column with the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "PC1" and the y-axis as "PC2".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Optimize Clusters with Principal Component Analysis
Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

What is the total explained variance of the three principal components?
Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the PCA DataFrame should appear as follows:

The first five rows of the PCA DataFrame

Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:

Create a list with the number of k-values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the Elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
Answer the following question in your notebook:
What is the best value for k when using the PCA data?
Does it differ from the best k value found using the original data?
Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the PCA data.
Predict the clusters to group the cryptocurrencies using the PCA data.
Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Answer the following question:
What is the impact of using fewer features to cluster the data using K-Means?
REWIND
Recall that you learned how to create composite plots in a previous module. If you need a refresher on how to create these plots, review that module. You can also check Composing PlotsLinks to an external site. in the hvPlot documentation.