# Data-Analysis-Challenge-For-LALAMOVE
This challenge is based around the skills to retrieve data and analyze it using technologies like SQL and Python in real world scenario at a firm.

https://www.lalamove.com/india/mumbai/en/home



There are two sample tables in this small test, one table called "vanorder" and one table called "vaninterest".

Logic of the sample system: A record is created in vanorder when user places an order. Each order starts at order_subset A, and each order can be accepted by multiple drivers. There will be a new record in the vaninterest table when a driver accepts an order. After accepting order, the driver has the option to reject an order, which will go back to the pool and allow other drivers to match this order again.

1) vanorder
- Contains the final status of the orders information
- idvanOrder: The order ID, which is the primary key 
- order_status: The final status of the order.
  -- 2: 'Completed'
  -- 3: 'Cancelled'
  -- 5: 'Expired'
- order_subset: The final order subset of the order
- requestor_client_id: The user account ID
- servicer_auth: The driver ID
- total_price: The price of the order
- order_datetime: The order time of the order
- txCreate: The record creation time, which is the order placed time by the user

2) vaninterest
- Contains the order information for each subset 
- idvanInterest: The primary key of this table 
- idvanOrder: The order ID associated to this record
- order_subset_assigned: The order subset that is associated to this record
- servicer_auth: The driver ID for this subset
- txCreate: The record creation time, which is the time that this driver accepted the order

We are using MySQL for the tables. The two csv files contain the same data.

Now we  write a few SQL statement to understand more about our data, users, and drivers. 

The answers to the SQL question 

find the answers for the questions numbered 5-8.
The .ipynb file is saved as "Data Analysis Using Python.ipynb"

The dashboard was made using Tableau and the file is saved as
"dashboard"
if there is a "1. missing file" popup
after opening Tableau select "1.csv" from " Answer for ques 5-8"
folder

1) For hours with orders, how many orders are there each hour based on order time?
2) What is the percentage of money spent for each of the following group of clients?
	- Clients who completed 1 order
	- Clients who completed more than 1 order
3) List of unique Client ID who completed at least one order, also show each client's total money spent, and the total order(s) completed. Order the list by total money spent (descending), then by total order(s) completed (descending)
4) List of all drivers who took order(s) (regardless of whether they eventually complete the order), also show each driver's total income and total order(s) completed. Order the list by total income (descending), then by total order(s) completed
5) List of driver ID who took orders, but never complete an order?

Now we will be doing some analysis using Python. Read the two csv files into Python "pandas" DataFrame with sample.py script (after editing the file paths), and do a quick analysis of the following,

6) What is the order fulfillment rate, i.e. percentage of orders that was completed, based on order time?
7) We will now look at the match time. Match time is the time it takes from user placing the order, to the driver accepting the order. For this part, consider only orders with a driver at subset A, i.e. all records with a driver at subset A in vaninterest table.
  (a) What is the average match time, by immediate/advanced orders? Immediate orders are defined as orders with order time within 60 minutes(inclusive) of placed time
  (b) What is the median match time, again by immediate/advanced?
  (c) Which of the above one do you think provides a better representation the data, i.e. a better metric for tracking our performance in matching?

One fundamental role of a data scientist is to put together useful data and analysis into dashboards. For the following dashboards, you can present them in any way you prefer. The dashboards should show the design, layout, and data for the dashboard.

8) How would you put together a dashboard for this data, to show the management team how we are doing today? 

9) If instead of the management team, how could we show a dashboard that is useful to the Operations team, who deals with the day-to-day operations and drivers verification(Our driver supply)?

To find the answers for the SQL questions in the " Answers for SQL.txt " file.

To find the answers for the questions numbered 5-8 open the
The .ipynb file is saved as "Data Analysis Using Python.ipynb"

The dashboard was made using Tableau and the file is saved as
"dashboard"
if there is a "1. missing file" popup
after opening Tableau select "1.csv" from " Answer for ques 5-8"
folder
