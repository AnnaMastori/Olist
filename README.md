# Olist
### Olist is project we worked on as part of the course Business Intelligence and Big Data Analysis, which is taught by Damianos Chatziadoniou at Athens University of Economics and Business. The main objective was to construct a data warehouse and perform data mining tasks for a publicly available dataset.

## Summary
In this project we created a data warehouse and did 2 data mining tasks on a sales dataset for Olist, which is a Brazilian E-commerce business. More specifically, for the data warehouse we implemented an ETL process, we modeled the data as a star schema and we created an OLAP server. Finally, we used analysis and data mining to extract insights from the data and visualised them with the help of Miscrosoft Power BI. For the data storage, ETL process, Olap server, analysis and visualization we used Microsoft tools and the data mining was done using Python.

## About the company 
The Olist store is an e-commerce business headquartered in Sao Paulo, Brazil. This firm acts as a single point of contact between various small businesses and the customers who wish to buy their products. 

## About the dataset
It is a public dataset and it has information of over 100k orders from 2016 to 2018 made by multiple marketplaces in Brazil. 
You can fing it in Kaggle. [Brazilian E-Commerce Public Dataset by Olist | Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

![Dataset schema](https://github.com/AnnaMastori/Olist/blob/main/Dataset%20schema.png "Dataset schema")

## Extract-Transform-Load Process
Firstly, we created some staging tables in the SQL server we used for storage. We created an ETL process which extracts the data from the csv files, transforms them (e.g. aggregation, filtering) and loads them in the Data Warehouse(sql tables). For the ETL process we used the SSIS extention of Visual Studio.

## Star Schema
We constructed the star schema that is shown below to model our data. Our star schema consists of 1 fact table and 6 dimensions. The dimensions are the following: customer dimension, product dimension, seller dimension, order status dimension, date dimension, order dimension and product  dimension. Our fact table has a row for each item purchased, approximately 100.000 rows. It contains the following measures :freight value of each item, price of each item, score for each order( it is the same for all items of an order). It is an essential task in order to analyse large datasets (eg aggregations)fast with the help of olap servers.

![Star schema](https://github.com/AnnaMastori/Olist/blob/main/Star%20schema.png "Dataset schema")

## OLAP server
We used the data from the data warehouse as they are modeled in the star schema in order to create a cube. Our multidimentional cube consists of 1 fact table and 6 dimensions. We created a hierarchy of the date attributes for the Date dimension. We also created 2 Calculated Members in the cube. We used the cube for our analysis of the dataset. The olap server was created with the SSAS extention of Visual Studio.

## Data Mining Tasks 
Given our dataset and the the business model of Olist we ran two DM models. We did a Customer Segmentation using clustering and the RFM(Recency-Frequency-Monetary) method. Also, we classified each seller as Silver, Gold, Platinum based on the number of products, customers and sales each had. To achieve that created a classsification model using the KNN classifier. For the data mining models we used Python (pandas, sklearn, matplotlib).

## Reports
As a last step, we created reports in PowerBI to showcase the results of our analysis and datamining tasks.
For example,	the following report has the sales of year 2018 by month, day of the week and product category. We observed that the revenue for the last quarter of the year is the lowest. 
![Revenue of 2018 report](https://github.com/AnnaMastori/Olist/blob/main/sales2018.png "Revenue of 2018 by day, month and product")


