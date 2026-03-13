# SQL Basics – HackerRank Practice

This file contains my SQL practice solutions for basic SELECT queries from HackerRank.

## Problem List

| # | Problem Name |
|---|---|
|[1](#problem-1) | Revising the Select Query I |
| [2](#problem-2) | Revising the Select Query II |
| [3](#problem-3) | Select All |
| [4](#problem-4) | Select By ID |
| [5](#problem-5) | Japanese Cities' Attributes |
| [6](#problem-6) | Japanese Cities' Names |
| [7](#problem-7) | Weather Observation Station 1 |
| [8*](#problem-8)| Weather Observation Station 3 |

---

### Solutions

#### Problem 1
```
SELECT * from CITY;
```
---
#### Problem 2
```
SELECT * from CITY where ID = 1661;
```
-----------------------------------
#### Problem 3
To query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.
```
SELECT * from CITY where COUNTRYCODE='USA' AND POPULATION > 100000;
```
-----------------------------------
#### Problem 4
```
SELECT NAME from CITY where POPULATION>120000 AND countrycode='USA';
```
-----------------------------------
#### Problem 5
```
SELECT * from CITY where countrycode='JPN';
```
-----------------------------------
#### Problem 6
```
SELECT name from CITY where countrycode='JPN';
```
-----------------------------------
#### Problem 7
```
SELECT city, state from STATION;
```
-----------------------------------
#### Problem 8
```
SELECT DISTINCT city from STATION where ID%2=0 ;
```
