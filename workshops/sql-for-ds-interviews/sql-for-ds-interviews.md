# SQL for Data Science Interviews 

Table of Contents
* [What is SQL?](#what-is-sql)
* [Workshop Description](#workshop-description)
* [Requirements](#requirements)
* [Excercises](#exercises) 
* [Practice Problems](#practice-problems)
* [Additional Commands](#additional-commands)
* [Additional Resources](#additional-resources)

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
* To run the following SQL commands and to practice for your upcoming interview go [here](https://www.w3schools.com/sql/trysql.asp?filename=trysql_asc).

## Exercises 
### `SELECT` 

1. Select all records from the table `Customers`

    ```
    SELECT * FROM Customers;
    ```

2. Select the records in columns `CustomerName`, `City` from  `Customers`

    ```
    SELECT CustomerName, City FROM Customers;
    ```

### Aggregate Functions (`COUNT`, `AVG`, `SUM`)

3. Return the total number of products

    ```
    SELECT COUNT(*) FROM Products;
    ```

4. Return the average price of products

    ```
    SELECT AVG(Price) FROM Products;
    ```
    **Tip: You can round to 2 decimal places by using the ROUND() function.**

    ```
    SELECT ROUND(AVG(Price),2) FROM Products;
    ```

5. Return the total price of products

    ```
    SELECT SUM(Price) FROM Products;
    ```

### `WHERE `
WHERE is used to filter columns based on certain conditions

 6. Return all the names of customers who live in France

    ```
    SELECT CustomerName FROM Customers WHERE Country='France';
    ```

### `GROUP BY`
A GROUP BY clause allows us to 
  group together tuples that have a common value and apply an aggregate function to the tuples in each subgroup 
  
7. What is the average quantity for each `ORDERID` in `OrderDetails`?
    ```
    SELECT ORDERID, AVG(Quantity) FROM OrderDetails GROUP BY ORDERID;
    ```
    **Tip: NULLs will be grouped together if your GROUP BY column contains NULLS**

### `HAVING`
The HAVING clause was added to SQL because the WHERE clause cannot be used to filter for groups or aggregate functions. 

**Key Idea: `WHERE` filters before data is grouped, `HAVING` filters after data is grouped**

8. Which countries in `Customers` have more than 10 customers? 

    ```
    SELECT COUNT(CustomerID), Country FROM Customers GROUP BY Country
    HAVING COUNT(CustomerID) < 10;
    ```

### Sorting with `ORDER BY`

The ORDER BY clause allows us to sort data by particular columns 

9. Select all records from `Suppliers` in ascending alphabetical order

    ```
    SELECT * FROM Suppliers ORDER BY City;
    ```

10. What about if we add `DESC` in the end? Try it! And also sort more than one columns?

    ```
    SELECT * FROM Suppliers ORDER BY Country, City DESC;
    ```

    **Tip: `ORDER BY` must always be the last clause in a `SELECT` statement**
    ```
    SELECT * 
    FROM Suppliers 
    WHERE SupplierID < 10
    ORDER BY City;
    ```

### Sorting by Column Index 
Alternatively, we can order by the column index. In SQL, the column index begins at 1.

11. So if we wanted to select all records from  `Suppliers`, ordered by ascending contact name, we would run the following command since `ContactName` is the third columm in our table.

    ```
    SELECT * 
    FROM Suppliers 
    ORDER BY 3;
    ```

### `LIKE and Wildcard`
LIKE is a special operator used with the WHERE clause to search for a specific pattern in a column. It is used in conjuction with 2 wildcards:

* The  `_` wildcard is used to match with one single character 

* The `%` wildcard is used to match with unspecified number characters


12. Select all the records of customers that begin with `C`

    ```
    SELECT * FROM Customers WHERE CustomerName LIKE 'C%';
    ```

13. Return all the records of customers that begin with `C` and end with `a`

    ```
    SELECT * FROM Customers WHERE CustomerName LIKE 'C%a';
    ```
14. Select all the records where postal codes that have an `2` in the second position

    ```
    SELECT * FROM Customers WHERE PostalCode LIKE '_2%';
    ```

### Joining Tables
The basic syntax for combining two or more tables is:

```  
SELECT <column(s)> FROM TABLE_A JOIN TABLE_B ON TABLE_A.KEY = TABLE_B.KEY;
```

### `INNER JOIN` 
INNER JOIN the default JOIN clause and it will join two or more tables based on matching column values 

![](/workshops/sql-for-ds-interviews/img/inner-join.png)

15. Return the order ID and customer name after joining `ORDERS` and `Customers`\

    ```
    SELECT Orders.OrderID, Customers.CustomerName FROM Orders INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
    ```

### `LEFT JOIN`

A LEFT JOIN will keep all the records from the first table and only include matching records from the second table

![](/workshops/sql-for-ds-interviews/img/left-join.png)

16. Try replacing the INNER JOIN in the previous command with LEFT JOIN and compare the differences

### `RIGHT JOIN`

A RIGHT JOIN will keep all the records from the second table and only include matching records from the first table

![](/workshops/sql-for-ds-interviews/img/right-join.png)

## Practice Problems

1. How many total orders have Speedy Express shipped?
2. Which employee has completed the most orders? How many?
3. What product is most bought (quantity-wise) by Germany? How many?
4. Which product is most ORDERED by Germany? How many?

## Additional Commands

### `INSERT`
A command to insert data into a table

    INSERT INTO table_name (column_1, column_2, column_3)
    VALUES (value_1, 'value_2', value_3);
        

### `UPDATE`
To update a record in a table, use the `UPDATE` statement. You can use UPDATE to change existing records. The syntax is:

    UPDATE table_name 
    SET column1 = value1,
    column2 = value2, ...
    WHERE condition;

### `DELETE`
A command used to delete a record in a table. 

**Be careful! You can delete all records of the table or just a few. Use the WHERE condition to specify which records you want to delete. The syntax is:**

    DELETE FROM table_name
    WHERE condition;

Example:

    DELETE FROM Person
    WHERE Id = 3;

## Additional Resources
* [SQL Data Types](http://www.cs.toronto.edu/~nn/csc309/guide/pointbase/docs/html/htmlfiles/dev_datatypesandconversionsFIN.html)
* [Entity Relationship Diagrams (ERDs)](https://medium.com/codex/entity-relationship-diagrams-4e3c827edf46)
* [Interview Questions](https://platform.stratascratch.com/technical)

