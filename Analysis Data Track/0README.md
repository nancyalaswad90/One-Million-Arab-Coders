

# Data-Analysis-Track  Certifications and Structures 


## First Certifications

![image](https://user-images.githubusercontent.com/36210723/65848891-b7ad7d80-e350-11e9-8ccc-f1c18d8eaaa6.png)


## Second Certifications

![image](https://user-images.githubusercontent.com/36210723/65848875-ad8b7f00-e350-11e9-88d8-969ef68da83b.png)



# Query a Digital Music Store (Part I)

## Introduction


In this lab, you will query the Chinook Database. The Chinook Database holds information about a music store. For this lab, you will be answering 4 queries to help the Chinook team understand the media in their store, their customers and employees, and their invoice information. To assist you in the queries ahead, the schema for the Chinook Database is provided below. You can see the columns that link tables together via the arrows.

https://s3.amazonaws.com/video.udacity-data.com/topher/2019/February/5c6164bf_chinook/chinook.png

## Q1

The Chinook database contains all invoices from the beginning of 2009 till the end of 2013. The employees at Chinook store are interested in seeing all invoices that happened in 2013 only. Using the Invoice table, write a query that returns all the info of the invoices in 2013.

Select *
From Invoice
Where InvoiceDate like'%2013%';


## Q2

The Chinook team decided to run a marketing campaign in Brazil, Canada, india, and Sweden. They will start with the country that has the least customers. Using the customer table, write a query that returns the first name, last name, and country for all customers from the 4 countries.

select FirstName , LastName , Country 
           From Customer
           where Country IN ('Brazil','Canada','India','Sweden')
           
## Q3

Using the Track and Album tables, write a query that returns all the songs that start with the letter 'A' and the composer field is not empty. Your query should return the name of the song, the name of the composer, and the title of the album.

Select Track.Name, Track.Composer, Album.Title
From Track
Join Album
On Track.AlbumId = Album.AlbumId
Where Track.Name  like 'A%' and Track.Composer IS NOT NULL ;


## Q4

The Chinook team would like to throw a promotional Music Festival for their top 10 cutomers who have spent the most in a single invoice. Write a query that returns the first name, last name, and invoice total for the top 10 invoices ordered by invoice total descending.

Select Customer.FirstName, Customer.LastName , Invoice.Total
From Customer
Join Invoice
On Customer.CustomerId = Invoice.CustomerId
Order by Invoice.Total DESC
Limit 10;


# Query a Digital Music Store (Part II)

In this lab, you will query the Chinook Database. The Chinook Database holds information about a music store.
Task
For this lab, you will help the Chinook team understand the media in their store, their customers and employees, and their invoice information.

## Key Takeaways
Use subqueries and temporary tables to take your queries to a whole new level
Use SQL to make data informed decisions


## Q1

Use the Invoice table to determine the countries that have the most invoices. Provide a table of BillingCountry and Invoices ordered by the number of invoices for each country. The country with the most invoices should appear first.

SELECT BillingCountry AS billingCountry,
       COUNT(*)       AS Invoices 
  FROM Invoice 
GROUP BY BillingCountry 
ORDER BY Invoices DESC;


## Q2

We would like to throw a promotional Music Festival in the city we made the most money. Write a query that returns the 1 city that has the highest sum of invoice totals. Return both the city name and the sum of all invoice totals.

check your solution

The top city for Invoice dollars was Prague with an amount of 90.24


SELECT BillingCity , SUM(Total) AS  sum_invoices
FROM Invoice
GROUP BY 1
ORDER BY 2 desc
LIMIT 1


##Q3

The customer who has spent the most money will be declared the best customer. Build a query that returns the person who has spent the most money. I found the solution by linking the following three: Invoice, InvoiceLine, and Customer tables to retrieve this information, but you can probably do it with fewer!

check your solution

The customer who spent the most according to invoices was Customer 6 with 49.62 in purchases.

SELECT c.CustomerId ,c.FirstName, c.LastName, SUM(i.Total) Invoices
FROM Invoice i
JOIN Customer c
ON c.CustomerId = i.CustomerId
GROUP BY 1,2,3
ORDER BY 4 DESC
limit 1

## Q4

The team at Chinook would like to identify all the customers who listen to Rock music. Write a query to return the email, first name, last name, and Genre of all Rock Music listeners. Return your list ordered alphabetically by email address starting with 'A'.

Check your solution

Your final table should have 59 rows and 4 columns.


SELECT distinct(c.Email), c.FirstName , c.LastName, g.Name as Genre
FROM Customer c
JOIN Invoice i
ON c.CustomerId = i.CustomerId
JOIN InvoiceLine il
ON i.InvoiceId = il.InvoiceId
JOIN Track t
ON il.TrackId = t.TrackId
JOIN Genre g
ON t.GenreId = g.GenreId
WHERE g.GenreId = (
                    SELECT GenreId
                    FROM Genre
                    WHERE NAME = "Rock")
ORDER BY 1 


## Q5

Write a query that determines the customer that has spent the most on music for each country. Write a query that returns the country along with the top customer and how much they spent. For countries where the top amount spent is shared, provide all customers who spent this amount.

You should only need to use the Customer and Invoice tables.

Check Your Solution

Though there are only 24 countries, your query should return 25 rows because the United Kingdom has 2 customers that share the maximum.


WITH t1
AS (SELECT
  c.Country As Country,
  c.FirstName  As FirstName,
  c.LastName AS LastName,
  c.CustomerId As CustomerId,
  SUM(i.Total) AS TotalSpent
FROM Customer  c
JOIN invoice  i
  ON c.CustomerId = i.CustomerId
GROUP BY 1,2,3),
t2
AS (SELECT
  t1.Country,
  MAX(t1.TotalSpent) AS max_spent
FROM t1
GROUP BY 1
ORDER BY 1, 2 DESC)
SELECT
  
  t1.CustomerId,
  t1.FirstName,
  t1.LastName,
  t1.Country,
  t1.TotalSpent
FROM t1
JOIN t2
  ON t1.country = t2.country
WHERE t1.TotalSpent =  t2.max_spent 
