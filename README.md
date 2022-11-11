<img align="right" src="https://dataschool.com/assets/images/learn-sql/extras/copyDBs/copyDBs_1.png">

## 🚀 PostgreSQL
PostgreSQL quick start 


## Commands

Database Connection
```bash
  \c [DATABASE NAME]
``` 
Create Database 
```bash
  CREATE DATABASE [DATABASE NAME];
``` 
Delete Database
```bash
  DROP DATABASE [DATABASE NAME];
``` 
Show all databases
```bash
  \l
```
Create Table 
```bash
  CREATE TABLE [table name](column_name BIGSERIAL PRIMARY KEY,
                column_name VARCHAR(50) NOT NULL,
                date_column DATE);
``` 
Show all tables

```bash
  \dt
```
Show table details
```bash
  \d [TABLE NAME]
```
Delete Table
```bash
  DROP TABLE [table name];
```

Database Connection

```bash
  \c [DATABASE NAME]
``` 
Show entries 
- All entries(*)
- Select column

```bash
  SELECT * FROM [table name] ;
  SELECT [column_name] FROM [table name];
  SELECT [column_name, column_name] FROM [table name];
``` 
Show entries in Order - By default Ascending , Descending(DESC)
```bash
  SELECT [column_name] FROM [table name] ORDER BY [table name];
  SELECT [column_name] FROM [table name] ORDER BY [table name] DESC;
``` 
Add entry into Table
```bash
   INSERT INTO [table name] (column, column_date) VALUES('value', DATE '2022-11-22' );
``` 
Upload file 
```bash
   \i [file path];
``` 
Show unique data (no repetitive)
```bash
   SELECT DISTINCT [column_name] FROM [table name];
``` 
Group the Similar Data based on Select column
```bash
    SELECT [column_name] FROM [table name] GROUP BY [column_name];
``` 
Group data with count(how many Similar )
```bash
    SELECT [column_name, count(*)] FROM [table name] GROUP BY [column_name];
``` 
Group data with count(how many Similar ), Also in order
```bash
    SELECT [column_name, count(*)] FROM [table name] GROUP BY [column_name] ORDER BY [column_name];
```
Get group data with count condition
```bash
    SELECT [column_name, count(*)] FROM [table name] GROUP BY [column_name] HAVING count(*) > 5 ;
    SELECT [column_name, count(*)] FROM [table name] GROUP BY [column_name] HAVING count(*) > 5 ORDER BY [column_name];
``` 
Find the row entry by one entry - WHERE
```bash
    SELECT * FROM [table name] WHERE [column_name]='[entry]';
``` 
Delete an entry
```bash
 DELETE FROM [table_name] WHERE [column_name] = [entry];
```
Delete All entries
```bash
 DELETE FROM [table_name];
```
Get multiple entries
```bash
    SELECT * FROM [table name] WHERE [column_name]='[entry]' OR [column_name]='[entry]';
```
Get multiple entries using the Array - IN
```bash
    SELECT * FROM [table name] WHERE [column_name] IN ['entry', 'entry2'];
``` 
Find entries by BETWEEN, for example- the date
```bash
    SELECT * FROM [table name] WHERE [column_name] BETWEEN '[entry]' AND '[entry2]';
```
Find entries with LIKE by related data[word] , 
- % -> no matter how many words
- _  -> one alphanumeric, two(__), and so on
```bash
    SELECT * FROM [table name] WHERE [column_name] LIKE '%[word]%';
    SELECT * FROM [table name] WHERE [column_name] LIKE '___[word]%';
``` 
Find entries with ILIKE - case insensitive 
```bash
    SELECT * FROM [table name] WHERE [column_name] ILIKE '%[word]%';
```
Show data in the limit, like the Above 5 entries
```bash
    SELECT * FROM [table name] LIMIT(5);
```
Show all data except the above 5 entries
```bash
    SELECT * FROM [table name] OFFSET(5);;
```
Show 5 entries except for the above 5 entries
```bash
    SELECT * FROM [table name] LIMIT(5) LIMIT(5);
```
The arithmetic function of PostgreSQL, 
- MIN - minimum value
- MAX - Maximum value
- AVG - average value
- SUM - submission value
- ROUND - Remove decimal
```bash
    SELECT MAX(column_name) FROM [table name] ;
    SELECT MIN(column_name) FROM [table name] ;
    SELECT AVG(column_name) FROM [table name] ;
    SELECT SUM(column_name) FROM [table name] ;
    SELECT ROUND(AVG(column_name)) FROM [table name] ;
```
Group data by arithmetic function
```bash
    SELECT [column_name], MIN(column_name) FROM [table name] GROUP BY [column_name] ;
    SELECT [column_name], MAX(column_name) FROM [table name] GROUP BY [column_name] ;
    SELECT [column_name], AVG(column_name) FROM [table name] GROUP BY [column_name] ;
    SELECT [column_name], SUM(column_name) FROM [table name] GROUP BY [column_name] ;
```
Arithmetic operation (+, - , *, /, %)
```bash
    SELECT 10 + 2 ;
    SELECT 10 - 2 ;
    SELECT 10 * 2 ;
    SELECT 10 / 2 ;
    SELECT 10 % 2 ;
    SELECT 10^2 ;
```
Calculate the percentage, for example - 10% value 
```bash
    SELECT [column_name], column_name * .10 FROM [table name] ;
    SELECT [column_name], ROUND(column_name * .10,2) FROM [table name] ;
```   
Assign the name of the percentage column by AS.
```bash
    SELECT [column_name], ROUND(column_name - ROUND(column_name * .10,2)) FROM [table name] ;
    SELECT [column_name], ROUND(column_name - ROUND(column_name * .10,2)) AS [new column_name] FROM [table name] ;
```
COALESCE - Add default value into empty shell
```bash
    SELECT COALESCE(column_name, 'default value') FROM [table name] ;
```
if we divide any number with zero, shows an error 'division by zero', so uses NULL instead of zero. But the output is not zero, it is empty, use COALESCE to show zero.
```bash
    SELECT COALESCE(number/NUll, 0);
```
NullIF - takes two arguments if both are the same, then the output is null otherwise takes the first argument for the operation
```bash
    SELECT number/NUllIF(0,0);
    SELECT COALESCE(number/NUllIF(0,0), 0);
```
Date and time
```bash
    SELECT NOW();
```
Only Date
```bash
    SELECT NOW()::DATE;
```
Only Time
```bash
    SELECT NOW()::TIME;
```
ADD and Subtract date and time using INTERVAL
```bash
SELECT NOW() - INTERVAL '10 YEAR';
SELECT NOW() - INTERVAL '10 MONTH';
SELECT NOW() - INTERVAL '10 DAY';
SELECT NOW() + INTERVAL '10 YEAR';
```
