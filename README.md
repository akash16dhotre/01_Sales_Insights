# 01_Sales_Insights
A project built in SQL and Power BI to analyze "Sales Insights" of the company. The project was implemented to primarily exercise my knowledge of data analysis and visualization. The project follows the pipeline of the project: Data gathering, data cleansing/data wrangling, model creation and generating dynamic reports in Power BI. I have recently upskilled and experimented using Power BI, this project should be a good exercise to put my learnings into action.

Following queries were utilized in the project to generate reports:

## Show all customer records
    SELECT * FROM customers;


## Show total number of customers
    SELECT count(*) FROM customers;


## Show transactions for Chennai market (market code for chennai is Mark001
    SELECT * FROM transactions where market_code='Mark001';


## Show distrinct product codes that were sold in chennai
    SELECT distinct product_code FROM transactions where market_code='Mark001';


## Show transactions where currency is US dollars
    SELECT * from transactions where currency="USD"


## Show transactions in 2020 join by date table
    SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;


## Show total revenue in year 2020,
    SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";


## Show total revenue in year 2020, January Month,
    SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");


## Show total revenue in year 2020 in Chennai
    SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
