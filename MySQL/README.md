- [1.Introduction to SQL](#1introduction-to-sql)
  - [1.1 RDBMS](#11-rdbms)
  - [1.2 SQL commands](#12-sql-commands)
  - [1.2 SELECT](#12-select)
  - [1.3 WHERE](#13-where)
  - [1.4 ORDER BY ( ASC | DESC )](#14-order-by--asc--desc-)
  - [1.5 INSERT INTO](#15-insert-into)
  - [1.6 NULL VALUE](#16-null-value)
  - [1.7 UPDATE Syntax](#17-update-syntax)
  - [1.8 DELETE Syntax](#18-delete-syntax)
  - [1.8 LIMIT Syntax](#18-limit-syntax)
  - [1.9 Min() Max()](#19-min-max)
  - [1.10 COUNT(), AVG() and SUM()](#110-count-avg-and-sum)
  - [1.11 Wildcard Characters](#111-wildcard-characters)
  - [1.12 Like syntax](#112-like-syntax)
  - [1.13 IN Syntax](#113-in-syntax)
  - [1.14 Between syntax](#114-between-syntax)
  - [1.15 Alias( AS ) Column Syntax](#115-alias-as--column-syntax)
  - [1.16 Joining Tables](#116-joining-tables)
    - [1.16.1 Inner join](#1161-inner-join)
    - [1.16.2 Left join](#1162-left-join)
    - [1.16.3 Right join](#1163-right-join)
    - [1.16.4 CROSS JOIN](#1164-cross-join)
    - [1.16.5 Self join](#1165-self-join)
  - [1.17 Union](#117-union)
  - [1.18 GROUP BY](#118-group-by)
  - [1.19 Having](#119-having)
  - [1.19 EXISTS](#119-exists)
  - [1.20 ANY and ALL](#120-any-and-all)
    - [1.20.1 ANY Operator](#1201-any-operator)
    - [1.20.2 ALL Operator](#1202-all-operator)
  - [1.21 INSERT INTO](#121-insert-into)
  - [1.22 CASE Syntax](#122-case-syntax)
  - [1.23 IFNULL() and COALESCE()](#123-ifnull-and-coalesce)
  - [1.24 If  condition](#124-if--condition)
- [2 Section two](#2-section-two)
  - [2.1 Create database](#21-create-database)
  - [2.2 Drop database](#22-drop-database)
  - [2.3 CREATE TABLE](#23-create-table)
    - [2.3.1 Create Table Using Another Table](#231-create-table-using-another-table)
  - [2.4 Drop table](#24-drop-table)
  - [2.5 After Table](#25-after-table)
  - [2.6 Create Constraints](#26-create-constraints)
  - [2.7 NOT NULL](#27-not-null)
  - [2.8 UNIQUE Constraint](#28-unique-constraint)
  - [2.9 Primary key](#29-primary-key)
  - [2.10 FOREIGN KEY](#210-foreign-key)
  - [2.11 CHECK Constraint](#211-check-constraint)
  - [Default](#default)
  - [2.12 Create Index](#212-create-index)
  - [2.13 AUTO\_INCREMENT](#213-auto_increment)
  - [2.14 Date Data Types](#214-date-data-types)
  - [2.14 create view](#214-create-view)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


# 1.Introduction to SQL

- SQL stands for Structured Query Language
- SQL lets you access and manipulate databases

## 1.1 RDBMS

- RDBMS stands for Relational Database Management System.
- The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.
- A relational database defines database relationships in the form of tables. The tables are related to each other - based on data common to each.

## 1.2 SQL commands

- SELECT - extracts data from a database
- UPDATE - updates data in a database
- DELETE - deletes data from a database
- INSERT INTO - inserts new data into a database
- CREATE DATABASE - creates a new database
- ALTER DATABASE - modifies a database
- CREATE TABLE - creates a new table
- ALTER TABLE - modifies a table
- DROP TABLE - deletes a table
- CREATE INDEX - creates an index (search key)
- DROP INDEX - deletes an index

## 1.2 SELECT

Create example table

~~~~sql
-- Create a table
CREATE TABLE example (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

-- Insert data into the table
INSERT INTO example (id, name, age)
VALUES
    (1, 'John Doe', 25),
    (2, 'Jane Smith', 30),
    (3, 'Bob Johnson', 22),
    (4, 'Top Kohnson', 22);

~~~~

Table look like this.
![Alt text](image.png)

1. ```select * from example;```\
Full table will show.
2. ```select name,id from example;```\
Only name and id will show. **Note** that here first name then id. It's maintain the order of query.
![Alt text](image-1.png)
3. ```select distinct * from example;```\
Does not take duplicate rows. Each copy only one piece.
4. ```select distinct age from example;```\
First Select selected colume(age) then remove duplicate rows.
![Alt text](image-2.png)
5. ```select count(distinct age) from example;```\
Return the number of distinct row with coloum=age
![Alt text](image-3.png)
6. ```select count(distinct age,name) from example;```\
Return the number of distinct row with coloum=age,name
![Alt text](image-4.png)

## 1.3 WHERE

Table same as older one.
![Alt text](image-5.png)

1. ```select * from example where age>=25;```\
   ![Alt text](image-6.png)
2. ```select name,id from example where age>=25 and id=2;```
   ![Alt text](image-7.png)
3. BETWEEN\
   ```select name,age from example where age between 20 and 25;```
   ![Alt text](image-8.png)
4. LIKE\
   ```select name,age from example where name like "j%";```
   ![Alt text](image-9.png)
5. IN\
   ```select name from example where name in ("John Doe","Bob Johnson");```
   ![Alt text](image-10.png)

- We can also use **distinct** and **count** here if we need.
- Alse we can use And,or not(!) operation same as c++.

## 1.4 ORDER BY ( ASC | DESC )

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

Table
![Alt text](image-11.png)

```select * from example order by name;```
```select * from example order by name asc;```
![Alt text](image-12.png)
```select name, id from example order by name ASC;```
![Alt text](image-13.png)
```select * from example order by age ASC,id DESC;```
![Alt text](image-14.png)

## 1.5 INSERT INTO

1. Adding value to the all columns

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

2. Adding value to the specify columns

```sql
INSERT INTO table_name VALUES (value1, value2, value3, ...);
```

Table same as older one.
![Alt text](image-5.png)

```insert into example (id,name,age) values (5,"Imran",26);```
```insert into example values (5,"Imran",26);```
![Alt text](image-15.png)
```insert into example (id,name) values (5,"Imran");```
![Alt text](image-16.png)

## 1.6 NULL VALUE

A NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during record creation!

```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```

```sql
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;
```

```sql
select * from example where age is null;
```

![Alt text](image-17.png)

## 1.7 UPDATE Syntax

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

![Alt text](image-5.png)
```update example set name='test',age=30 where id=3;```
![Alt text](image-18.png)
```update example set age=30 ;```
![Alt text](image-19.png)

## 1.8 DELETE Syntax

Table
![Alt text](image-20.png)

```sql
delete from example where id=4;
```

![Alt text](image-21.png)

- Delete All Records

```sql
delete from example ;
```

Here all record will be deleted.

## 1.8 LIMIT Syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

Table
![Alt text](image-20.png)

- Select first 3 rows.

```sql
select * from example limit 3;
```

![Alt text](image-22.png)

- From index(offset) i to limit x

```sql
select * from example LIMIT 3 OFFSET 1;
-- Here start from index 1+ and take 3 element.
```

![Alt text](image-23.png)

## 1.9 Min() Max()

Table
![Alt text](image-20.png)

```sql
select max(age) from example ;
```

![Alt text](image-24.png)

```sql
select min(age) from example;
```

![Alt text](image-25.png)

## 1.10 COUNT(), AVG() and SUM()

- count

```sql()
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```

- avg()

```sql
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```

- sum()

```sql
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```

Table
![Alt text](image-20.png)

Operation

```sql
select count(age) from example;
select avg(age) from example;
select sum(age) from example;
```

![Alt text](image-26.png)

## 1.11 Wildcard Characters

- (%) represent zero or more characters (bl%-> black,blue)
- (_) represent a single character h_t-> hot, hat, hit

## 1.12 Like syntax

```sql
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;
```

Table
![Alt text](image-20.png)

```sql
select * from example where name like '%n';
select * from example where name like '%so_%';
```

![Alt text](image-27.png)

## 1.13 IN Syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);
```

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name IN (SELECT STATEMENT);
```

Table
![Alt text](image-28.png)

```sql
select * from example where age in (22,30);
select * from example where name in (select name from student);
```

![Alt text](image-29.png)
1st table is example and second one is student.

## 1.14 Between syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

Table
![Alt text](image-30.png)

```sql
select * from example where age between 23 and 30 order by name;
```

After query
![Alt text](image-31.png)

## 1.15 Alias( AS ) Column Syntax

```sql
SELECT column_name AS alias_name
FROM table_name;
```

Table
![Alt text](image-30.png)

```sql
select id as e_id , name as e_name from example;
```

![Alt text](image-32.png)

Another example:

```sql
SELECT o.OrderID, o.OrderDate, c.CustomerName
FROM Customers AS c, Orders AS o
WHERE c.CustomerName='Around the Horn' AND c.CustomerID=o.CustomerID;
```

## 1.16 Joining Tables

This table I will use in this joining section.

```sql
-- Create a table
CREATE TABLE A (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

-- Insert data into the table
INSERT INTO A (id, name, age)
VALUES
(1, 'John Doe', 25),
(2, 'Jane Smith', 30),
(3, 'Bob Johnson', 22),
(4, 'Top Kohnson', 22),
(5, 'Imran Hosen', 23);

-- Create table B with a similar structure
CREATE TABLE B (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

-- Insert different data into the table B
INSERT INTO B (id, name, age)
VALUES
(6, 'Alice Brown', 28),
(7, 'Charlie Miller', 30),
(8, 'David Wilson', 29),
(9, 'Eva Davis', 22),
(10, 'Frank White', 25);

```

![Alt text](image-34.png)

Lets see an example

```sql
select A.name as A_name ,A.id as A_id, B.name as B_name,B.id as B_id from A inner join B on A.age=B.age;
```

Output
![Alt text](image-36.png)

![Alt text](image-35.png)

- **INNER JOIN:** Returns records that have matching values in both tables
- **LEFT JOIN:** Returns all records from the left table, and the matched records from the right table
- **RIGHT JOIN:** Returns all records from the right table, and the matched records from the left table
- **CROSS JOIN:** Returns all records from both tables

### 1.16.1 Inner join

In upper we already see an example of inner join.\
Lets see two code

```sql
select A.name as A_name ,A.id as A_id, B.name as B_name,B.id as B_id from A inner join B on A.age=B.age;
```

JOIN Three Tables

```sql
SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
FROM ((Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);
```

### 1.16.2 Left join

![Alt text](image-37.png)

```sql
select A.name as A_name ,A.id as A_id, B.name as B_name,B.id as B_id from A left join B on A.age=B.age;
```

![Alt text](image-38.png)

### 1.16.3 Right join

```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;

```

![Alt text](image-39.png)

```sql
select A.name as A_name ,A.id as A_id, B.name as B_name,B.id as B_id from A  right join B on A.age=B.age;
```

![Alt text](image-40.png)

### 1.16.4 CROSS JOIN

```sql
SELECT column_name(s)
FROM table1
CROSS JOIN table2;
```

![Alt text](image-41.png)

```sql
select A.name as A_name ,A.id as A_id, B.name as B_name,B.id as B_id from A  cross join B on A.age=B.age;
```

![Alt text](image-42.png)

```sql
select A.name as A_name ,A.id as A_id, B.name as B_name,B.id as B_id from A  cross join B ;
```

![Alt text](image-43.png)

###  1.16.5 Self join

A self join is a regular join, but the table is joined with itself.

```sql
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```

![Alt text](image-44.png)

## 1.17 Union

```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

- Every SELECT statement within UNION must have the same number of columns
- The columns must also have similar data types
- The columns in every SELECT statement must also be in the same order

> The **UNION** operator selects only distinct values by default. To allow duplicate values, use **UNION ALL**:
![Alt text](image-45.png)

```sql
select A.name,A.id from A union select B.name,B.id from B;
```

![Alt text](image-46.png)

```sql
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION
SELECT City, Country FROM Suppliers
WHERE Country='Germany'
ORDER BY City;
```

## 1.18 GROUP BY

Group by the simillar value

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```

![Alt text](image-47.png)

```sql
select count(age) ,age from A group by age;
```

![Alt text](image-48.png)

```sql
select count(age) ,age from A group by age order by count(age);
```

![Alt text](image-49.png)

## 1.19 Having

```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```

```sql
select count(age) ,age from A group by age having count(age)>=2;
```

![Alt text](image-50.png)

## 1.19 EXISTS

- The EXISTS operator is used to test for the existence of any record in a subquery.

- The EXISTS operator returns TRUE if the subquery returns one or more records.

```sql
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```

## 1.20 ANY and ALL

### 1.20.1 ANY Operator

- returns a boolean value as a result
- returns TRUE if ANY of the subquery values meet the condition

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
  (SELECT column_name
  FROM table_name
  WHERE condition);
```

### 1.20.2 ALL Operator

- returns a boolean value as a result
- returns TRUE if ALL of the subquery values meet the condition
- is used with SELECT, WHERE and HAVING statements

```sql
-- All with select
SELECT ALL column_name(s)
FROM table_name
WHERE condition;
```

```sql
-- all with wherer/having
SELECT column_name(s)
FROM table_name
WHERE column_name operator ALL
  (SELECT column_name
  FROM table_name
  WHERE condition);
```

Table

```sql
CREATE TABLE OrderDetails (
    OrderDetailID INT PRIMARY KEY,
    OrderID INT,
    ProductID INT,
    Quantity INT
);

-- Insert data into the table
INSERT INTO OrderDetails (OrderDetailID, OrderID, ProductID, Quantity)
VALUES
(1, 10248, 11, 12),
(2, 10248, 42, 10),
(3, 10248, 72, 5),
(4, 10249, 14, 9),
(5, 10249, 51, 40),
(6, 10250, 41, 10),
(7, 10250, 51, 35),
(8, 10250, 65, 15),
(9, 10251, 22, 6),
(10, 10251, 57, 15);
```

![Alt text](image-51.png)

- lets assume Order list another table.

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ALL
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```

## 1.21 INSERT INTO

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers;
```

```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
SELECT SupplierName, ContactName, Address, City, PostalCode, Country FROM Suppliers;
```

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers
WHERE Country='Germany';
```

## 1.22 CASE Syntax

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

![Alt text](image-52.png)

```sql
select OrderId,Quantity,
case 
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
end as QuantityText from OrderDetails;
```

![Alt text](image-53.png)

## 1.23 IFNULL() and COALESCE()

- IFNULL() function lets you return an alternative value if an expression is NULL.

```sql
SELECT IFNULL(NULL, 500);
-- output 500
```

```sql
SELECT ProductName, UnitPrice * (UnitsInStock + IFNULL(UnitsOnOrder, 0))
FROM Products;
```

- The COALESCE() function returns the first non-null value in a list.

```sql
SELECT COALESCE(NULL, NULL, NULL, 'W3Schools.com', NULL, 'Example.com');
--output W3Schools.com
```
## 1.24 If  condition
![Alt text](image-58.png)

Report for every three line segments whether they can form a triangle.

```sql
select *,if( x+y>z and x+z>y and z+y>x, 'Yes','No') as triangle  from Triangle 
```

# 2 Section two

## 2.1 Create database

```sql
CREATE DATABASE databasename;
```

## 2.2 Drop database

```sql
DROP DATABASE databasename;
```

## 2.3 CREATE TABLE

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
```

```sql
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
```

### 2.3.1 Create Table Using Another Table

```sql
CREATE TABLE new_table_name AS
    SELECT column1, column2,...
    FROM existing_table_name
    WHERE ....;
  -- Another example
CREATE TABLE TestTable AS
SELECT customername, contactname
FROM customers;
```

## 2.4 Drop table

```sql
DROP TABLE table_name;
```

## 2.5 After Table

- add
- delete
- modify
- drop
  
1. Add

```sql
ALTER TABLE table_name
ADD column_name datatype;

-- example
ALTER TABLE Customers
ADD Email varchar(255);
```

2. DROP COLUMN

```sql
ALTER TABLE table_name
DROP COLUMN column_name;

-- example
ALTER TABLE Customers
DROP COLUMN Email;
```

3. MODIFY COLUMN

```sql
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

## 2.6 Create Constraints

```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ....
);
```

![Alt text](image-54.png)

- if a column has NOT NULL constraint, it means the column cannot store NULL values.

## 2.7 NOT NULL

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

```sql
-- Create the table
CREATE TABLE person (
    id INT NOT NULL,
    firstName VARCHAR(255) NOT NULL,
    age INT
);

-- Insert data into the table
INSERT INTO person (id, firstName, age) VALUES
(1, 'John', 22),
(2, 'Jane', 25),
(3, 'Bob', 30),
(4, 'Alice', 28);

-- Modify the age column to be NOT NULL
ALTER TABLE person MODIFY age INT NOT NULL;
ALTER TABLE person ADD class INT NOT NULL;
```

![Alt text](image-55.png)

## 2.8 UNIQUE Constraint

- The UNIQUE constraint ensures that all values in a column are different.
- A PRIMARY KEY constraint automatically has a UNIQUE constraint.

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);
```

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT UC_Person UNIQUE (ID,LastName)
);
```

```sql
ALTER TABLE Persons
ADD UNIQUE (ID);
```

## 2.9 Primary key

- The PRIMARY KEY constraint uniquely identifies each record in a table.

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```

- PRIMARY KEY constraint on multiple columns,

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

In after table

```sql
ALTER TABLE Persons
ADD PRIMARY KEY (ID);

ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
-- drop primary key
ALTER TABLE Persons
DROP PRIMARY KEY;
```

## 2.10 FOREIGN KEY

- The FOREIGN KEY constraint is used to prevent actions that would destroy links between tables.
- A FOREIGN KEY is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table.

![Alt text](image-56.png)

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```

- using after table

```sql
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

Drop foreign key

```sql
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```

## 2.11 CHECK Constraint

- The CHECK constraint is used to limit the value range that can be placed in a column.

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);
```

using after table

```sql
ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
```

## Default

--- The DEFAULT constraint is used to set a default value for a column.

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Sandnes'
);
```

After table

```sql
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';
-- drop
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```

## 2.12 Create Index

- The CREATE INDEX statement is used to create indexes in tables.

Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.

-**Note:** Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);

CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...);
-- example
CREATE INDEX idx_pname
ON Persons (LastName, FirstName);

-- drop 
ALTER TABLE table_name
DROP INDEX index_name;
```

## 2.13 AUTO_INCREMENT

- MySQL uses the AUTO_INCREMENT keyword to perform an auto-increment feature.

```sql
CREATE TABLE Persons (
    Personid int NOT NULL AUTO_INCREMENT,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (Personid)
);
```

To let the AUTO_INCREMENT sequence start with another value, use the following SQL statement:

```sql
ALTER TABLE Persons AUTO_INCREMENT=100;
```

## 2.14 Date Data Types

![Alt text](image-57.png)

## 2.14 create view

- A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

- You can add SQL statements and functions to a view and present the data as if the data were coming from one single table.

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

```sql
CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

example

```sql
CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```
