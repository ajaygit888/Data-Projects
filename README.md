# E-COMMERCE SALES ANALYTICS PROJECT 
I Analyzed sales data from an e-commerce walmart business to gain insights & identify sales trends, quaterly patterns, top-preforming products, evaluate categorical sales 
 performance, and make data-driven recommendations.
 
# SALES INSIGHTS PROJECT - DATA ANALYSIS USING SQL
  In this project I analyze sales Insights data from sql database. And this project I used some sql function for analyze the sales 
  Insights data. And some looks like this...(AGGRIGATIVE FUNCTION, WINDOW FUNCTION, JOINS CLAUSE, WHERE CLAUSE, GROUP BY, ORDER BY, 
  LIMIT).  
# Analyze total_revenue in a table.
  select sum(t.sales_amount) as total_revenue from transactions as t where t.currency='inr\r' or t.currency= 'usd\r';

# Analyze total sales_qty in a table.
  select sum(sales_qty) as total_sales_qty from transactions;

# Analyze total revenue each Market code.
  select markets_code, sum(t.sales_amount) as revenue from transactions as t
  join markets as m on t.market_code=m.markets_code
  where t.currency='inr\r'or t.currency='usd\r' group by markets_code order by sum(t.sales_amount) desc;
 
# Analyze total revenue each markets name by zone.
  select m.zone, m.markets_name, sum(t.sales_amount)'revenue',
  row_number() over (partition by m.zone order by sum(t.sales_amount) desc)'Num_zone' from transactions t
  join markets m on t.market_code=m.markets_code
  where t.currency='inr\r' or t.currency='usd\r' group by m.zone,m.markets_name;

# Analyze total revenue each year.
  select d.year, sum(t.sales_amount)as revenue from transactions as t
  join date as d on t.order_date=d.date
  where t.currency='inr\r'or t.currency='usd\r' group by d.year;

# Analyze total revenue each Customer_type.
  select customer_type, sum(t.sales_amount) as revenue from transactions as t
  join customers as c on t.customer_code=c.customer_code
  where t.currency='inr\r'or t.currency='usd\r' group by customer_type;

# Analyze total revenue each Product_type.
  select product_type, sum(t.sales_amount)as revenue from transactions as t
  join products as p on t.product_code=p.product_code
  where t.currency='inr\r'or t.currency='usd\r' group by product_type;

# Analyze total revenue by top 15 customer's. 
  select custmer_name, sum(t.sales_amount)as revenue from transactions as t
  join customers as c on t.customer_code=c.customer_code
  where t.currency='inr\r'or t.currency='usd\r'
  group by custmer_name order by sum(t.sales_amount) desc limit 15;

# SUPERSTORE ANALYSIS PROJECT
  Superstore data analysis for the superstore sales dataset. Collect dataset from Kaggle. And load the data on power BI from ETL process. 
  And finally visualize the data.
  Analyzed Superstore sales data by region, category, and segment.
  Created visualizations to display sales and profit data.
  Identified top 10 profitable customers and top 10 selling products.

# NETFLIX MOVIES & TV SHOWS ANALYSIS PROJECT 
  netflix movies & tv shows dataset from Kaggle. And loaded the csv.file data on power BI for analyzing the data. For this project I used 
  DAX QUERY (exp. COUNTX FUNCTION for used find of total number of movies & total number of shows).
  I Analyzed the number of movies and TV shows released per year by Netflix.
  Explored ratings of Netflix movies and TV shows.
  Identified top 10 actors, directors, and viewed genres.
  Utilized DAX queries, including COUNTX, to analyze the top 5 movies and shows on Netflix.
