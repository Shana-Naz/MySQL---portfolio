# Sales Insights 
# Data Analysis Using MySQL

1. Show all customer records
    
    SELECT * FROM customer;
    
2. Show total number of customers

    SELECT COUNT(*) FROM customer;
    
3. Show all the transactions for Delhi NCR market ( Marketcode is Mark004)

    SELECT * FROM transactions WHERE Market_code="Mark004";
    
4. Show distrinct product codes that were sold in Delhi NCR

   SELECT DISTINCT product_code FROM transactions WHERE Market_code="Mark004";
   
5. Show transactions of only 2020

   SELECT transactions.* , date.*  FROM transactions INNER JOIN date ON transactions.order_date = date.date WHERE date.year = 2020;
   
6. Show transactions currency is USD

   SELECT * FROM transactions WHERE currency = "USD";
  
7. Show total revenue of year 2020

   SELECT SUM(transactions.sales_amount) AS total_revenue FROM transactions INNER JOIN date ON transactions.order_date = date.date WHERE date.year = 2020 AND transactions.currency = "INR" OR transactions.currency = "USD";
  
8. Show total revenue of year 2020 in Delhi NCR 

   SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date = date.date WHERE date.year = 2020 AND transactions.Market_code = "Mark004";
