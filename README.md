# Capstone-Estimate-the-unit-sales-of-Walmart-retail-goods---Kaggle

The M5 dataset, generously made available by Walmart, involves the unit sales of various.  <br />
products sold in the USA, organized in the form of grouped time series. More specifically,  <br />
the dataset involves the unit sales of 3,049 products,classified into 3 product  <br />
categories (Hobbies, Foods, and Household) and  <br />
7 product departments, in which the above-mentioned categories are disaggregated.  <br />
The products are sold across ten stores, located in three States (CA, TX, and WI).  <br />
In this respect, the bottom level of the hierarchy, i.e., product-store unit sales  <br />
can be mapped across either product categories or geographical regions.  <br />

Data was imported and the following analysis were done:  <br />
1)Plotting aggregate Sales data for all stores:  <br />
It was noticed that CA was the highest-selling state and CA_3 was the highest-selling store.  <br />
WI was the lowest-selling state for the data provided.  <br />
2) Due to a large amount of data CA_3 was the store for Item_id level forecasting for faster computation.  <br />
CA_3 was selected as it was the highest-selling store.  <br />
3) Box plot showing median selling price per price category by year for CA_3 store  <br />
4) Pie chart showing that Food (60%) contributes the highest revenue followed by household (30%) and hobbies (10%)  <br />
5) Identifying A, B, C items i.e. items generating top sales  <br />
A total of 3049 items were there in the dataset and ABC classification of inventory was done  <br />
 using the fmethodology,following was found:  <br />
A-	item_id that contributes> 80% of Total revenue were around 1130 items  <br />
B-	item_id that contributes the next 15% of Total revenue were around 996 items  <br />
C-	item_id that contributes the remaining 5% of Total revenue were around 923 items  <br />

6) Data frame for Summarizing data at store level - Daily time frame was created for further use  <br />
7) Summary statistics of sales by various stores and their respective totals for getting an estimate of importance by various stores <br />
8) Plotting for sales and holidays for the 3 major states to see how peaks and valleys correspond to various holidays <br />
This showed that the yearly daily-- low was during Christmas while the peak was around father’s day  <br />

9)Data trend and seasonality plotting. This was done to check for daily, weekly, and yearly seasonality  <br />
Following is the summary:
Here is a summary: 
a) Daily
Daily PACF – lags of 7,14,21,28 were showing significant <br />
Daily ACF – lags of 7,2,3 were showing significant <br />
Pdq from pmdarima is SARIMAX(5, 1, 0)x(2, 0, 0, 7) <br />
Stationarity test :Daily data was stationary per ad fuller test <br />

b)Weekly data <br />
PACF – lags of 10,6 were showing as significant <br />
ACF- lags of 6,10,4 were showing as significant <br />
Stationarity test :Weekly data was stationary per ad fuller test <br />
Pdq from pmdarima is SARIMAX(3, 1, 2)x(1, 0, [], 52) <br />
c) Monthly data<br />
PACF – lags of 8,12,14 were showing as significant <br />
ACF- lags of 12 were showing as significant <br />
Stationarity test :Weekly data was stationary per ad fuller test <br />
Pdq from pmdarima is SARIMAX(0, 1, 1)x(0, 1, [], 12) <br />

10) Plotting of 2015 holidays for just CA_3  <br />
11) Preparing Data frame for the item-level forecast  <br />
12) Autocorrelation function (ACF) and partial autocorrelation function (PACF) Plots.  <br />
These plots were also done at daily, weekly and monthly levels. Stationarity was also checked   <br />
and Auto Arima was used to check for p, d, q  <br />
13) Monthly and quarterly data were plotted using monthly and quarterly plot  <br />
Monthly plot:  clearly showed June and August as the peak months.  <br />
Quarterly plot: showed Q3 as the peak quarter.  <br />

14) Hierarchical forecasting using Auto Arima- this was done at daily level and did not take SKU level information into account:  <br />
This was done using both top-down and bottom-up methodology.  <br />
15) Machine learning model (ML) was used to generate Store_Item_id level forecast. <br />
Only 10 item_ids and one store was done by me due to computational limitations of my laptop. But the logic can be scaled.<br />
Feature creation for time series forecasting using ML  <br />
For ML forecasting following Features were created:   <br />
a)	Date time and cyclical features  <br />
b)	Lag features  <br />
c)	Rolling window features  <br />
d)	Difference feature  <br />
e)	Expanding feature  <br />

16) Feature importance using  lasso  <br />
17) ML forecasting for time series:  <br />
a) XG boost for one step forecast  <br />
b) lasso for 28-day direct forecast. This used multi target   <br />


