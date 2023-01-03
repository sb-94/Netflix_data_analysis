# Netflix_data_analysis
A Sales dashboard for Executives

Steps involved:
1. Understand the problem
2. Collect and gather the data
3. Clean the data
4. Interpret the results

PROBLEM STATEMENT:
1. Total Revenue
2. Revenue per month
3. Revenue per State
4. Revenue per store
5. Revenue per Product category
6. Revenue per brand
7. Top 10 customers
8. Revenue per sales Rep



The data exploration, cleaning, removing any redundancies are done using SQL, Excel and Tableau.
To pull data from different tables into one, we'll first work on SQL. SQL will be used to gather the data and analyze the data. 


  /* QUERY TO PULL DATA FROM DIFFERENT OTHER TABLES */
  Refer to this link -:
  [Netflix_analysis.txt](https://github.com/sb-94/Netflix_data_analysis/files/10334743/Netflix_analysis.txt)
  
   SELECT 
   
  ord.order_id,
  
  CONCAT(cus.first_name,' ',cus.last_name)AS 'customers',
  
  cus.city,
  
  cus.state,
  
  ord.order_date,
  
  SUM(ite.quantity) AS 'total_units',
  
  SUM(ite.quantity*ite.list_price)AS 'revenue',
  
  pro.product_name,
  
  cat.category_name,
  
  sto.store_name,
  
  CONCAT(sta.first_name,' ',sta.last_name)AS 'sales_rep'
  
  FROM
  
  sales.orders ord
  
  JOIN sales.customers cus
  
  ON ord.customer_id=cus.customer_id
  
  JOIN sales.order_items ite
  
  ON ord.order_id=ite.order_id
  
  JOIN production.products pro
  
  ON ite.product_id=pro.product_id
  
  JOIN production.categories cat
  
  ON pro.category_id=cat.category_id
  
  JOIN sales.stores sto
  
  ON ord.store_id=sto.store_id
  
  JOIN sales.staffs sta
  
  ON ord.staff_id=sta.staff_id
  
  GROUP BY
  
  ord.order_id,
  
  CONCAT(cus.first_name,' ',cus.last_name),
  
  cus.city,
  
  cus.state,
  
  ord.order_date,
  
  SUM(ite.quantity),
  
  SUM(ite.quantity*ite.list_price),
  
  pro.product_name,
  
  cat.category_name,
  
  sto.store_name,
  
  CONCAT(sta.first_name,' ',sta.last_name)
  

  
  Data gathering is performed so that we can proceed to the next step in Excel.
  
  After importing the SQL file, we look for any redundancies, missing values and unwanted field in the dataset. After the data is cleaned and if everything is alright, we're ready to go to 
  the next step where the visuals are created using Tableau.
  
  
  ![Screenshot (34)](https://user-images.githubusercontent.com/117995417/210309925-b40b4282-e800-4b47-97e0-4f828f1aa721.png)

  
