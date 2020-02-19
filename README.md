Introduction
===================


**This is the sql query list file**.



Mysql is very useful for exploring data and joint table ,make several calculation based on huge files in host server or in local server. Here are the sample list from the work.

> **Schema Imarket_sql**

>-  First using schema imarket_sql 
       > **USE** imarket_sql ;

> **Table Line_item**
   
>- Select the entire line_item table.
     
      SELECT * FROM line_item;
     
 > - Select only the first 10 rows from the line_item table
     
      SELECT * FROM line_item LIMIT 10;
      
>-   Select only the columns sku, unit_price and date from the line_item table (and only the first 10 rows)
     
      SELECT sku,unit_price,date FROM line_item LIMIT 10;

>-   Which products were bought in largest quantities? Select the “stock keeping unit” (sku) and product_quantity of the 100 products with the biggest "product quantity"
      
      SELECT sku,product_quantity  FROM line_item 
      ORDER BY product_quantity DESC    LIMIT 100;

> **Table Products**
> - What's the name and description of the most expensive product per brand and per category?
  
      SELECT name_en,short_desc_en,price,brand,manual_categories
      FROM products WHERE (price, brand,manual_categories) IN
      (SELECT max(price), brand,manual_categories
      FROM products  
      GROUP BY brand,manual_categories;






#### <i class="icon-file"></i> Joint Table

Here is mainly introduce how to joint defferent tables.


> **First using schema imarket_sql** 
       >- **USE** imarket_sql ;


   
>- Our first query should return the "sku", "product_quantity", "date" and "unit_price" from the line_item table together with the "name" and the "price" of each product from the "products" table. We want only products present in both tables.

![](https://github.com/Vangie1002/SQL/blob/master/1.PNG)

>- Build a query that outputs the price difference that you just calculated, grouping products by category. Round the result.

![](https://github.com/Vangie1002/SQL/blob/master/2.PNG)

>- Let's keep working on the same query: now we want to keep only Cancelled orders. Modify this query to group the results from the previous query, first by category and then by brand, adding in both cases a count so we know which categories and which brands are most times present in Cancelled orders.

![](https://github.com/Vangie1002/SQL/blob/master/3.PNG)

#### <i class="icon-folder-open"></i> There has more in the complete files
In the sprint 3 quesries PDF ,I have wrote all questions queries .
