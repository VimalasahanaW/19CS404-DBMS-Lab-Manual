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
Write a SQL query to Delete All Doctors with a NULL Last Name

Sample table: Doctors

attributes : doctor_id, first_name, last_name, specialization

```sql
delete from Doctors
where  last_name is NULL;
```

**Output:**

<img width="1429" height="700" alt="image" src="https://github.com/user-attachments/assets/86a76ebd-290c-4426-bff2-67e5ef67ca5c" />


**Question 6**
---
Write a SQL query to delete a specific doctor from Doctors table whose ID is 1.

Sample table: Doctors

attributes : doctor_id, first_name, last_name, specialization

```sql
delete from Doctors
where doctor_id = 1;
```

**Output:**

<img width="1142" height="298" alt="image" src="https://github.com/user-attachments/assets/022d4f9f-607f-40aa-bb69-3a1223dfce70" />


**Question 7**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is greater than or equal to 2.

```sql
delete from Customer
where GRADE >= 2;
```

**Output:**

<img width="651" height="566" alt="image" src="https://github.com/user-attachments/assets/d681249a-891a-4175-af41-3c603bd93ba9" />


**Question 8**
---
Write a SQL query to locate the details of customers with grade values above 100. Return customer_id, cust_name, city, grade, and salesman_id.



```sql
select customer_id, cust_name, city, grade,salesman_id
from customer
where grade > 100;
```

**Output:**

<img width="1378" height="520" alt="image" src="https://github.com/user-attachments/assets/5cb87d7b-6890-4571-ab3f-bd5072091cf3" />


**Question 9**
---
Write a SQL query to Select all patients who were admitted during the year 2023.

```sql
select patient_id , first_name , admission_date
from Patients
where admission_date BETWEEN '2023-01-01' AND '2023-12-31';
```

**Output:**

<img width="997" height="443" alt="image" src="https://github.com/user-attachments/assets/3af6cc75-c149-4d84-9a03-e8976296ebd8" />


**Question 10**
---
write a SQL query to create a union of two queries that shows the customer id, cities, and ratings of all customers. Those with a rating of 300 or greater will have the words 'High Rating', while the others will have the words 'Low Rating'.

```sql
SELECT customer_id,city,grade,'High Rating'
as Rating
from customer
where grade >= 300

union

SELECT customer_id,city,grade,'Low Rating'
as Rating
from customer
where grade < 300;
```

**Output:**

<img width="1078" height="545" alt="image" src="https://github.com/user-attachments/assets/73dd5590-2b4b-4243-be49-289616437f51" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
