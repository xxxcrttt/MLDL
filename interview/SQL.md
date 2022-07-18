## Q1. RDBMS -- Relational Database Management System
A RDMS refers to the software used to store, manage and query data. Data is stored in tabels and can be linked to other datasets
based on shared information, hence the name 'relational'.     
关系数据库的管理系统 -- 一个 DBMS，基于关系模型

### Popular RDBMS
```Oracle database, MySQL, Microsoft SQL Server, IBM DB2, SQLite```

### vs. DBMS
1. RDBMS stores data in a relational table with rows and columns, while DBMS stores data as a file.
2. RDBMS provides access to multiple users (including client-server side interaction), whereas a DBMS only supports single user. 

## Q2. SQL 
SQL is a programming language to perform data-related tasks; every RDBMS uses SQL as it standard programming laguage.    
SQL allows users to create tables, update data, make queries, and perform analytics. 

### vs. MySQL 
1. SQL is the programming language used in RDBMS. 
2. MySQL is an example of an RDBMS, it is one of the most first open-source DBMS. 

### Create a table with SQL 
```CREATE TABLE```: table name, column names, types of data, copies of existing tables, 
### Insert dates with SQL 
```DATE``` datatype is used to store data or time values in the DB, generally format is 'YYYY-MM-DD'.

## Q3. Query? 
A query is a request for data or information from a database.   
1. **Select query** is a query that groups data from a table for analytic purposes.   
```SELECT, FROM, WHERE```
2. **Action query** is a query that changes the contents of the database based on specified criteria.    
```UPDATE, DELETE, CREATE TABLE, INSERT INTO```

### perform a select query 
1. **SELECT**: to specify the columns you want to query
2. **FROM**: to specify the particular table holding the data 
3. **WHERE**: to filter data based on specified conditions. 

#### subquery
A subquery is a query that is embedded within another statement that requires multiple steps.    
The subquery provides the enclosing query with additional information needed to execute a task, 
such as when the completion of one query depends firstly on the results of another. 

type: 
1. **single-row sub**: return 1 row in results
2. **multi-row sub**: return 2 or more rows 
3. **correlated sub**: return results according to outer queries 



## Q4.Constraints 约束
SQL constraints are a set of rules or conditions implemented on an RDBMS to specify what data can be inserted, updated, or deleted in its table.     
This is done to maintain data integrity and ensure that the information stored in database is accurate. 

### Important constraints 
1. **NOT NULL**: ensures a column cannot contain a NULL value 
2. **UNIQUE**: ensures all values in a column are different 
3. **DEFAULT**: provides a default value for a column when none is specified 
4. **INDEX**: creates an index for data retrieval purposes 
5. **CHECK**: checks values in a column against certain specified conditions 

 
## Q5. JOIN clauses 
The join clause combines columns with related values from 2 or more tables to create a new table. 
1. **JOIN**: return records with matching values in both tables. 
2. **LEFT JOIN**: return all records from the left table and matching records from the right table 
3. **RIGHT JOIN**: return all .... the right table and ....
4. **FULL JOIN**: returns all records from both tables 

<img src='https://user-images.githubusercontent.com/56160038/179553422-a2445f80-2955-4687-bb42-af7b0a20ee05.png' width='300' align=centre/>

## Q6. index 
An SQL index stores important parts of a database table to allow for a quick and efficient lookup.    
Rather than searching the entire database, users only have to consult the index during data retrieval. 

### create an index with SQL
It varies depending on the RDBMS. Can use```CREATE INDEX``` to initiate the process. 

### clustered vs. non-clustered indexes
1. Clustered indexes define the physical order in which tables are stored and sort them accordingly,      
   Non-clustered indexed create a logical order that doesn't match the physical order of the rows on the disk.
2. C sort data rows based on their key values, N use a structured seperate from the data rows. 
3. There can be only one C index pertable, but can be multiple N per table.
 
## Q7. NULL 
A NULL value indicates the data is unknown. ==> means no data is stored at all. 

## Q8. SQL commands
1. **DDL**: data definition language -- change the structure of the database
2. **DML**: data manipulation language -- modify data in database tables
3. **DCL**: data control language -- mange user access to the database
4. **TCL**: transaction control language -- manage transactions made by DML commands
5. **DQL**: data query language -- retrieve information from the database

## Q9. alias
Aliases are temporary names given to tables or columns for the duration of a particular SQL query.    
Their purpose is to reduce the amount of code required for the query, saving time and effors. 

## Q10. normalization vs. denormalization 
1. **Normalization**: the process of dividing data into tables to remove redundant data and improve data integrity
2. **Denormalization**: used to combine multiple tables in order to reduce the time required to perform queries. 

### types of normalization 
1. *1st Normal Form*: ensure rows and columns always contain singular, unique values
2. *2nd NF*: remove all partial dependencies
3. *3rd NF*: remove all transitive functional dependencies
4. *4th / Boyce-Codd NF*: ensure all functions dependencies are a super key to the table 
5. *5th NF*: ensure decomposition doesn’t result in any loss of data
6. *6th NF*: decompose the relation variables into irreducible components

## Q11. cursor 光标
The cursor allows users to process data from a result set, one row at a time.

Cursors are an alternative to commands, which operate on all rows in a result set at the same time. 

## Q12. Collation Sensitivity 敏感性
Collation refers to a set of rules or conditions that influence how data is stored and ordered. 
1. **Case**: Uppercase & lowercase characrers. 
2. **Accent**: accented & unaccented
3. **Width**: full-width & half-width 

## Q13. how to select EVEN / ODD numbers in a table? 
MOD function can be used in most RDBMS as part of the **WHERE** in a select query.

```MOD(column name, 2) = 1/0```

## Q14. how to rename a column in SQL?
1. use ```ALTER TABLE name``` to select the table with the column to change 
2. use ```RENAME COLUMN old TO new``` to rename the column 

## Q15. DELETE vs. TRUNCATE 
1. **DELETE**: a DML command, removes records and recods each deletion in the transaction log,
2. **TRUNCATE**: a DDL command, deallocates pages and records each deallocation in the transaction log; it is generally considered quicker as it makes less use of the transaction log. 

## Q16. how to copy data from one table to another? 
1. use ```INSERT INTO``` and specify the destination as the *new table*
2. use ```SELECT``` to specify the columns to copy 
3. use ```WHERE``` to specify the table you want to copy

## Q17. how to delete a column? 
1. ```ALTER TABLE name``` to select the table with the column want to delete 
2. ```DROP COLUMN name``` 

## Q18. aggregate function 
Aggregate functions are used to perform calculations on a set of values to return a single value. 

```AVG, COUNT, MIN, MAX, SUM```

## Q19. schema
A schema refers to a collection of database objects -- tables, functions, indexes, and procedures -- associated with a databse. 

The schema helps segragate database objects for different applications and access rights; 

## Q20. scalar function 
Scalar functions are user-defined functions applied to a set of data to return a single value. 

```UCASE, LCASE, MID, ROUND, NOW```

## Q21. SQL injections
An SQL injection is a type of cyber attack in which hackers insert malicious SQL code into the database to gain access to potentially valuable or sensitive information -- for web applications that use an SQL-based database.   

It's possible to prevent SQL injections by creating multiple database accounts to limit access or by using a 3rd-party web aaplication firewall. 

## Q22. how can SQL queries be optimized? 
* Specify particular columns with *SELECT* rather than *SELECT**
* Make joins with *INNER JOIN* rather than *WHERE*
* Define filters using *WHERE* rather than *HAVING*
* Avoid looping statements in the query structure 
* Avoid correlated subqueries 

## Q23. ACID properties 
ACID: Atomicity, Consistency, Isolation, Durability 
* **Atomicity**: Changes to data are performed as a single, unified operation
* **Consistency**: Data values are consistent at the start and end of the transaction
* **Isolation**: The intermediate state of a transaction is hidden from other transactions
* **Durability**: Changes to data remain the same after the transaction is completed




