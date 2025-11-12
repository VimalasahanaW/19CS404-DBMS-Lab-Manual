# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Write a SQL statement to Update the address to '58 Lakeview, Magnolia' where supplier ID is 5 in the suppliers table.

Suppliers Table 

|name     |          type|
|---------|  -------------|
|supplier_id |       INT|
|supplier_name  |    VARCHAR(100)|
|contact_person |    VARCHAR(100)|
|phone_number   |    VARCHAR(20)|
|email    |          VARCHAR(100)|
|address   |         VARCHAR(250)|

```sql
update Suppliers
set address = '58 Lakeview, Magnolia'
where supplier_id = 5;
```

**Output:**

<img width="1853" height="334" alt="image" src="https://github.com/user-attachments/assets/0e618207-1345-4e82-bbbf-88f53976b1a9" />


**Question 2**
---
Write a SQL statement to Change the category to 'Household' where product name contains 'Detergent' in the products table.

## Products Table :

|name      |    type  |     
|----------|   --------|
|product_id   |  INT PRIMARY KEY |       
|product_name |  VARCHAR(10) |
|category   |    VARCHAR(50) |
|cost_price  |   DECIMAL(10) |
|sell_price   |  DECIMAL(10) |
|reorder_lvl  |  INT   |     
|quantity     |  INT   |     
|supplier_id   | INT  |        
```sql
update Products
set category = 'Household'
where product_name like '%Detergent%';
```

**Output:**

<img width="1797" height="400" alt="image" src="https://github.com/user-attachments/assets/7f49910c-e11a-40b2-a5a4-2ebe8677f8dd" />


**Question 3**
---
Write a SQL statement to Increase the selling price per unit by 5% for product ID 15 who's sale is on '2023-01-31'.

sales(sale_id,sale_date,product_id,quantity,sell_price,total_sell_price)
```sql
update sales
set sell_price = sell_price * 1.05
where product_id = 15 and sale_date = '2023-01-31';

```

**Output:**

<img width="1746" height="465" alt="image" src="https://github.com/user-attachments/assets/67bcc16d-1702-4a37-940f-0b82e6f9dcbb" />

**Question 4**
---
Write a SQL statement to change the email column of employees table with 'Unavailable' for all employees in employees table.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id
```sql
update Employees
set email = 'Unavailable';
```

**Output:**

<img width="1355" height="459" alt="image" src="https://github.com/user-attachments/assets/2c508718-81eb-44e5-997f-16a5bb05bf9c" />


**Question 5**
---
-- Paste Question 5 here

```sql
-- Paste your SQL code below for Question 5
```

**Output:**

![Output5](output.png)

**Question 6**
---
-- Paste Question 6 here

```sql
-- Paste your SQL code below for Question 6
```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Paste Question 7 here

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

![Output10](output.png)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
