##### Title: Minneapolis Housing Price Prediction



##### Data Source:

https://www.kaggle.com/datasets/thuynyle/redfin-housing-market-data





##### Problem Statement:

In order for the homebuyer to have a better idea of housing costs, a model could be used to predict the cost, and then the home buyer could compare to the expected price given by the model.



##### Goal:

Build a Model that can be used to determine if a property is over/under valued







##### Data Wrangling/Cleanup:



This Jupyter Notebook is called: MN\_Housing\_DW.ipynb

###### 

###### Dataset summary:

&nbsp;	Two CV's were uploaded and combined into one dataframe to give a dataset consisting of 27 columns and 702 rows. Two of these rows didn't actually have data so those were removed right away. These were the only two rows that did not have a value for Price.



###### Data Cleanup:



&nbsp;	The general process for cleanup was the following steps. 



1. Remove Nan values in the price column
2. Remove unwanted features such as URL
3. Remove features with a single value such as State or Province (Always was MN)
4. Removed all vacant land values
5. Fill in remaining nan values in lot size with 0
6. Modify data types to match the values in each feature
7. Confirmation of data types and # of nan values



The remaining table is given below. 



&nbsp;#   Column              Non-Null Count  Dtype  

---  ------              --------------  -----  

&nbsp;0   PROPERTY TYPE       687 non-null    string 

&nbsp;1   ADDRESS             687 non-null    string 

&nbsp;2   CITY                687 non-null    string 

&nbsp;3   ZIP OR POSTAL CODE  687 non-null    string 

&nbsp;4   PRICE               687 non-null    float64

&nbsp;5   BEDS                687 non-null    float64

&nbsp;6   BATHS               687 non-null    float64

&nbsp;7   LOCATION            687 non-null    string 

&nbsp;8   SQUARE FEET         687 non-null    float64

&nbsp;9   LOT SIZE            687 non-null    float64

&nbsp;10  YEAR BUILT          687 non-null    int64  

&nbsp;11  DAYS ON MARKET      687 non-null    int64  

&nbsp;12  $/SQUARE FEET       687 non-null    float64

&nbsp;13  HOA/MONTH           687 non-null    float64

&nbsp;14  MLS#                687 non-null    string 

&nbsp;15  LATITUDE            687 non-null    float64

&nbsp;16  LONGITUDE           687 non-null    float64

dtypes: float64(9), int64(2), string(6)



The table was then exported as a CSV file called "MN\_cleaned.csv"







##### Data EDA:





This notebook is titled: MN\_Housing\_EDA.ipynb





The following Hypotheses were explored for better clarification of the data:



1\. Location has an affect on price

2\. As size increases for the housing unit, so does the price

3\. number of beds has an affect on price, likely a price increase

4\. number of bathrooms has an affect on price, likely an increase in price

5\. Different classes of property types will have different prices (vague I know, but hard to get specific with multiple property types)





First a general relatioinship between data and 



!\[feature\_heatmap\_EDA](feature\_heatmap\_EDA.png)



















