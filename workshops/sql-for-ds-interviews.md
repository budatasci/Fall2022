# SQL for Data Science Interviews 

Table of Contents
* [What is SQL](#what-is-sql)
* [Workshop Description](#workshop-description)
* [Requirements](#requirements)
* [Excercises](#exercises) 

## What is SQL?
SQL is short for Structure Query Language. It is a language used to query data from a database. 

## Workshop Description
In this workshop, you will learn how run basic SQL commands. The database we will be using for our examples has the folllowing schema:

| Tablename | Records| 
| :-----: | :---: | 
| Customers| 91 | 
| Categories | 8 | 
| Employees | 10 |
| OrderDetails | 518 |  
| Orders | 196 |
| Products | 77 |
| Shippers | 3 |
| Suppliers | 29 |

## Commands

INSERT: a way to insert data into a table

    INSERT INTO table_name (column_1, column_2, column_3)
    VALUES (value_1, 'value_2', value_3)


UPDATE: to update a record in a table, use the UPDATE statement. You can use UPDATE to change existing records. The syntax is:

    UPDATE table_name
    SET column1 = value1,
        column2 = value2, ...
    WHERE condition;

Example:

    UPDATE Person
    SET Name = "Elton John"
    WHERE Id = 4;


DELETE: used to delete a record in a table. 

Be careful! You can delete all records of the table or just a few. Use the WHERE condition to specify which records you want to delete. The syntax is:

    DELETE FROM table_name
    WHERE condition;

Example:


    DELETE FROM Person
    WHERE Id = 3;


## Requirements 
* To run the following SQL commands and to practice for your upcoming interview go [here](https://www.stratascratch.com/).

## Exercises 
### SELECT 
1. Select all rows from the table `Customers`

    ```
    SELECT * FROM Customers;
    ```

2. Select the columns `CustomerName`, `City` from  `Customers`

    ```
    SELECT CustomerName, City FROM Customers;
    ```

### UPDATE
1. Update the `City` column of all records in the `Customers` table.
    ```
    UPDATE Customers
    SET City = 'Oslo';
    ```

### DELETE
1. Delete all the records from the `Customers` table where the Country value is `Norway`.
    ```
    DELETE FROM Customers
    WHERE Country = 'Norway';'
    ```


### WHERE 
Used to filter records

1. Return all the names of customers who live in France

    ```
    SELECT CustomerName FROM Customers WHERE Country='France';
    ```

### Additional Practice Questions
