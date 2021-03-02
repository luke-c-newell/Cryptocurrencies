# Cryptocurrencies
In this repository, I have created a report for my client at a prominent investment bank, who is looking to gain an understanding of the cryptocurrency investment market. Their aim is to offer a new cryptocurrency investment portfolio for their customers, based on segments of the cryptocurrency market.

My report highlights which cryptocurrencies are currently being traded and determines how they could be grouped to create a classification system for this new investment portfolio. Using a Jupyter Notebook, the pandas, hvplot, plotly and sklearn python libraries, I have used unsupervised machine learning to cluster a dataset of over 500 cryptocurrencies into 4 distinct groups, based on their 3 principal components.

### Preprocessing the Data
I completed initial data pre-processing to remove any cryptocurrencies that are not suitable for being added to the investment portfolio, based on the following criteria:

- The cryptocurrency is currently trading
- The cryptocurrency has a working algorithm
- The cryptocurrency does not have any null values in the dataset
- The cryptocurrency has a non-zero number of coins already mined

After removing the cryptocurrencies that do not meet the above criteria, and any unnecessary columns, I created the below DataFrame to hold the clean dataset. There are 532 cryptocurrencies that currently fit my clients investment criteria.

#### Initial cryptocurrency DataFrame
![crypto_df](https://github.com/luke-c-newell/Cryptocurrencies/blob/main/images/crypto_df.png "crypto_df.png")
### Principal Component Analysis (PCA) and clustering cryptocurrencies Using K-Means
I performed principal component analysis to determine the 3 components that have the greatest impact for grouping the data into clusters. The 3 components can be found in the new DataFrame seen below. To determine the optimal number of clusters for the cryptocurrencies, I created an elbow curve chart to visualize the different values for K, used in the K-means clustering algorithm. The chart below shows that the optimal number of clusters is 4, as the 'elbow' is found at k=4. The 4 clusters are described in the 'Class' column, described as classes 0, 1, 2 and 3.

![elbow_plot](https://github.com/luke-c-newell/Cryptocurrencies/blob/main/images/elbow_plot.png "elbow_plot.png")
#### DataFrame including predicted clusters and cryptocurrency classes
![clustered_df](https://github.com/luke-c-newell/Cryptocurrencies/blob/main/images/clustered_df.png "clustered_df.png")
### Visualizing Cryptocurrencies Results
#### 3D-Scatter plot with Clusters
This chart highlights the different clusters, showing the groups created by the 3 principal components. Each class is represented by a different color and marker, enabling quick identification on the chart.

![3d_plot_label](https://github.com/luke-c-newell/Cryptocurrencies/blob/main/images/3d_plot_label.png "3d_plot_label.png")
#### Table with tradeable Cryptocurrencies
This table is a visualization of the entire cleaned dataset, created using the hvplot library.

![hvplot_table](https://github.com/luke-c-newell/Cryptocurrencies/blob/main/images/hvplot_table.png "hvplot_table.png")
#### 2D-Scatter plot showing Total Coins Mined against Total Coin Supply
This plot shows the different classes of cryptocurrencies, based on the number of coins mined and the number of coins available in the market. This chart was plotted using scaled data, which allows for a better visualization of the results. The correct values for the TotalCoinsMined and TotalCoinSupply columns can be found by viewing the full version of the table above.

![scatter_plot](https://github.com/luke-c-newell/Cryptocurrencies/blob/main/images/scatter_plot.png "scatter_plot.png")

