# Assignment

## Brief

Write the SQL DML statements for the following questions.

## Instructions

Paste the answer as SQL in the answer code section below each question.

### Question 1

Select the minimum and maximum price per sqm of all the flats.

```sql

select  
round (max (resale_price/floor_area_sqm),2) as maximum_price,     
round(min (resale_price/floor_area_sqm),2) as minimum_price
from resale_flat_prices_2017

```

### Question 2

Select the average price per sqm for flats in each town.

```sql
SELECT 
  town,
  round (AVG(resale_price)/avg(floor_area_sqm),2) AS avg_price_sqm
FROM 
  resale_flat_prices_2017
GROUP BY 
  town;


```

### Question 3

Categorize flats into price ranges and count how many flats fall into each category:

- Under $400,000: 'Budget'
- $400,000 to $700,000: 'Mid-Range'
- Above $700,000: 'Premium'
  Show the counts in descending order.

```sql
SELECT
  COUNT(CASE WHEN resale_price < 400000 THEN 1 END) AS Budget,
  COUNT(CASE WHEN resale_price BETWEEN 400000 AND 700000 THEN 1 END) AS Midrange,
  COUNT(CASE WHEN resale_price > 700000 THEN 1 END) AS Premium
FROM
  resale_flat_prices_2017 dsc


```

### Question 4

Count the number of flats sold in each town during the first quarter of 2017 (January to March).

```sql
SELECT
 town,  COUNT(*) AS Sold,
  
FROM
  resale_flat_prices_2017 
GROUP BY 
  town;


```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
