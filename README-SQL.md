# SQL
SQL stands for **Structured Query Language**. It is used for the retrieval and management of data in a relational database.
## Application of SQL
SQL is one of the most widely used query languages.
Here is the list of the application:-
1. It allows the user to create and drop databases as well as tables.
2. It allows the user to embed with other programming languages using some libraries.
3. It allows the user to describe the data.
4. It allows the user to set permissions on tables.

[Know more about SQL](https://www.javatpoint.com/sql-tutorial )

## Types of SQL Commands
There are five types of SQL commands. Here we will discuss only three which is widely used:-
**1. DDL Commands**:- DDL stands for **Data Definition Language**. It is used to create and change the structure of the table.
Here are some DDL commands:- 
1. CREATE 
2. ALTER
3. DROP
4. TRUNCATE

**1. CREATE**:- It is used to create a new table in the database.
Syntax of `CREATE` command:-
`CREATE TABLE TABLE_NAME (COLUMN_1 DATATYPE, COLUN_2 DATATYPE,...);`

Let's take an example:-
`CREATE TABLE STUDENT(Roll_No INT, Name VARCHAR(20), DOB DATE);`

Table will look like:- 
|Roll_No|Name|DOB|
|--- |---  |--- |
|    |     |    |

[Know more about `CREATE` Command](https://www.javatpoint.com/sql-create-table)

**2. DROP**:- It is used to drop/delete the table with the structure and the records.

Syntax of `DROP` Comand:- 
`DROP TABLE TABLE_NAME;`

Let's take an example:- 
`DROP TABLE STUDENT;`

[Know more about `DROP` Command](https://www.javatpoint.com/sql-drop-table)

**3. ALTER**:- It is used to modify the structure of the database. It can be used to modify the characteristics of an existing attribute or add a new attribute.

Syntax of `ALTER` command:- 

Add a new column in the table:-
`ALTER TABLE TABLE_NAME ADD NEW_COLUMN COLUMN_DEFINITION;`

Let's take an example:-
`ALTER TABLE STUDENT ADD Contact_No VARCHAR(13);`

[Know more about `ALTER` Command](https://www.javatpoint.com/sql-alter-table)

**4. TRUNCATE**:- It is used to delete all the rows from a table.

Syntax of `TRUNCATE` command:- 
`TRUNCATE TABLE TABLE_NAME;`

Let's take an example:-

`TRUNCATE TABLE STUDENT;`

**2. DML Commands**:- DML stands for **Data Manipulation Language**.
These commands are used to insert/modify the records in the database.
Here are some DML commands:- 
1. INSERT
2. UPDATE
3. DELETE


**1. INSERT**:- It is used to insert a new row with data in the table.
Syntax of `INSERT` Command is:
`INSERT INTO TABLE_NAME(COLUMN_1, COLUMN_2,...) VALUES (VALUE_1, VALUE_2,...);`

Let's take a example:-
`INSERT INTO TABLE_NAME(Roll_No Name,DOB) VALUES (18, "Arnav","1976-01-09");`

Now table will be like:- 
|Roll_No|Name|DOB|
|--- |---  |--- |
|  18  |  Arnav   |  1976-01-09  |

[Know more about `INSERT` query...](https://www.javatpoint.com/sql-insert)


**2. UPDATE**:- It is used to update the value in the column in databases.
Syntax of `UPDATE` Command is:
`UPDATE TABLE_NAME SET[COLUMN_1 = NEW_VALUE_1, COLUMN_2 = NEW_VALUE_2, ...] [WHERE CONDITION];`

Let's take a example:-
`UPDATE STUDENT SET  Name = "Arnav Goswami" WHERE Roll_No = 18;`

Now table will be like:- 
|Roll_No|Name|DOB|
|--- |---  |--- |
| 18 |Arnav Goswami | 1976-01-09  |

[Know more about `UPDATE` query](https://www.javatpoint.com/sql-update)

**3. DELETE**:- It is used to delete one or more rows in the table.
Syntax of `DELETE` query is:
`DELETE FROM TABLE_NAME [WHERE CONDITION];`

Let's take an example:-
`DELETE FROM STUDENT WHERE Roll_No = 18;`

Now table will be like:- 
|Roll_No|Name|DOB|
|--- |---  |--- |
|    |     |    |

[Know more about `DELETE` query](https://www.javatpoint.com/sql-delete)

**3. DQL Command**:- DQL stands for **Data Query Language**. It is used to retrieve data from the database.

It uses only one query give below:-
**1. SELECT**:- `SELECT` is used to fetch a row or more row from the database.

Syntax for `SELECT` Query:- 

`SELECT * FROM TABLE_NAME;`


for example:-
`SELECT * FROM STUDENT;`

Now you can see the output will be like:-
|Roll_No|Name|DOB|
|--- |---  |--- |
| 18 |Arnav Goswami | 1976-01-09  |
| 19 |Alok Singh | 1977-05-02  |

Note:- The * (asterisk) is used to fetch all the data from tables.

Let's say you have multiple rows in your STUDENT table, and you want to access only one row from that table. Then you can consider `WHERE` clause in your query.
Syntax for `SELECT` with `WHERE` clause:-
`SELECT * FROM TABLE_NAME [WHERE CONDITION];`

for example:-
`SELECT * FROM STUDENT WHERE Roll_No = 18;`

Now you can see the output will be like:-
|Roll_No|Name|DOB|
|--- |---  |--- |
| 18 |Arnav Goswami | 1976-01-09  |

You can remove * with one or more column names which one you want to access. 

for example:-

`SELECT Name FROM STUDENT WHERE Roll_No = 18;`

Now you can see the output like:-
|Name|
|--- |
|Arnav Goswami |

[Know more about `SELECT` query](https://www.javatpoint.com/sql-select)

Here we read about the basic concept of SQL.
Now let's move to some advanced concepts of SQL.

# Advance SQL
## SQL JOIN

JOIN is used to combine the records from more than one table. It is used with the `SELECT` command when fetching the record from more than one table.

Let's take a look following two tables:-
**Table 1-** STUDENT Table
|Roll_No|Name|DOB|
|--- |---  |--- |
| 18 |Arnav Goswami | 1976-01-09  |
| 19 |Alok Singh | 1977-05-02  |
| 20 |Animesh Sharma | 1991-05-04  |
| 21 |Mandeep Singh | 1989-04-08  |

**Table 1-** STUDENT_LIB Table
|LID|Date|S_Roll_No| Status |
|--- |---  |--- |--- |
| 01 |2021/05/06 | 18  |Book1 issued   | 
| 02 |2021/06/05| 18  | Book1 submitted|
| 03 |2021/05/08 | 19 | Book2 issued   |
| 04 |2021/06/12 | 21 | Book3 issued   |

Now let's JOIN two tables with `SELECT` operation and see what happens:-

`SELECT Roll_No, NAME, Status
   FROM STUDENT, STUDENT_LIB
   WHERE  STUDENT.Roll_No = STUDENT_LIB.S_Roll_No;`

It will produce the following output:-
|Roll_No|Name|Status|
|--- |---  |--- |
| 18 |Arnav Goswami | Book1 issued  |
| 18 |Arnav Goswami | Book1 submitted  |
| 19 |Alok Singh | Book2 issued |
| 21 |Mandeep Singh | Book3 issued  |


Note:- You can also use <, >, <= ,>=, != operators with the `WHERE` clause based on condition.

**Types of JOINs:-**
**1. INNER JOIN:-** INNER JOIN used to return only those rows which are matches in both tables.

The syntax for INNER JOIN:-
>SELECT TABLE1.COLUMN1, TABLE2.COLUMN2, ...
FROM TABLE1
INNER JOIN TABLE2
ON TABLE1.COMMON_FIELD = TABLE2.COMMON_FIELD;

[Know more about INNER JOIN query](https://www.tutorialspoint.com/sql/sql-inner-joins.htm)

**2. RIGHT JOIN:-** RIGHT JOIN is used to return all the rows from the right table even if there are no matches in the left table.
Syntax for RIGHT JOIN:-
>SELECT TABLE1.COLUMN1, TABLE2.COLUMN2, ...
FROM TABLE1
RIGHT JOIN TABLE2
ON TABLE1.COMMON_FIELD = TABLE2.COMMON_FIELD;

[Know more about INNER JOIN](https://www.tutorialspoint.com/sql/sql-right-joins.htm)

**3. LEFT JOIN:-** LEFT JOIN is used to return all the rows from the left table even if there are no matches in the right table.

Syntax for LEFT JOIN:-
>SELECT TABLE1.COLUMN1, TABLE2.COLUMN2, ...
FROM TABLE1
LEFT JOIN TABLE2
ON TABLE1.COMMON_FIELD = TABLE2.COMMON_FIELD;

[Know more about LEFT JOIN](https://www.tutorialspoint.com/sql/sql-left-joins.htm)

**4. FULL JOIN:-** FULL JOIN is used to returns the rows when there is a match in one of the tables.

The syntax for FULL JOIN:-
>SELECT TABLE1.COLUMN1, TABLE2.COLUMN2, ...
FROM TABLE1
FULL JOIN TABLE2
ON TABLE1.COMMON_FIELD = TABLE2.COMMON_FIELD;

[Know more about FULL JOIN](https://www.tutorialspoint.com/sql/sql-full-joins.htm)

## SQL Aggregate Functions

SQL aggregation function is used to perform the calculations on multiple rows on a single column of a table. It returns a single value. It can also use to summarize the data.

**Types of SQL Aggregation Function**
![Image](https://static.javatpoint.com/dbms/images/dbms-sql-aggregate-functio.png "image")
 
**1. COUNT Function:-**
COUNT is used to count the number of rows in a table.
This function can work on both numeric and non-numeric data types.

Syntax for COUNT function:-
>COUNT(*) 
or  
COUNT( [ALL|DISTINCT] expression ) 

Let's create the sample table STUDENT:
Roll_No|Name|Fee|
|--- |--- |---|
| 18 |Arnav Goswami  | 2000|
| 19 |Alok Singh  |1400|
| 20 |Animesh Sharma| |1200|
| 21 |Mandeep Singh   |1800|
| 22 | Sachin | 1500|

Example:- COUNT()
`SELECT COUNT(*) FROM STUDENT;`  

It will produce the following output:-
`5`

Example:- COUNT with WHERE
`SELECT COUNT(*) FROM STUDENT WHERE Roll_no >= 18 and Roll_no <= 20;` 

It will produce the following output:-
`3`

[Know more about `COUNT()` function](https://www.javatpoint.com/dbms-sql-aggregate-function#:~:text=SQL%20Aggregate%20Functions,used%20to%20summarize%20the%20data.)

**2. SUM Function:_**
SUM function is used to calculate the sum of all selected columns.
It works on numeric fields only.

Syntax for SUM function:-
>SUM() 
or  
SUM( [ALL|DISTINCT] expression ) 
Example:- SUM()
`SELECT SUM(Fee) FROM STUDENT;`

It will produce the following output:-
`7900`

Example:- SUM() with WHERE
`SELECT SUM(Fee) FROM STUDENT WHERE Fee > 1200;`

It will produce the following output:-
`6700`

[Know more about `SUM()` function](https://www.javatpoint.com/dbms-sql-aggregate-function#:~:text=SQL%20Aggregate%20Functions,used%20to%20summarize%20the%20data.)

**3. AVG Function:-**
This function is used to calculate the average value of the numeric type. It works only on all numeric types.
The syntax for AVG function:-
>AVG()  
or  
AVG( [ALL|DISTINCT] expression)  

Example:- 
`SELECT AVG(Fee) FROM STUDENT;` 

It will produce the following output:-
`1580.00`

**4. MAX Function:-**
This function is used to find the max value of a specified column.
This is used to find largest value of all selected values.
Syntax for MAX function:-
> MAX()  
or  
MAX( [ALL|DISTINCT] expression)

Example:- 
`SELECT MAX(Fee) FROM STUDENT;` 

It will produce the following output:-
`2000`

**3. MIN Function:-**
This function is used to find the minimum value of a specified column. This function finds the smallest value of a specified column.
Syntax for MIN function:-
>MIN()  
or  
MIN( [ALL|DISTINCT] expression) 

Example:-
>SELECT MIN(Fee)  
FROM STUDENT;  

It will produce the following output:-
`1200`




