# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
What is the count of male and female patients?

```sql
select Gender ,
count(*) as  TotalPatients
from Patients group by Gender;
```

**Output:**

<img width="865" height="413" alt="image" src="https://github.com/user-attachments/assets/0f1039c9-2e01-45b6-a6a0-5ce03053d360" />


**Question 2**
---
What is the total number of medications prescribed for each patient?

```sql
select PatientID,
count(*) as TotalMedications
from Prescriptions group by PatientID;
```

**Output:**

<img width="777" height="763" alt="image" src="https://github.com/user-attachments/assets/c6f93bc2-04a1-4d48-a042-e2fa729507ff" />


**Question 3**
---
What is the total number of appointments scheduled by each doctor?

```sql
select DoctorID,
count(*) as TotalAppointments
from Appointments group by DoctorID;
```

**Output:**

<img width="860" height="637" alt="image" src="https://github.com/user-attachments/assets/5da1ec80-0a44-4523-a801-8901e28e23e0" />


**Question 4**
---
Write a SQL query to return the total number of rows in the 'customer' table where the city is Noida.

```sql
select count(*) as COUNT 
FROM  customer
WHERE city = 'Noida';

```

**Output:**

<img width="554" height="371" alt="image" src="https://github.com/user-attachments/assets/d94f393c-d1c3-4c64-ac4a-f69d186095de" />


**Question 5**
---
Write a SQL query to find the total number of unique cities in the customer table?
```sql
SELECT COUNT(DISTINCT city) AS unique_cities
FROM customer;
```

**Output:**

<img width="644" height="362" alt="image" src="https://github.com/user-attachments/assets/12b9b90c-fe65-4f37-8418-fe0249762f16" />


**Question 6**
---
Write a SQL query to find the Fruit with the lowest available quantity.

Note: Inventory attribute contains amount of fruits

```sql
select name as fruit_name, inventory as lowest_quantity
from fruits 
where inventory = (select min(inventory) from fruits);
```

**Output:**

<img width="669" height="366" alt="image" src="https://github.com/user-attachments/assets/2b475b23-59f1-46cb-b4cd-d754fd9c8dce" />


**Question 7**
---
Write a SQL query to calculate total available amount of fruits that has a price greater than 0.5 . Return total Count. 

Note: Inventory attribute contains amount of fruits
```sql
select sum(inventory) as total_available_amount
from fruits 
where price >0.5;
```

**Output:**

<img width="752" height="373" alt="image" src="https://github.com/user-attachments/assets/f2900e8b-6a16-4a86-8f6f-65b9c4d52119" />


**Question 8**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the minimum work hours for each date, and excludes dates where the minimum work hour is not less than 10.
```sql
select jdate, MIN(workhour)
from employee1 group by jdate having min(workhour)  < 10;
```

**Output:**

<img width="816" height="472" alt="image" src="https://github.com/user-attachments/assets/6f764e69-6fd8-496a-84f6-2c8d82e81007" />


**Question 9**
---
Write the SQL query that accomplishes the selection of average price for each category from the "products" table and includes only those products where the average price falls between 10 and 15.
```sql
select category_id, AVG(Price)
from products group by category_id
having avg(price) between 10 and 15;
```

**Output:**

<img width="710" height="390" alt="image" src="https://github.com/user-attachments/assets/1c5cbed3-13db-4ef6-b131-5ee8e177c429" />

**Question 10**
---
Write an SQL query that groups the customer data into 5-year age intervals, calculates the minimum salary for each group, and excludes groups where the minimum salary is not less than 2000.

```sql
SELECT (age/5) * 5 AS age_group ,MIN(salary)
from customer1 group by (age/5) * 5
having MIN(salary)<2000;
```

**Output:**

<img width="689" height="397" alt="image" src="https://github.com/user-attachments/assets/8716298f-3b41-4b24-8bd7-e3e5d2a0463c" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
