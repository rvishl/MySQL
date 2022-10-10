## SQL Command Practice

- `SELECT * FROM Customers;`
  - It will select all data from Customers table.
- `SELECT CustomerName, City FROM Customers;`
  - It will select only <CustomerName> and <City> from Customers table.
- `SELECT CustomerName, City FROM Customers WHERE City='Berlin'`;
  - It will be select only those CustomerName and City from customers table who lived in 'Berlin City'.

## What is Database?

- Collection of data.
  - Eg: Phone Book directory.

# SQL

- A method for accessing and manipulation data.

**SQL -> standard -> 1986 -> ANSI (American National Standard Institute)**

- 1987 -> ISO -> (International Organisation for Standardization)

Application -> Business Professional,
Data Scientist,
Developers,
Accountants.

## MySQL vs SQL

- SQL is a language. we use to talk to over databases.
  - SQL Eg: find all users who are 18 or older.
  - MySQL Eg: SELECT \* FROM users WHERE age >= 18;

## Some Popular DataBases:

- MongoDB
- Oracle
- MySQL
- SQLite
- PostgreSQL
- MaxDB
- firebird
- Redis

**SQL is the language we use to "talk" to our databases.**

## Two Takeaways
- Once you learn SQL, it's pretty easy to switch to another DATABASE that uses SQL.
- What makes databases(DBMS) unique are the features they offer, not the language.

##  Goorm-ide

**MySQL-ctl cli;**
- ctl - control transaction durability
- cli - command line interface



## Command
- CREATE DATABASE <DATABASE_NAME>;
  - It is use for creating database;
- SHOW DATABASES;
  - It is use to show existing database;
- DROP DATABASE <DATABASE_NAME>;
  - It is use to delete existing database;
- USE <DATABASE_NAME>;
  - This command to go inside existing database;

- SELECT DATABASE();
  - This command is to show in which database using now.

- CREATE TABLE <tablename> (
  column_name data_type,
  column_name data_type
);
  - This command is used to create table in database;

- SHOW tables;
  - This command is used to show all the tables in the database;

- DESC <table_name>;
  - This command is used to show to description/summary of that table.

- DROP table <table_name>;
  - This command is used to delete whole specific table.

- SHOW columns FROM <table_name>;
  - It is similar to DESC Command;

- INSERT INTO <table_name> (<columns>, <columns>) VALUES (<columns_values>, <columns_value>);
  - This command is used to insert data into table.

- SELECT * FROM <table_name>;
  - This command is used to show the data from table.

- INSERT INTO <table_name>(<columns>, <columns>) VALUES(<columns_values>, <columns_values>), (<columns_values>, <columns_values>), (<columns_values>, <columns_values>), (<columns_values>, <columns_values>);
  - This is for multiple insertion.


- Example:
  CREATE TABLE employees (
    emp_id int not null PRIMARY KEY AUTO_INCREMENT,
    first_name varchar(50) not null,
    last_name varchar(50) not null,
    middle_name varchar(50),
    age int not null,
    current_status varchar(100) not null default 'employed' 
  );

- ALTER TABLE <table_name> CHANGE <old_column_name> <new_column_name> <column_defination>;
  - This command is used to change table columns name and defination as well.
  - Eg- ALTER TABLE employees CHANGE current_status current_status varchar(100) not nul default 'employed';\

- ALTER TABLE <table_name> RENAME COLUMN <old_column_name> TO <new_column_name>;
  - This command is used to only rename the column name of table;
  - Eg - ALTER TABLE employees RENAME COLUMN 'current_status' TO 'status';

- ALTER TABLE <table_name> MODIFY <column_name> <new_definition>;
  - This command is used to modify the column difinition but not its name.
  - Eg - ALTER TABLE employees MODIFY middle_name varchar(50) not null;


**L1 - completed**

## L2

- SELECT * FROM <table_name>;
  - Eg: SELECT * FROM employees;
  - It will show all data from employees table.

- SELECT <column_name> , <column_name> FROM cats;
  - Eg: SELECT name, age FROM employees;
  - It will show data from emplyees table which we want.

- SELECT * FROM <table_name> WHERE <specific_case>;
  - Eg: SELECT * FROM employee WHERE age=32;
  - It will show all data from employee where age is 32.

## Introduction to alias
- 'as'
  SELECT <colummn_name> as <New_column_name>, <colummn_name> as <New_column_name> FROM <table_name>; 
  - Eg:
      - SELECT name as 'Employee name', current_status as 'status', age FROM cats;
      - It will not change or rename the the actual database but it show the data as per we want to read.

## Update Command
- `update` `set` `where`

- UPDATE <table_name> SET <column_name> = <'new_name'> WHERE <column_name> = <'column_name'>;
  - Eg: `UPDATE employee SET current_status = 'developer' WHERE current_status = 'software engineer';`
  - `UPDATE employee SET age = 24 WHERE name = 'vishal raj';`


## DELETE COMMAND
- It will use to delete permanenet, it can not be rollback.
- `DELETE` `WHERE`
  - DELETE FROM <tabel_name> WHERE <column_name> = <'column_name'>;
  - Eg: `DELTE FROM employee WHERE name = 'Vishal Raj';`


# String Function

## CONCAT
- `SELECT CONCAT(<column_name>, ' ' , <column_name>) as <'Given_name'> FROM <table_name>;`
  - Eg:  `SELECT title, CONCAT(author_fname, " " , author_lname) AS 'author full_name' FROM books;`
  - It will show the data after merge of two colunms but it will not affected or changing the actual databases.
  - `SELECT CONCAT(author_fname, ' ' , author_lname) as 'author full_name' FROM books;`

- `SELECT CONCAT_WS(<'Word_Seperator'>, <column_name>, <column_name> AS <'Given_name'> FROM <table_name>;`
  - Eg: SELECT CONCAT_WS(' - ', title, released_year) AS 'Books Details' FROM books;
  - It will show data with seperated column by 'word_seperator'.


## Substring

- `select substring('Hello World', 1, 4);`
  - Output: Hell
- `select substring('Hello World', 7);`
  - Output: World
- `select substring('Hello World', -3);`
  - Output: rld
- `select substring('Hello World', -7, 4);`
  - Output: o Wo
- `select substr(title, 1, 15) from books;`

## Replace

- `select replace('Hello World', 'World', 'hell');`
  - Output: Hello hell
  - It will replace the word as per your given.
- `select replace(title, 'e', 3) from books;`

## Reverse

- `select reverse('Hello');`
  - Output: olleH
  - It will simply reverse the word.
- `select reverse('nitin');`


# Palindrome
- `select concat('woof', reverse('woof'));`

# Character length
- `select char_length('Hello World');`

# Upper case
- `select upper('hi');`
  - It will show all the character into upper case.

# Lower case
- `select lower('HI');`
  - It will show all the character into lower case

## Selection Refining
- distinct
  - To find Unique values
  - It means show data only once not repeted.
  - Eg: `select distinct author_lname from books;`
- order by
  - It is used to show the data into ascending or descending order.
  - by default it is ascending order.
  - Eg: `select author_lname from books order by author_lname;`
          Output will show the ascending order
        `select released_year from books order by released_year desc;`
          Output will show the descending order
        `select title, author_fname, author,lname from books order by author_lname;`
        `select titile, author_fname, author,lname from books order by 1, 2, 3;`

**L2 completed**



## L3 

- limit
  - This is use to show the limited data by limit keyword
  - Eg: `select title, released_year from books order by released_year desc limit 5;`
  - `select title, released_year, pages from books order by pages desc limit 10;`
- like
  - `select title from books where title like '%stories%';`

  - `select title, page from books order by pages desc limit 1;`

## Aggregate Function
- Count
  - It will count the row from <table>;
  - Eg:
    - `select count(*) from books;`
    - `select count(title) from books;`
    - `select count(distinct author_fname) from books;`

- min & max
  - (min) - It basically give the minimum value of integer.
  - (max) - It basically give the maximum value of integer.
  - Eg: 
    - (min)
    - `select min(released_year) from books;`
    - `select min(pages) from books;`

    - (max)
    - `select max(pages) from books;`
    - `select max(released_year) from books;`

    - SubQuery:
      - `select * from books where pages = (select min(pages) from books);`
      - `select * from books where pages = (select max(pages) from books);`

    - min / max group by
      - Q: find the year each author published therir first book.
        - `select author_fname, author_lname, min(released_year) from books group by author_fname, author_lname;`
        - `select author_fname, author_lname, min(released_year) from books group by 2, 1;`

      - Q: find the longest page count for each author.
        - `select author_fname, author_lname, max(pages) from books group by 1, 2;`
        - `select author_fname, author_lname, max(pages) from books group by author_lname, author_fname;`

    - sum 
      - `select sum(pages) from books;`
      - `select author_fname, author_lname, sum(pages) from books group by 2, 1;`
    
    - average
      - `select avg(pages) from books;`
      - `select author_fname, author_lname, avg(pages) from books group by author_fname, author_lname;`

- Q: Print the number of books in the database.
- `select count(*) from books;`

- Q: Print out how many books where released in each year
- `select count(*) from books group by released_year;`

- Q: Print out the total number of books in stock
- `select sum(stock_quantity) from books;`

- Q: Find the average released year for each author
- `select author_fname, author_lname, avg(released_year) from books group by author_fname, author_lname;`


- Q: Find the full name of the author who wrote the longest book
- `select concat(author_fname, ' ', author_lname), pages from books order by pages desc limit 1;`

- Q: 
- `select released_year as year, count(title) as books, avg(pages) as 'avg pages' from books group by released_year;`


## Logical operators
- Not equal
  - select title from books where released_year = 2017;
  - select title, released_year from books where released_year != 2017;

  - Not like
    - select title from books where title like '%w%';
    - select title from books where title not like '%w%';

- Greather than
  - select title, released_year from books where released_year > 2000 order by released_year;
  - select title, released_year from books where released_year < 2000 order by released_year;

- And ( && )
  - select title, author_lname, released_year from books where author_lname = 'Eggers' and released_year > 2010;

- OR ( || )
  - select title, author_lname, released_year from books where author_lname = 'Eggers' || released_year > 2010;

- Between -> and or not this one &&
  - select title, released_year from books where released_year BETWEEN 2004 and 2015;

- not between
  - select title, released_year from books where released_year not between 2004 and 2015;

- In -> OR || not in -> and 
  - select title, author_lname from books where author_lname = 'Carver' OR author_lname = 'Lahiri' OR author_lname = 'Lahiri' OR author_lname = 'Smith';
  - select title, author_lname from books where author_lname in ('Carver', 'Lahiri', 'Smith'); 


## CASE 
- SELECT title, released_year,
  CASE 
    WHEN released_year >= 2000 THEN 'Modern Lit'
    ELSE '20th Century Lit'
  END AS GENRE
FROM books;
- SELECT title, stock_quantity,
  CASE
    WHEN stock_quantity BETWEEN 0 AND 50 THEN '*'
    WHEN stock_quantity BETWEEN 51 AND 100 THEN '*'
    ELSE '***'
  END AS Stock
FROM books;


- select title, author_lname, 
case
when count(*) = 1 then ' 1 book'
else concat(count(*), ' books')
end as count
from books
group by author_lname;

# L3 completed

# L4 

## Relationship
- Types of relationship
    - one to one
    - one to many
    - many to many

  ### one to one
  - Ex: country - capital city
  - persion - their fingerprints
  - email - user account

  ### one to many
  - Ex: country - city
  - parent - child
  - employee - manager

    ## JOIN 
  - INNER JOIN
    - It will show all the records that have matching values in both tables
    - Eg: `SELECT * from customers inner join orders on orders.customer_id = customers.id;`

  - LEFT JOIN
    - It will show all the records from left table and matched records from the right table. If there is no match for a specific record, you will NULL in the corresponding column of the right table.
    - Eg: `SELECT * FROM orders LEFT JOIN customers ON customers.id = orders.customer_id;`

  - RIGHT JOIN
    - It show all records from the right table and the matching records from the left table. If there is no match for a specific record, you will NULL in the corresponding column of the left table.
    - Eg: `SELECT * FROM  orders RIGHT JOIN customers ON customers.id = orders.customer_id;`
    
    ### many to many

    