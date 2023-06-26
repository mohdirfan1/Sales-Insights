# Sales-Insights
Sales Insights Data Analysis Project
![Dashboard 1](https://github.com/mohdirfan1/Sales-Insights/assets/107385987/b8f33c58-e2cd-4e0c-9f37-2e2ae336a656)

## Problem Statement

XYZ-Hardware is a company that supplies computer hardware and peripherals to many clients. They have this client called Excel stores, and normal stores across India and they supply all these types of equipment to them now. XYZ-Hardware has a head office in Delhi, India and they have a lot of regional offices throughout India.

Now, the Sales Director for this company is facing a lot of challenges. The challenge is this the market is growing dynamically and then he's facing issues in terms of tracking the sales in this dynamically growing market and he's having issues with the insights of his business. So he has these Regional Managers for North India, South India, and Central India, whenever he wants to get insights into these three regions he would call these people and on the phone, these local regional managers will give him some insights that this was the sales last quarter and we are going to grow by this much in the next quarter.

The problem is the conversation that is happening they're all verbal and you know they try to paint a rosy picture, so things don't want to look bad. The Sales Director is extremely frustrated with this because he sees that overall the sales are declining but he's not getting a complete picture when he asked for numbers. These people give him a lot of Excel files and XYZ-hardware is a pretty big business they have so many clients that these Excel files that he gets are so many with so many rows in them. 

He wants to see the clear picture and wants to know in simplistic terms how our business is doing and what are the areas where we need to focus like regions where the sales numbers are declining maybe we can start some promotional offers or maybe we can engage with customers in a better way.

As humans cannot consume so many numbers, there is a saying, a picture is worth a thousand words. So he's more interested in a dashboard where he can check and look at what’s happening in real-time and then as a Sales director he can make data-driven decisions and these data-driven decisions will help him increase the sales for his company. So that's all I have for the problem statement, we'll be talking more about it next sections and the data discovery phase.

## Data Discovery
project planning using the AIMS grid and data discovery after the Sales Director at AtliQ hardware realizes the pains and the possible solution. 
### AIMS grid is a project management tool and it has four components:
**1. Purpose:**     
To unlock sales insights that are not visible before for the sales team for decision support and automate them to reduce manual time spent in data gathering.

**2. Stakeholders:**
* Sales Director
* Marketing Team
* Customer Service Team
* Data and Analytics Team

**3. End Result:**      
An automated dashboard providing quick and latest sales insights in order to support data-driven decision-making.

**4. Success Criteria:**      
Dashboard(s) uncovering the sales order insights with the latest data available
The sales team is able to take better decisions and prove 10% cost savings of total spend
Sales Anlysts stop data gathering manually in order to save 20% of their business time and reinvest it value added activity

# I did simple data analysis using SQL.   
1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`

# Data Cleaning and ETL (Extract, Transform, and Load)


We did simple data analysis using MySQL. Now we are going to use tableau to connect with the same MySQL database and we will pull this data and do data cleaning, it is also known as ETL (extract, transform, and load). We will do some transformation because some of the data is messy and we will need we need to convert it into a different format so that we can perform our data analysis. We will pull this data in tableau, we'll do our transformation or ETL and then we will build a data model this data model will be suitable for doing our analysis. Now, tableau is connected with MySQL pulling all the records from these tables into the tableau  environment. 

Now we’ll make our data model (shows a relationship between your different tables), by default it establishes some relationship if the column names are the same in different tables. If columns contain the same values but their names are different we’ve to drag and drop columns to make the relationship. In the data model, there are two basic types of schemas star and snowflake. In a star schema, there is a fact table and a dimension table in our case see the fact table is a transaction (the actual transaction actual activity) is fact table, it is basically events that are happening in your business and the dimension table is the table such as customer, product, market and so on and all these tables entity tables connect with your fact table in this manner and it kind of looks like a star that is why it is called a star schema. We have done our data modeling.
   

![Screenshot (99)](https://github.com/mohdirfan1/Sales-Insights/assets/107385987/5a788d8a-7311-4207-9cfb-2720d1a0ee52)


The first thing we want to filter out is New York and Paris from the Markets table because XYZ-hardware is running a business only in India right now and New York and Paris happen to be some value that exists in our database. By going on transform data 
The second one, in our sales transaction table the problem that we had in this table was there are two problems one is the sales amount is -1 and 0. We’ll filter out these two values.   
and have convert some USD transaction in INR 
# Data Visualization
https://public.tableau.com/app/profile/mohd.irfan3276/viz/salesinsight_16877938881700/Dashboard1

![Dashboard 1](https://github.com/mohdirfan1/Sales-Insights/assets/107385987/b8f33c58-e2cd-4e0c-9f37-2e2ae336a656)

## After doing all this different created visualization which are:
* Revenue by Markets
* Quantity by Markets
* Revenue by year 
* Top 5 Customers
* Top 5 Products









