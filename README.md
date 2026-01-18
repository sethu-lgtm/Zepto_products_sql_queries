# Zepto_products_sql_queries
"SQL queries for zepto_product analysis
use zepto_analysis;
select * from 
zepto_v2;
#1-how many total products are available in the zepto data set
select count(*) as total_products 
from zepto_v2;
#2-how many unique cataories are present 
select count( distinct category) as unique_categories
 from zepto_v2;
#3-list all distinct products categories 
select distinct category
 from zepto_v2;
#4-show all columns and their datatypes in the table
desc zepto_v2;
### product and pricing analysis
#5- find the top 10 most expensive products by mrp
select name,mrp from zepto_v2 order by mrp desc 
limit 10;
#6- find the top 10 most cheapest products by mrp
select name,mrp from zepto_v2 order by mrp asc
limit 10; 
#7- List the products with MRP greater than 5000
select  name,mrp from zepto_v2 
where mrp>5000;
#8-find products whose discounted selling price is less than 3000
select name,discountedSellingPrice from zepto_v2
 where discountedSellingPrice <3000;
#9-calculate the avg mrp of all products 
select avg(mrp) from zepto_v2 as avg_mrp;
#--10 find the max and min MRP in the dataset
select max(mrp) from zepto_v2;
select min(mrp) from zepto_v2;
###--category wise analysis
#11-- count the no of products in each category 
select category,count(name) from zepto_v2 group by category;
#12--find the avg MRP per category
select category,avg(mrp) from zepto_v2 
as avg_mrp group by category;
#13-- find categories where avg mrp is greater than 4000
select category,avg(mrp) from zepto_v2 as avg_mrp
 group by category 
having avg(mrp)>4000;
