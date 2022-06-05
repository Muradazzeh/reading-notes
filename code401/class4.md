## SQL vs NoSQL Database Differences 
* sql : Structured Query Language thats  data stored as tables 
* Nosql: not only Structured Query Language : thats the data stored as object key value , graphs , documents ..etc

### SQL vs NoSQL: High-Level Differences

| SQL         | NOSQL |
| ----------- | ----------- |
|   databases are primarily called as Relational Databases (RDBMS)  |   database are primarily called as non-relational or distributed database   |
|  databases are table based databases   | databases are document based, key-value pairs, graph databases or wide-column stores        |
|          SQL databases have predefined schema    |    databases have dynamic schema for unstructured data           |
|     SQL databases are vertically scalable         |                 databases are horizontally scalable            |
|   databases are scaled by increasing the horse-power of the hardware                 |   scaled by increasing the databases servers in the pool of resources to reduce the load                  |
|   databases uses SQL ( structured query language ) for defining and manipulating the data, which is very powerful                   |        ueries are focused on collection of documents                |   
|         database examples: MySql, Oracle, Sqlite, Postgres and MS-SQL              |        MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb                    |   
|    MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb                    |               databases are not good fit for complex queries             |
|          databases are not best fit for hierarchical data storage                        |         database fits better for the hierarchical data storage as it follows the key-value pair way of storing data similar to JSON data              |
|        databases are vertically scalable. You can manage increasing load by increasing the CPU, RAM, SSD, etc, on a single server                      |    NoSQL databases are horizontally scalable. You can just add few more servers easily in your NoSQL database infrastructure to handle the large traffic                        |
|                   databases are best fit for heavy duty transactional type applications              |              transactions purpose, it is still not comparable and sable enough in high load and for complex transactional applications           |
|         Excellent support are available for all SQL database from their vendors               |       database you still have to rely on community support, and only limited outside experts are available for you to setup and deploy your large scale NoSQL deployments                     |
|      databases emphasizes on ACID properties ( Atomicity, Consistency, Isolation and Durability                      |           the Brewers CAP theorem ( Consistency, Availability and Partition tolerance )       |
|          On a high-level, we can classify SQL databases as either open-source or close-sourced from commercial vendors        |     classified on the basis of way of storing data as graph databases, key-value store databases, document store databases              |

### NoSQL Database Examples
1. MongoDB
Mongodb is one of the most popular document based NoSQL database as it stores data in JSON like documents

## Data Modeling Concepts
* is procces of creating a digrame for a software system and and it is data elemnt and table and how it is flow 

![link](./class4imag/Database-Table-Data-Modeling.png)

* Major element of the table is :
    * Table name 
    * primery key 
    * Table Columns 
    * Foreign Key

### Data Modeling – Table Relationships 
| Cardinality           |	    Notation |
|     ----             |       ----       |
| zero or one-to-many	 |       0..*|
| one-to-many	        |       1..*|
| zero or one-to-one    |     0..1|
| one-to-one	            |   1..1|

## Exercises:
What is the difference between one-to-one relationship and a many-to-one relationship?

> * one to one is the way when we connected 2 table , both having one entry  .
> *  many to one when we connected 2 table  , first table having one entry and the other table having many entry.

What is a Foreign Key?  How do you define one?

> foriegn key is the column that match the primery key with the other table.

What is the difference between a primary key and a compound primary key?

> * it is unique identefier for a spacific row in the table.
> * compaound primery key : is primery key but it has more than one column 

## Things I want to know more about class4 reading ?

* in which type of application we will use NOSQL and how we can implement data we get and how to store it .

* I need to try to deeply understand the connection between tables , and how I can do data base modeling . 
* when I have time I need to solve exercises for primery key and foriegn key . 