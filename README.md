# Sales Insights Project - Data Analysis using SQL
In this project I analyze sales Insights data from sql database. And this project I used some sql function for analyze the sales Insights data. And some looks like this...(AGGRIGATIVE FUNCTION, WINDOW FUNCTION, JOINS CLAUSE, WHERE CLAUSE, GROUP BY, ORDER BY, LIMIT).  

  # Find out total_revenue in table.
select sum(t.sales_amount) as total_revenue from transactions as t where t.currency='inr\r' or t.currency= 'usd\r';

  # Find out total sales_qty in table.
select sum(sales_qty) as total_sales_qty from transactions;

  # Find out total revenue each Markets name.
select markets_name, sum(t.sales_amount) as revenue from transactions as t
 join markets as m on t.market_code=m.markets_code
 where t.currency='inr\r'or t.currency='usd\r' group by markets_name order by sum(t.sales_amount) desc;
 
 # Find out total revenue each markets name by zone.
select m.zone, m.markets_name, sum(t.sales_amount)'revenue',
 row_number() over (partition by m.zone order by sum(t.sales_amount) desc)'Num_zone' from transactions t
 join markets m on t.market_code=m.markets_code
 where t.currency='inr\r' or t.currency='usd\r' group by m.zone,m.markets_name;

  # Find out total revenue each year.
 select d.year, sum(t.sales_amount)as revenue from transactions as t
  join date as d on t.order_date=d.date
  where t.currency='inr\r'or t.currency='usd\r' group by d.year;

  # Find out total revenue each Customer_type.
select customer_type, sum(t.sales_amount) as revenue from transactions as t
 join customers as c on t.customer_code=c.customer_code
 where t.currency='inr\r'or t.currency='usd\r' group by customer_type;

  # Find out total revenue each Product_type.
select product_type, sum(t.sales_amount)as revenue from transactions as t
 join products as p on t.product_code=p.product_code
 where t.currency='inr\r'or t.currency='usd\r' group by product_type;

  # Find out total revenue by top 15 customer's. 
select custmer_name, sum(t.sales_amount)as revenue from transactions as t
 join customers as c on t.customer_code=c.customer_code
 where t.currency='inr\r'or t.currency='usd\r'
 group by custmer_name order by sum(t.sales_amount) desc limit 15;

# Superstore Data Analysis project
Superstore data analysis for the superstore sales dataset. Collect dataset from Kaggle. And load the data on power BI from ETL process. And finally visualize the data.
I create visualization to show the Analyze sales & profit data by Region.
Built a visualization to show the Analyze sales & proft data by Category.
Built a visualization to show the Analyze sales & profit data by Segment.
And visualization to show the Analyze top 10 Profitable Customer.
Another visualization to show the Analyze top 10 selling Product.

# Netflix movies & tv shows data analysis project
netflix movies & tv shows dataset from Kaggle. And loaded the csv.file data on power BI for analyzing the data. For this project I used DAX QUERY (exp. COUNTX FUNCTION for used find of total number of movies & total number of shows).
I analyze number of movies & tv shows released per year.
Analyze ratings of movies & tv shows on Netflix.
Analyze top 10 viewed genres.
Analyze top 10 Actors & Directors on Netflix movies & tv shows.
Analyze top 5 Movies & Shows on Netflix.
