# Sales Insights Project - Data Analysis using SQL

  #Total_Revenue & sales_Qty
select sum(t.sales_amount) as total_revenue from transactions as t where t.currency='inr\r' or t.currency= 'usd\r' ;
select sum(sales_qty) as total_sales_qty from transactions;

  #Revenue by Markets_name
select markets_name, sum(t.sales_amount) as revenue_by_markets_name from transactions as t join markets as m on t.market_code=m.markets_code where t.currency='inr\r'or t.currency='usd\r' group by markets_name order by sum(t.sales_amount) desc;

  #Revenue by year's
select sum(t.sales_amount) as revenue_by_year_2017 from transactions as t join date as d on t.order_date=d.date where d.year='2017'and t.currency='INR\r'or t.currency='usd\r';

select sum(t.sales_amount) as revenue_in_year_2018 from transactions as t join date as d on t.order_date=d.date where d.year='2018'and t.currency='INR\r'or t.currency='usd\r';

select sum(t.sales_amount) as revenue_in_year_2019 from transactions as t join date as d on t.order_date=d.date where d.year='2019'and t.currency='INR\r'or t.currency='USD\r';

select sum(t.sales_amount) as revenue_in_year_2020 from transactions as t join date as d on t.order_date=d.date where d.year='2020'and t.currency='INR\r'or t.currency='USD\r';

  #Revenue by Customer_type
select customer_type, sum(t.sales_amount) as revenue_by_customer_type from transactions as t join customers as c on t.customer_code=c.customer_code where t.currency='inr\r'or t.currency='usd\r' group by customer_type;

select sum(t.sales_amount)as revenue_by_Brick_and_Mortar from transactions as t join customers as c on t.customer_code=c.customer_code where customer_type='Brick & Mortar' and t.currency='inr\r'or t.currency='usd\r';

select sum(t.sales_amount)as revenue_by_E_commerce from transactions as t join customers as c on t.customer_code=c.customer_code where customer_type='E-commerce' and t.currency='inr\r'or t.currency='usd\r';

  #Revenue by Product_type
select product_type, sum(t.sales_amount)as revenue_by_product_type from transactions as t join products as p on t.product_code=p.product_code group by product_type;

select sum(t.sales_amount)as revenue_by_Own_Brand from transactions as t join products as p on t.product_code=p.product_code where product_type='Own Brand' and t.currency='inr\r'or t.currency='usd\r';

select sum(t.sales_amount)as revenue_by_Distribution from transactions as t join products as p on t.product_code=p.product_code where product_type='Distribution' and t.currency='inr\r' or t.currency='usd\r';

  #Revenue by top 15 customer_name
select custmer_name, sum(t.sales_amount)as revenue_by_top_15_customer_name from transactions as t join customers as c on t.customer_code=c.customer_code where t.currency='inr\r'or t.currency='usd\r' group by custmer_name order by sum(t.sales_amount) desc limit 15;

# Superstore Data Analysis project
Superstore data analysis for the superstore sales dataset. Collect dataset from Kaggle. And load the data on power BI from ETL process. And finally visualize the data.
I create visualization to show the Analyze sales & profit data by Region.
Built a visualization to show the Analyze sales & proft data by Category.
Built a visualization to show the Analyze sales & profit data by Segment.
And visualize to show the Analyze top 10 Profitable Customer.
Another visualize to show the Analyze top 10 selling Product.

# Netflix movies & tv shows data analysis project
netflix movies & tv shows dataset from Kaggle. And loaded the csv.file data on power BI for analyzing the data. For this project I used DAX QUIREY (exp. COUNTX FUNCTION for used find of total number of movies & total number of shows).
I analyze number of movies & tv shows released per year.
Analyze ratings of movies & tv shows on Netflix.
Analyze top 10 viewed genres.
Analyze top 10 Actors & Directors on Netflix movies & tv shows.
Analyze top 5 Movies & Shows on Netflix.
