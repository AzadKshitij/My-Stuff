![[Assets/WhatsApp Image 2022-09-28 at 22.52.30.jpg]]

Assignment 3

1. Dataset
- The size of the [dataset](https://www.kaggle.com/datasets/debashis74017/stock-market-data-nifty-50-stocks-1-min-data) is 10.2 GB.
- The dataset consist of Nifty 50 stocks data and two indices data, along with 55 technical indicators used by Market experts. This dataset contains historical daily prices for Nifty 100 stocks and indices currently trading on the Indian Stock Market.
- Data samples are of 5-minute intervals and the availability of data is from Jan 2015 to Feb 2022.

2. Analysis
	1. Pandas
		- Pandas was not able to handle 10 GB of data and gave "Out of memory" error.
		- I tried using multi processing but cant do the same with PySpark.

	2. Pyspark
		- PySpark easily able to handle 10 GB of data.
		- PySpark API is very similar to of Pandas.

* Queries
As pandas was not able to handle big data I used 600MB file to perform different queries to compare pandas and pyspark.

![[Assets/Pasted image 20221009225218.png]]

From the above data we can see that pandas performed better compared to PySpark. But as pandas is not able to read large data I will prefer PySpark as it's dataframes can be converted to pandas dataframe and we can use same API as of Pandas for analysis.

![[Assets/Pasted image 20221010114116.png]]
```python
df_10500000.filter(df_10500000['volume'] > 10000).show(5)
```




