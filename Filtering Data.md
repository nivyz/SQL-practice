This file contains my SQL practice solutions for basic SELECT queries from HackerRank.

## Problem List

| # | Problem Name |
|---|---|
|[1](#problem-1) | Weather Observation Station 4 |
| [2](#problem-2) | Weather Observation Station 5|
| [3](#problem-3) | Weather Observation Station 6 |
| [4](#problem-4) | Weather Observation Station 7 |
| [5](#problem-5) | Higher Than 75 Marks |
| [6](#problem-6) | Employee Salaries|
| [7](#problem-7) | BETWEEN operator  |
| [8](#problem-8) | IN operator  |
| [9](#problem-9) | Type of Triangle |

---

### Solutions

#### Problem 1
Difference between the total number of CITY entries in the table and the number of distinct CITY entries
```
select count(city)- count(DISTINCT city) FROM STATION;
```
---
#### Problem 2
Two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
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
note: for vowel anywhere use pattern- eg: '%a%' ;
for 'a' at exactly 3rd postion- eg: '__a%'

-----------------------------------
#### Problem 5
Query the Name of any student in STUDENTS who scored not less than 76  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.
```
SELECT name from STUDENTS where marks>75 order by right(name,3),id ;
```
note:  equivalent to marks>75, NOT marks<76 can be used --> logical NOT.

-----------------------------------
#### Problem 6
Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than 2000  per month who have been employees for less than 10 months. Sort your result by ascending employee_id.
```
SELECT name from Employee where months<10 and salary>2000
order by employee_id
```
-----------------------------------
#### Problem 7
Query the Name of any student in STUDENTS who scored between 50 and 100  Marks. 
```
SELECT name from STUDENTS where marks BETWEEN 50 AND 100 ;
```
note: 50 and 100 are here inclusive.
  
-----------------------------------
#### Problem 8
Query the Name of students in STUDENTS who lives in germany or uk.
```
SELECT name from STUDENTS where country IN ('germany','uk') ;
```
note: similarly NOT IN operator also exist.
