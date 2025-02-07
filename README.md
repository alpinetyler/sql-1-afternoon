<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250" align="right">

# Project Summary

In this project we will be practicing inserting and querying data using SQL. We'll make use of a handy online tool provided by DevMountain that will allow us to write SQL in your browser. [Click Me](https://postgres.devmountain.com/)

On the left are the Tables with their fields, the right is where we will be writing our queries, and the bottom is where we will see our results.  

Any new tables or records that we add into the database will be removed after you refresh the page.

## Table - person

### Instructions
1. Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color. 
    * id should be an auto-incrementing id/primary key - Use type: SERIAL
2. Add 5 different people into the person database. 
    * Remember to not include the person_id because it should auto-increment.
3. List all the people in the person table by height from tallest to shortest.
4. List all the people in the person table by height from shortest to tallest.
5. List all the people in the person table by age from oldest to youngest.
6. List all the people in the person table older than age 20.
7. List all the people in the person table that are exactly 18.
8. List all the people in the person table that are less than 20 and older than 30.
9. List all the people in the person table that are not 27 (Use not equals).
10. List all the people in the person table where their favorite color is not red.
11. List all the people in the person table where their favorite color is not red and is not blue.
12. List all the people in the person table where their favorite color is orange or green.
13. List all the people in the person table where their favorite color is orange, green or blue (use IN).
14. List all the people in the person table where their favorite color is yellow or purple (use IN).

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>

CREATE TABLE person(
  id SERIAL,
  name VARCHAR,
  age INTEGER,
  height INTEGE,
  city VARCHAR,
  favorite_color VARCHAR
  );
  

```sql
CREATE TABLE person ( person_id SERIAL, name VARCHAR(200), age INTEGER, height INTEGER, city VARCHAR(200), favorite_color VARCHAR(200) );
```

</details>

<details>

<summary> <code> #2 </code> </summary>
INSERT INTO person(
  name,
  age,
  height,
  city,
  favorite_color
  )
  VALUES('Jim Smith', 45, 180, 'Provo', 'red'),
  VALUES('Abe Jensen', 33, 190, 'Alpine', 'blue'),
  VALUES('Jane Doe', 38, 165, 'Midway', 'blue'),
  VALUES('Mary Jones', 53, 160, 'Lindon', 'green'),
  VALUES('Phillip Jensen', 33, 188, 'Provo', 'purple');


```sql
INSERT INTO person ( name, age, height, city, favorite_color ) VALUES ( 'First Last', 21, 182, 'City', 'Color' );
```

</details>

<details>

<summary> <code> #3 </code> </summary>
SELECT * FROM person 
ORDER BY height DESC;

```sql
SELECT * FROM person ORDER BY height DESC;
```

</details>

<details>

<summary> <code> #4 </code> </summary>
SELECT * FROM person 
ORDER BY height ASC;

```sql
SELECT * FROM person ORDER BY height ASC;
```

</details>

<details>

<summary> <code> #5 </code> </summary>
SELECT * FROM person 
ORDER BY age DESC;

```sql
SELECT * FROM person ORDER BY age DESC;
```

</details>

<details>

<summary> <code> #6 </code> </summary>
SELECT * FROM person 
WHERE age > 20;

```sql
SELECT * FROM person WHERE age > 20;
```

</details>

<details>

<summary> <code> #7 </code> </summary>
SELECT * FROM person 
WHERE age = 18;

```sql
SELECT * FROM person WHERE age = 18;
```

</details>

<details>

<summary> <code> #8 </code> </summary>
SELECT * FROM person 
WHERE age < 20 OR
age > 30;

```sql
SELECT * FROM person WHERE age < 20 OR age > 30;
```

</details>

<details>

<summary> <code> #9 </code> </summary>
SELECT * FROM person 
WHERE age != 27;

```sql
SELECT * FROM person WHERE age != 27;
```

</details>

<details>

<summary> <code> #10 </code> </summary>
SELECT * FROM person 
WHERE favorite_color != 'red';

```sql
SELECT * FROM person WHERE favorite_color != 'red';
```

</details>

<details>

<summary> <code> #11 </code> </summary>
SELECT * FROM person 
WHERE favorite_color != 'red' AND
favorite_color != 'blue';

```sql
SELECT * FROM person WHERE favorite_color != 'red' AND favorite_color != 'blue';
```

</details>

<details>

<summary> <code> #12 </code> </summary>
SELECT * FROM person 
WHERE favorite_color = 'orange' OR
favorite_color = 'green';

```sql
SELECT * FROM person WHERE favorite_color = 'orange' OR favorite_color = 'green';
```

</details>

<details>

<summary> <code> #13 </code> </summary>
SELECT * FROM person 
WHERE favorite_color IN('orange', 'green','blue');

```sql
SELECT * FROM person WHERE favorite_color IN ( 'orange', 'green', 'blue' );
```

</details>

<details>

<summary> <code> #14 </code> </summary>
SELECT * FROM person 
WHERE favorite_color IN ('yellow', 'purple');

```sql
SELECT * FROM person WHERE favorite_color IN ( 'yellow', 'purple' )
```

</details>

</details>

## Table - orders

### Instructions

1. Create a table called orders that records: person_id, product_name, product_price, quantity.
2. Add 5 orders to the orders table.
    * Make orders for at least two different people.
    * person_id should be different for different people.
3. Select all the records from the orders table.
4. Calculate the total number of products ordered.
5. Calculate the total order price.
6. Calculate the total order price by a single person_id.

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>
CREATE TABLE orders(
  person_id SERIAL,
  product_name VARCHAR,
  product_PRICE DECIMAL,
  quantity INTEGER);

```sql
CREATE TABLE orders ( person_id SERIAL, product_name VARCHAR(200), product_price NUMERIC, quantity INTEGER );
```

</details>

<details>

<summary> <code> #2 </code> </summary>
INSERT INTO orders(
  person_id,
  product_name,
  product_PRICE,
  quantity)
  VALUES
  (1, 'sandbox', 14.99, 3),
  (2, 'shovel', 8.00, 1),
  (3, 'hose', 5.00, 2),
  (2, 'saw', 21, 1),
  (4, 'screwdriver', 6.00, 1);

```sql
INSERT INTO orders ( person_id, product_name, product_price, quantity ) VALUES ( 0, 'Product', 12.50, 2 );
```

</details>

<details>

<summary> <code> #3 </code> </summary>
SELECT * FROM orders;

```sql
SELECT * FROM orders;
```

</details>

<details>

<summary> <code> #4 </code> </summary>
SELECT SUM(quantity)
FROM orders;

```sql
SELECT SUM(quantity) FROM orders;
```

</details>

<details>

<summary> <code> #5 </code> </summary>
select Sum(product_price * quantity) from orders;


```sql
SELECT SUM(product_price * quantity) FROM orders;
```

</details>

<details>

<summary> <code> #6 </code> </summary>
select Sum(product_price * quantity) from orders
WHERE person_id = 1;

```sql
/* The value of person_id depends on what IDs you used. Use a valid ID from your table */
SELECT SUM(product_price * quantity) FROM orders WHERE person_id = 0;
```

</details>

</details>

## Table - artist

### Instructions

1. Add 3 new artists to the artist table. ( It's already created )
2. Select 10 artists in reverse alphabetical order.
3. Select 5 artists in alphabetical order.
4. Select all artists that start with the word 'Black'.
5. Select all artists that contain the word 'Black'.

### Solution 

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>
INSERT INTO artist(name)
VALUES
('Billy Joel'),
('Earth Wind & Fire'),
('Falco');

```sql
INSERT INTO artist ( name ) VALUES ( 'artist name' );
```

</details>

<details>

<summary> <code> #2 </code> </summary>
SELECT * FROM artist 
ORDER BY name DESC
LIMIT 10;

```sql
SELECT * FROM artist ORDER BY name DESC LIMIT 10;
```

</details>

<details>

<summary> <code> #3 </code> </summary>
SELECT * FROM artist 
ORDER BY name ASC
LIMIT 5;

```sql
SELECT * FROM artist ORDER BY name ASC LIMIT 5;
```

</details>

<details>

<summary> <code> #4 </code> </summary>
SELECT * FROM artist 
WHERE name LIKE 'Black%';

```sql
SELECT * FROM artist WHERE name LIKE 'Black%';
```

</details>

<details>

<summary> <code> #5 </code> </summary>
SELECT * FROM artist 
WHERE name LIKE '%Black%';

```sql
SELECT * FROM artist WHERE name LIKE '%Black%';
```

</details>

</details>

## Table - employee

### Instructions

1. List all employee first and last names only that live in Calgary.
2. Find the birthdate for the youngest employee.
3. Find the birthdate for the oldest employee.
4. Find everyone that reports to Nancy Edwards (Use the ReportsTo column).
   * You will need to query the employee table to find the Id for Nancy Edwards
5. Count how many people live in Lethbridge.

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>
SELECT first_name, last_name FROM
employee WHERE city = 'Calgary';

```sql
SELECT first_name, last_name FROM employee WHERE city = 'Calgary';
```

</details>

<details>

<summary> <code> #2 </code> </summary>
SELECT max(birth_date) FROM employee


```sql
SELECT MAX(birth_date) from employee;
```

</details>

<details>

<summary> <code> #3 </code> </summary>
SELECT min(birth_date) FROM employee
f

```sql
SELECT MIN(birth_date) from employee;
```

</details>

<details>

<summary> <code> #4 </code> </summary>
SELECT * FROM employee
WHERE first_name = 'Nancy' AND
last_name = 'Edwards'

SELECT * FROM employee
WHERE reports_to = 2


```sql
SELECT * FROM employee WHERE reports_to = 2;
```

</details>

<details>

<summary> <code> #5 </code> </summary>
SELECT COUNT(*) FROM employee
WHERE city = 'Lethbridge'

```sql
SELECT COUNT(*) FROM employee WHERE city = 'Lethbridge';
```

</details>

</details>

## Table - invoice 

### Instructions

1. Count how many orders were made from the USA.
2. Find the largest order total amount.
3. Find the smallest order total amount.
4. Find all orders bigger than $5.
5. Count how many orders were smaller than $5.
6. Count how many orders were in CA, TX, or AZ (use IN).
7. Get the average total of the orders.
8. Get the total sum of the orders.

### Solution

<details>

<summary> <code> SQL Solutions </code> </summary>

<details>

<summary> <code> #1 </code> </summary>
SELECT COUNT(*) FROM invoice
WHERE billing_country = 'USA'

```sql
SELECT COUNT(*) FROM invoice WHERE billing_country = 'USA';
```

</details>

<details>

<summary> <code> #2 </code> </summary>
SELECT MAX(total) from invoice


```sql
SELECT MAX(total) FROM invoice;
```

</details>

<details>

<summary> <code> #3 </code> </summary>
SELECT MIN(total) from invoice

```sql
SELECT MIN(total) FROM invoice;
```

</details>

<details>

<summary> <code> #4 </code> </summary>
SELECT * FROM invoice
WHERE total > 5

```sql
SELECT * FROM invoice WHERE total > 5;
```

</details>

<details>

<summary> <code> #5 </code> </summary>
SELECT COUNT(*) FROM invoice
WHERE total < 5

```sql
SELECT COUNT(*) FROM invoice WHERE total < 5;
```

</details>

<details>

<summary> <code> #6 </code> </summary>
SELECT COUNT(*) FROM invoice
WHERE billing_state IN('CA', 'TX', 'AZ')

```sql
SELECT COUNT(*) FROM invoice WHERE billing_state in ('CA', 'TX', 'AZ');
```

</details>

<details>

<summary> <code> #7 </code> </summary>
SELECT AVG(total) FROM
invoice

```sql
SELECT AVG(total) FROM invoice;
```

</details>

<details>

<summary> <code> #8 </code> </summary>
SELECT SUM(total) FROM
invoice

```sql
SELECT SUM(total) FROM invoice;
```

</details>

</details>


## Resources

<details>

<summary> <code> SQL </code> </summary>

* [SQL Teaching](http://www.sqlteaching.com/)
* [SQL Bolt](http://sqlbolt.com/)

</details>

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2017. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250">
</p>

