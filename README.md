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
We use the StandardScaler to our Alrgorithm and ProofType features. Standardizing our data centers the mean at zero and the standard deviation at 1. 

<img src="https://github.com/carlosjennings1991/Cryptocurrencies/blob/main/StandardizeData.png">
