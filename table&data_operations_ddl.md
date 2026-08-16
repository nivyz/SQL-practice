This file contains SQL practice solutions for basic table operations (DDL).

## Problem List

| # | Problem Name |
|---|---|
|[1](#problem-1) | Table creation with constraints |
| [2](#problem-2) | Alter table |
| [3](#problem-3) | Remove a column |
| [4](#problem-4) | Delete table |
| [5](#problem-5) | inserting data|
| [6](#problem-6) | modifying the data |
| [7](#problem-7) | delete data |

---

### Solutions

#### Problem 1
Create a new table called persons with columns: id, person_name, birth_date and phone
```
create table persons (
id int not null,         -- format# field | datatype | constraint
person_name varchar(50) not null,
birth_date date,
phone varchar(10) not null,
constraint pk primary key(id)
)
```
---
#### Problem 2
Add a column email to the table
```
alter table persons 
add email varchar(20)
```
-----------------------------------
#### Problem 3
Remove the column phone from table
```
alter table persons drop column phone

```
-----------------------------------
#### Problem 4
Delete the table
```
drop table persons
```
-----------------------------------
#### Problem 5
Insert data into table
```
insert into persons(id,person_name,birth_date,phone)
values (0,'max',null,'12342'),
(7,'abc','2.5.26','99992');

```
-----------------------------------
#### Problem 6
Change the score of odd-numbered customers to 0 and country to UK.
```
update customers
set score=0, country='UK'
where id%2!=0
```
note: if 'where' clause not used, full column gets updated accidentally.

-----------------------------------
#### Problem 7
Delete all customers with country UK.
```
delete from customers 
where country='UK'
```
note: to empty the whole table, TRUNCATE FROM customers is faster.
