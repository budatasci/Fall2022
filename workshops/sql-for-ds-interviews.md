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



## Sorting with ORDER BY

#### ORDER BY clause allows user to sort data by particular columns 

Select all columns from `Suppliers` in ascending alphabetical order
```
SELECT * 
FROM Suppliers 
ORDER BY City;
```

#### What is about if we add DESC in the end? Try it!
```
SELECT * 
FROM Suppliers 
ORDER BY City DESC;
```

#### Tip: ORDER BY must always be the last clause in a select statement
```
SELECT * 
FROM Suppliers 
WHERE SupplierID < 10
ORDER BY City;
```
#### Sorting by Column Position 
```
SELECT * 
FROM Suppliers 
ORDER BY 3;
```
#### * 3 means 3rd column

## Grouping Data

##### GROUP BY
##### HAVING
```
SELECT ContactName FROM Suppliers 
WHERE SupplierID < 10
GROUP BY Country;
```
#### Tip: NULLs will be grouped together if your GROUP BY column contains NULLS

### WHERE vs. HAVING 
#### WHERE does not work for groups, WHERE filters on rows. Instead use HAVING clause to filter for groups.
#### WHERE filters before data is grouped
#### HAVING filters after data is grouped 
#### Rows eliminated by the WHERE clause will not be a included in the gorup 
```
SELECT * 
FROM Products
WHERE SupplierID >= 10
GROUP BY Price
HAVING ProductID BETWEEN 30 and 40;
```


### Additional Practice Questions

1. How many total orders have Speedy Express shipped?
2. Which employee has completed the most orders? How many?
3. What product is most bought (quantity-wise) by Germany? How many?
4. Which product is most ORDERED by Germany? How many?







