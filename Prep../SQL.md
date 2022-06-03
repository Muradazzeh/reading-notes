## This is the SQL Reading part with the solved exercises
* Ex 1 
    * SELECT queries : To retrieve data from a SQL database, we need to write **SELECT** statements,

![link](./sql%20image/ex1%20a.png)

* Ex2 : Queries with constraints: we can use condation to retrive spacific data .**WHERE**

![link](./sql%20image/ex2.png)

* Ex3
    * Queries with constraints : When writing WHERE clauses with columns containing text data, SQL supports a number of useful operators to do things like case-insensitive string comparison like **(<,>,!=,=,%)**

![link](./sql%20image/ex3.png)

* Ex 4 :  Filtering and sorting Query results : provides a convenient way to discard rows that have a duplicate column value by using the **DISTINCT** keyword.

![link](./sql%20image/ex4.png)

* Ex 5 : Simple SELECT Queries : 
* SELECT column,
* FROM mytable
* WHERE condition(s)
* ORDER BY column ASC/DESC
* LIMIT num_limit OFFSET num_offset;

![link](./sql%20image/ex5.png)

* Ex 6  : Multi-table queries with JOINs . Using the JOIN clause in a query, we can combine row data across two separate tables using this unique key. The first of the **joins** that we will introduce is the **INNER JOIN**

![link](./sql%20image/ex6.png)

* Ex 7: OUTER JOINs : If the two tables have asymmetric data, which can easily happen when data is entered in different stages, then we would have to use a **LEFT JOIN**, **RIGHT JOIN** or **FULL JOIN** instead to ensure that the data you need is not left out of the result

![link](./sql%20image/ex7.png)

* Ex 8:  A short note on NULLs. In these cases, you can test a column for **NULL** values in a WHERE clause by using either the **IS NULL** or IS **NOT NULL** constraint

![link](./sql%20image/ex8.png)

* Ex9: Queries with expressions : can also use expressions to write more complex logic on column values in a query , like to make callculation and selecting the result from tabel

![link](./sql%20image/ex9.png)

* Ex 10 : Queries with aggregates 1:  that allow you to summarize information about a group of rows of data

![link](./sql%20image/ex10.png)

* Ex 11: Queries with aggregates 2 :  SQL allows us to do this by adding an additional **HAVING**clause which is used specifically with the **GROUP** BY clause to allow us to filter grouped rows from the result set.


![link](./sql%20image/ex11.png)

* Ex 12 : Order of execution of a Query
    1. FROM and JOINs
    2. WHERE 
    3. GROUP BY
    4. HAVING
    5. SELECT
    6. DISTINCT
    7. ORDER BY
    8. LIMIT / OFFSET

![link](./sql%20image/ex12.png)

* Ex 13 : Inserting rows :When inserting data into a database, we need to use an **INSERT** statement, which declares which table to write into, the columns of data that we are filling, and one or more rows of data to insert.

![link](./sql%20image/ex13.png)

* Ex 14 : Updating rows adding new data, a common task is to update existing data, which can be done using an **UPDATE** statement

![link](./sql%20image/ex14.png)

* Ex 15 Deleting rows : When you need to delete data from a table in the database, you can use a **DELETE** statement, which describes the table to act on, and the rows of the table to delete through the **WHERE** clause

![link](./sql%20image/ex15.png)

* Ex 16 :Creating tables : hen you have new entities and relationships to store in your database, you can create a new database table using the **CREATE TABLE** statement
    * **CREATE TABLE IF NOT EXISTS mytable** (
   
);

![link](./sql%20image/ex16.png)

* Ex 17 : Altering tables : As your data changes over time, SQL provides a way for you to update your corresponding tables and database schemas by using the **ALTER TABLE** statement to add, remove, or modify columns and table constraints

![link](./sql%20image/ex17.png)

* Ex 18:Dropping tables you may want to remove an entire table including all of its data and metadata, and to do so, you can use the **DROP TABLE** statement, which differs from the DELETE statement in that it also removes the table schema from the database entirely
    * **DROP TABLE IF EXISTS**

![link](./sql%20image/ex18.png)
