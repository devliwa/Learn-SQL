# Learn-SQL-CRUD

#### SQL Commands: CREATE table and INSERT Data
- [W3Schools on SQL](https://www.w3schools.com/sql/)
- [SQL Playground on sqliteonline.com](https://sqliteonline.com/#fiddle-5bbdbaef7288bo2ajn2wly03)
- [Data Types in SQL](https://www.w3schools.com/sql/sql_datatypes.asp)
- [Primary Keys in SQL](https://www.w3schools.com/sql/sql_primarykey.asp)
- [Completed Lesson SQL Demo Code](https://www.mycompiler.io/view/08q0XDT7TFp)
create table
```sql
CREATE TABLE products (
id INT NOT NULL,
name STRING,
price MONEY,
PRIMARY KEY (id)
)
```
insert data
```sql
INSERT INTO products VALUES (1, 'Pen', 1.20)
```
```sql
INSERT INTO products (id, name) VALUES (2, 'pencil')
```

#### SQL Commands: READ, SELECT, and WHERE
read data
```sql
SELECT * FROM 'products';
```
select data
```sql
SELECT name, price FROM 'products';
```
where data
```sql
SELECT * FROM products WHERE id=1
```

#### Updating Single Values and Adding Columns in SQL
update single value
```sql
UPDATE products SET price = 0.80 WHERE id=2
```
adding column
```sql
ALTER TABLE products ADD stock INT
```

#### SQL Commands: DELETE
delete
```sql
DELETE FROM products WHERE id = 2
```

#### Understanding SQL Relationships, Foreign Keys and Inner Joins 
- [Foreign Keys in SQL](https://www.w3schools.com/sql/sql_foreignkey.asp)
- [Inner Joins](https://www.w3schools.com/sql/sql_join_inner.asp)
- [Completed SQL demo Project](https://www.mycompiler.io/view/7ZK5EPwt68f

-- create customers table
```sql
CREATE TABLE customers (
  id INT,
  first_name STRING,
  last_name STRING,
  address STRING,
  PRIMARY KEY (id)
);
```

-- insert some values
```sql
INSERT INTO customers VALUES (1, 'John', 'Doe', '32 Cherry Blvd');
INSERT INTO customers VALUES (2, 'charles', 'liwa', '12 Sunset Drive');
-- fetch some values
SELECT * FROM customers WHERE first_name = 'John';
```

-- create the products table
```sql
CREATE TABLE products (
    id INT NOT NULL,
    name STRING,
    price MONEY,
    PRIMARY KEY (id)
);
```

--insert a product into products table
```sql
INSERT INTO products VALUES (1, 'Pen', 1.20);
```
-- select a product with id = 1
```sql
SELECT * FROM products WHERE id = 1;
```
--insert a product with no price into products table
```sql
INSERT INTO products (id, name) VALUES (2, 'Pencil');
```
--select a product with id = 2
```sql
SELECT * FROM products WHERE id = 2;
```
--update a row in products table
```sql
UPDATE products SET price=0.8 WHERE id = 2;
```
--select all records from products table
```sql
SELECT * FROM products;
```
--add a new column - stock to the products table
```sql
ALTER TABLE products ADD stock INT;
```
--update a row in products table
```sql
UPDATE products SET stock=32 WHERE id = 1;
```
--select all records from products table
```sql
SELECT * FROM products;
```
--update a row in products table
```sql
UPDATE products SET stock=12 WHERE id = 2;
```
--select all records from products table
```sql
SELECT * FROM products;
```
--delete a row from products table
```sql
DELETE FROM products WHERE id = 2;
```
--insert back the deleted row into products table
```sql
INSERT INTO products VALUES (2, 'Pencil', 0.8, 12);
```
-- create the orders table
```sql
CREATE TABLE orders (
  id INT NOT NULL,
  order_number INT,
  customer_id INT,
  product_id INT,
  PRIMARY KEY (id),
  FOREIGN KEY (customer_id) REFERENCES customers(id),
  FOREIGN KEY (product_id) REFERENCES products(id)
);
```
--insert an order into orders table
```sql
INSERT INTO orders VALUES (1, 4362, 2, 1);
```
--join orders and customers table
```sql
SELECT orders.order_number, customers.first_name, customers.last_name, customers.address
FROM orders
INNER JOIN customers ON orders.customer_id = customers.id;
```
--join orders and products table
```sql
SELECT orders.order_number, products.name, products.price, products.stock
FROM orders
INNER JOIN products ON product_id = products.id;
```
