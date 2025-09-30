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
```sql
Create TABLE orders (
id INT NOT NULL,
order_number INT,
customer_id INT,
product_id INT,
PRIMARY KEY (id),
FOREIGN KEY (customer_id) REFERENCES customers(id),
FOREIGN KEY (product_id) REFERENCES products(id)
)
