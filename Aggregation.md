This file contains my SQL practice solutions for Aggregation queries from HackerRank.

## Problem List

| # | Problem Name |
|---|---|
|[1](#problem-1) | Revising Aggregations – The Count Function |
| [2](#problem-2) | Revising Aggregations – The Sum Function |
| [3](#problem-3) | Revising Aggregations – Averages |
| [4*](#problem-4) | Average Population |
| [5](#problem-5) | Japan Population |
| [6*](#problem-6) | Population Density Difference |
| [7](#problem-7) | Top Earners |
| [8](#problem-8)| The Blunder |
| [9](#problem-9)| Weather Observation Station 14 |
| [10](#problem-10)| Weather Observation Station 15|
| [11](#problem-11)| Use of HAVING|
| [12](#problem-12)| All basic commands (together)|

---

### Solutions

#### Problem 1
Query a count of the number of cities in CITY having a Population larger than 100000.
```
select count(id) FROM city where population>100000
```
---
#### Problem 2
Sum of all population
```
SELECT sum(population) from city where district='California'
```
-----------------------------------
#### Problem 3
Average of all population
```
SELECT avg(population) from city where district='California'
```
-----------------------------------
#### Problem 4
Query the average population for all cities in CITY, rounded down to the nearest integer.
```
SELECT round(avg(population),0) from city
```
note: round (avg(population)) also works. '0' here is for the decimal part.
Similarly, ceiling(), floor() also available.
-----------------------------------
#### Problem 5
Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.
```
SELECT sum(population) from city where countrycode='JPN'
```
-----------------------------------
#### Problem 6
Query the difference between the maximum and minimum populations in CITY.
```
SELECT max(population) - min(population) from city

```
note: arithemetic subtraction is used for this. 
-----------------------------------
#### Problem 7
We define an employee's total earnings to be their monthly  worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as  space-separated integers.
```
SELECT salary*months, count(*) from Employee group by (salary*months) order by (salary*months) DESC limit 1
```
learning: aggregations return only a single value. so, count(max(salary*months)) is wrong
-----------------------------------
#### Problem 8
Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.
Write a query calculating the amount of error (i.e.:  average monthly salaries- errored), and round it up to the next integer.
```
select ceiling(avg(salary)- avg(cast(replace(salary,'0','') as unsigned)) ) from employees
```
note: unsigned bcos, 'integer' datatype unexist in Mysql.
main syntaxes used:
- REPLACE(value, old_text, new_text)
- CAST(value AS datatype)
- CEILING(number)
-----------------------------------
#### Problem 9
Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to  decimal places.
```
SELECT round(max(lat_n),4) from station where lat_n<137.2345
```
-----------------------------------
#### Problem 10
Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345 . Round your answer to  decimal places.
```
SELECT top 1 round(long_w,4) from station where lat_n < 137.2345 order by lat_n desc
```
note: top 1 (before tablename) or limit 1 (after tablename) can be used.
-----------------------------------
#### Problem 11
Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345 . Round your answer to  decimal places.
```
select year, avg(close) from tutorial.aapl_historical_stock_price GROUP by year having AVG(close)>100
```
-----------------------------------
#### Problem 12
Find the average score for each country considering only customers with a score not equal to 0 and return only those countries with an average score greater than 430.
```
select country,avg(score) as avg_score from dbo.customers where score !=0 GROUP BY country having avg(score)>430 order by avg_score desc
```
-----------------------------------

