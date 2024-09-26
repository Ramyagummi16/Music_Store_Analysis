# Music_store_Analysis
This project contains a series of SQL queries aimed at analyzing a music store database. The queries focus on extracting and analyzing key data, such as sales performance, customer demographics, and inventory details, providing insights into store operations and business trends.

1Q. Who is the senior most employee based on job title? 
    SELECT * FROM employee
    ORDER by levels DESC
    LIMIT 1

2Q: Which countries have the most Invoices?
    SELECT COUNT(*) as Total_invoices, billing_country 
    FROM invoice
    GROUP BY billing_country
    ORDER BY Total_invoices desc

3Q: What are top 3 values of total invoice and the countries? 
    SELECT billing_country, total FROM invoice 
    ORDER BY total desc
    LIMIT 3

4Q: Q4: Which city has the best customers? We would like to throw a promotional Music Festival in the city we made the most money. 
Write a query that returns one city that has the highest sum of invoice totals. 
Return both the city name & sum of all invoice totals
    SELECT billing_city, ROUND(SUM(total)) AS Total_Invoices
    FROM invoice
    GROUP BY billing_city
    ORDER BY Total_Invoices  DESC
    LIMIT 1

5Q: Who is the best customer? The customer who has spent the most money will be declared the best customer. 
Write a query that returns the person who has spent the most money.
    SELECT c.customer_id, c.first_name, c.last_name, ROUND(SUM(i.total)) AS Total_money 
    FROM customer c
    INNER JOIN invoice i
    on c.customer_id = i.customer_id
    GROUP BY c.customer_id
    ORDER BY Total_money DESC
    LIMIT 1






