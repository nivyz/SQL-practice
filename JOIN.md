This file contains my SQL practice solutions for JOIN queries.

## Problem List

| # | Problem Name |
|---|---|
|[1](#problem-1) | Population Census|
| [2](#problem-2) |The Report |
| [3](#problem-3) | Top Competitors |
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
You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks; Grades with grade, min_marks, max_marks.
Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

Write a query to help Eve.
```
select 
CASE
   when grade<8 then NULL
   else name
end as name, grade, marks from Students as s join 
Grades as g on s.marks between g.min_mark and g.max_mark
order by grade desc, 
case 
    when grade>=8 then name end asc,
CASE
    WHEN grade<8 then marks end asc
 
```
-----------------------------------
#### Problem 3
[Average of all population](https://www.hackerrank.com/challenges/full-score/problem)
```
select s.hacker_id,h.name
from Hackers as h join Submissions as s on h.hacker_id=s.hacker_id 
join Challenges as c on s.challenge_id=c.challenge_id 
join Difficulty as d on c.difficulty_level=d.difficulty_level
where s.score=d.score group by s.hacker_id,h.name having count(distinct s.challenge_id)>1 order by count(s.hacker_id) DESC, s.hacker_id ASC

```
-----------------------------------
