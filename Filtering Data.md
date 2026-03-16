This file contains my SQL practice solutions for basic SELECT queries from HackerRank.

## Problem List

| # | Problem Name |
|---|---|
|[1](#problem-1) | Weather Observation Station 4 |
| [2](#problem-2) | Weather Observation Station 6|
| [3](#problem-3) | Weather Observation Station 7 |
| [4](#problem-4) | Higher Than 75 Marks |
| [5](#problem-5) | Employee Names |
| [6](#problem-6) | Employee Salaries |
| [7](#problem-7) | Type of Triangle |

---

### Solutions

#### Problem 1
Difference between the total number of CITY entries in the table and the number of distinct CITY entries
```
select count(city)- count(DISTINCT city) FROM STATION;
```
---
#### Problem 2
```
SELECT CITY, LENGTH(CITY) AS CityLength FROM STATION ORDER BY CityLength, CITY LIMIT 1; 
SELECT CITY, LENGTH(CITY) AS CityLength FROM STATION ORDER BY CityLength DESC, CITY LIMIT 1;
```
------------
#### Problem 3
list of CITY names starting with vowels from table STATION, without duplicates.
```
SELECT DISTINCT CITY
FROM STATION
CITY where city LIKE 'a%' OR
city LIKE 'e%' OR
city LIKE 'i%' OR
city LIKE 'o%' OR
city LIKE 'u%';
```
-----------------------------------
#### Problem 4
list of CITY names ending with vowels from table STATION, without duplicates.
```
SELECT DISTINCT CITY
FROM STATION
CITY where city LIKE '%a' OR
city LIKE '%e' OR
city LIKE '%i' OR
city LIKE '%o' OR
city LIKE '%u';
```
-----------------------------------
#### Problem 5
list of CITY names ending with vowels from table STATION, without duplicates.
```

```
-----------------------------------
