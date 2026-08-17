This file contains my SQL practice solutions for JOIN queries.

## Problem List

| # | Problem Name |
|---|---|
|[1](#problem-1) | Population Census|
| [2](#problem-2) |The Report |
| [3](#problem-3) | Ollivander's Inventory |
| [4](#problem-4) | Challenges |
| [5](#problem-5) |Contest Leaderboard |
| [6](#problem-6) | SQL Project Planning |
| [7](#problem-7) | Symmetric Pairs |
| [8](#problem-8)| Placements |
| [9](#problem-9)| New Companies |
| [10](#problem-10)| Company|


| [11](#problem-11)| Use of HAVING|
| [12](#problem-12)| All basic commands (together)|





















---

### Solutions

#### Problem 1
Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.
```
select sum(city.population) from city INNER JOIN country ON 
city.countrycode= country.code where country.continent='Asia'
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
