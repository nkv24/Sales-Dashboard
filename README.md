## Sales Insights Data Analysis Project

### Instructions to setup mysql on your local computer

1. Follow step in this video to install mysql on your local computer
https://www.youtube.com/watch?v=WuBcTJnIuzo

1. SQL database dump is in db_dump.sql file above. Download `db_dump.sql` file to your local computer and import it as per instructions given in the tutorial video

### Data Analysis Using SQL

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

### MYSQL connection to Tableau
1. To connect mysql server to tableau, we need to download mysql-connector-odbc driver.
2. After installing the driver, connect tableau with mysql providing server, port database, username and password details of MySQL user
![image](https://user-images.githubusercontent.com/89015099/132034486-ef398a95-18e6-4c07-aea0-584282682bfe.png)
)

#### REVENUE DASHBOARD

<img width="800" alt="Revenue Analysis" src="https://user-images.githubusercontent.com/89015099/132034700-f7cb6c17-0075-431d-9b16-4cde7aa2835b.png">

#### PROFIT ANALYSIS DASHBOARD

<img width="800" alt="Profit Analysis" src="https://user-images.githubusercontent.com/89015099/132034751-f2b269f8-66a9-4874-b499-95d407a2ecf7.png">




