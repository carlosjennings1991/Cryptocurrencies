# Cryptocurrencies

For this analysis, we review all the tradable currencies, classify them into certain groups and determine which ones are worth investing in. 
In order to do so, we practice the following. 

- [x] Data Scaling 
- [x] Principal Component Analysis
- [x] KMeans to determine clusters

All of which were performed using Jupyter Notebook in conjunctions with the Pandas and ScikitLearn libraries. 

[Source Data Here](https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/crypto_data.csv)
<br>
[Code File Here](https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/crypto_clustering.ipynb)

---

## Step 1: Preprocess our Data. 

After reading in our csv file, we have to make sure our data is in a condition ready for processing. So before we do anything else we have to do the following. 

- [x] Remove NaNs
- [x] Remove defunct cryptocurrencies
- [x] Remove cryptos without any supply

## Step 2: Standardize our Data.
We use the StandardScaler to our Alrgorithm and ProofType features. Standardizing our data centers the mean at zero and the standard deviation at 1. This is done to not distort our results later, like when we need to plot our data. 

<img src="https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/StandardizeData.png">

___

## Step 3: Use PCA (Principal Component Analysis) on our Scaled Data
This reduces the number of features of our data down to a predetermined number (3 for our purposes). The remaning columns contain the majority of the variation within the data. Those remaining columns are initially an array which we turn into a dataframe which will be useful for future data transformations. 

<img src="https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/PCA_columns.png">

___

## Step 4: Use KMeans to determine clusters. 
We use the dataframe we created in the previous step, pcs_df, and create a graph which plots the number of clusters (K) and inertia, which can be understood as variation within the data. This graph is known as an 'Elbow Curve'. The number of clusters we select for future data transformations is the poin on the curve where the line becomes more horizontal, which in our case is 4. 

<img src="https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/KMeans_ElbowCurve.png">

___

## Step 5: Determine which cluster each coin belongs to. 
We determine each cluster by creating a model which produces 4 possible outcomes and apply that model to our data. Our classes will be named 0, 1, 2, and 3. As we can see from the screenshot below, most coins belong to either the 0 or 1 class, which very few belonging to classes 2 or 3. 

<img src="https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/DetermineCluster.png">

___

## Step 6: Merge the dataframes
Earlier on we had split our dataframe for the sake of scaling our data. Those resulting dataframes were crypto_df and pcs_df, Now we want to merge them back together. 

<img src="https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/MergeDataframes.png">

___

## Step 7: Create 3D Visualizatio of our 4 Clusters
We do this by using the px method within the plotly package which we imported at the beginning of our code file. As we can see, almost all coins belong to either the 0 or 1 class, with only four coins belonging to Class 3 and only one coin belonging to Class 2.

<img src="https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/3DVisualizations_of_Clusters.png">
