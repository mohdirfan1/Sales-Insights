# Sales-Insights
Sales Insights Data Analysis Project
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

# Data Cleaning and ETL (Extract, Transform, and Load)
**I did simple data analysis using SQL.**   
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



