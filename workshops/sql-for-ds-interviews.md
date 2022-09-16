# SQL for Data Science Interviews 

Table of Contents
* [What is SQL](#what-is-sql)
* [Workshop Description](#workshop-description)
* [Requirements](#requirements)
* [Excercises](#exercises) 

## What is SQL?
SQL is short for Structure Query Language. It is a language used to grab data from a database. 

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


### WHERE 
Used to filter records

1. Return all the names of customers who live in France

    ```
    SELECT CustomerName FROM Customers WHERE Country='France';
    ```

### Additional Practice Questions

1. How many total orders have Speedy Express shipped?
2. Which employee has completed the most orders? How many?
3. What product is most bought (quantity-wise) by Germany? How many?
4. Which product is most ORDERED by Germany? How many?







