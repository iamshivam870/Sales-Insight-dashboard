# Sql analysis
A clean and professional dashboard project visualizing key metrics related to [insert topic]. Created as part of a learning project and refined based on feedback. Showcases data visualization, design skills, and insight presentation in a compact PDF format.

/*Show all customer records*/
select * from sales.customers;

/*Show total number of customers*/
select count(*) from sales.customers;

/*Show transactions for Chennai market (market code for chennai is Mark001*/
select * from sales.transactions where market_code = 'mark001';

/*Show distrinct product codes that were sold in chennai*/
select distinct product_code from transactions where market_code = 'mark001';

/*Show transactions where currency is US dollars*/
select * from transactions where currency = 'USD';

/*Show transactions in 2020 join by date table*/
select transactions.*, date.year from sales.date join sales.transactions on  transactions.order_date = date.date where date.year = 2020;

/*Show total revenue in year 2020*/
select sum(sales_amount) as Total_revenue from sales.date join sales.transactions on  transactions.order_date = date.date where date.year = 2020;

/*Show total revenue in year 2020, January Month*/
select sum(sales_amount) as Total_revenue from sales.date join sales.transactions on  transactions.order_date = date.date 
where date.year = 2020 and month_name = 'january';

 /*Show total revenue in year 2020 in Chennai*/
select sum(sales_amount) as Total_revenue from sales.date join sales.transactions on  transactions.order_date = date.date 
where date.year = 2020 and market_code = 'mark001';
