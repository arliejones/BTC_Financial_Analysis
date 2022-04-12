# BTC_Financial_Analysis

This program was built to analyze historical trade data for Bitcoin from the Bitstamp and Coinbase exhanges from 2018. The program prepares the datasets for analysis by cleaning up missing and erroneous data. Once prepared, the program will analyze the data through summary statistics and visualizations. For deeper analysis, the program will then compare the closing prices from each exchange from specific time periods to identify arbitrage opportunities. If arbitrage opportunities are found, the program will plot them to show potential cumulative profits.

----

## Technologies
This application is written in Jupyter Lab Notebook in the Python programming language. The program was run & debugged using the Terminal in MAC OS Monterey 12.2.1. The Python libraries used in this application are Pandas -specifically DataFrame-  and Matoplotlib. Official documentation shown below:

[Pandas](https://pandas.pydata.org/docs/index.html)

[pandas.DataFrame](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html)

[Matplotlib](https://matplotlib.org/stable/index.html)

----

## Installation Guide
This program uses the Pandas library. If the user is not already running an environment that includes Pandas, then they will need to intall the library. Installation guide shown below:

[Pandas Installation](https://pandas.pydata.org/docs/getting_started/install.html)

----

## Usage
For the program to run correctly, the user must make sure that all libraries are correctly imported in the beginning of the code. This looks like:

> import pandas as pd

> from pathlib import Path

> %matplotlib inline

The user must also make sure that their references to the Bitstamp (bitstamp.csv) and Coinbase (coinbase.csv) data reflect the correct location in their directory.

#### The program is comprised of three parts:

1. **Collecting the Data**

  Using the Pandas *read_csv* function and the *Path* module, the program imports the data from the bitstamp.csv and coinbase.csv files and creates a   DataFrame for each.

2. **Preparing the Data**

  This section of the program drops all missing values, removes dollar signs from the values, converts data types to float, and checks for duplicates and drops them. The program does this for both the Bitstamp and Coinbase DataFrames.

3. **Analyzing the Data**

  This section of the program goes into multiple layers of analysis. It starts narrowing down the data to be analyzed by selecting the column 'Closed'. This is so we can focus in on the closing prices of Bitcoin from both exchanges. The program will give us big-picture analysis by getting summary statistics and plotting the Close data over the entire length of the data set for both exchanges. Then, the program goes into a more narrow analysis by choosing 3 different dates to analyze from the 3 month data set. The user can analyze any dates they would like ranging from 2018-01-01 to 2018-03-31. As this code is written, the program analyzes data from Jan 11, Jan 28, and March 2. The program gives us summary statistics for these dates and plots this data to visualize the spread between both exchanges. This spread is called an arbitrage opportunity. The program will then take this data to calculate arbitrage profits. First, it will calculate the arbitrage spread from each date and then calculate the spread returns with only the positive spreads from the data. Then, the program will narrow down the trading opportunities further by determining the number of times the trades with positive returns exceed the 1% minimum threshold that are needed to cover the trading costs.
(*This is where the dates I chose will start to return no data. For Jan 11 and March 2, there are no profitable trades, so the rest of the code will not work for those variables. Jan 28 is the only data set that returned profitable trades, so the remaining written code focuses in on that specific date.*) The program will create summary statistics for the spread returns greater than 1%. Then, the program will calcualte the potential profit, in dollars, per trade and plot the results. Lastly, the program will calulate the potential arbitrage profits for the day, then calculate the cumulative sum of those profits and plot the data.

----

## Contributors

Arlie Jones

[E-mail](arliejones98@gmail.com)

[LinkedIn](https://www.linkedin.com/in/arlie-jones-020092159/)

----

## License

None
