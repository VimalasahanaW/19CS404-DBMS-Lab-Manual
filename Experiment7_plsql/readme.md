# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.
## PROGRAM:
```
DECLARE
    num1 NUMBER := 50;
    num2 NUMBER := 80;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
/
```
**Expected Output:**  
Greater number is: 80
## OUTPUT:
<img width="1006" height="641" alt="image" src="https://github.com/user-attachments/assets/d186b31e-67db-4758-abfd-52292e313900" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
## PROGRAM:
```
DECLARE
    n   NUMBER := 10;
    i   NUMBER := 1;
    sum NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```
**Expected Output:**  
Sum of first 10 natural numbers is: 55
## OUTPUT:
<img width="1019" height="656" alt="image" src="https://github.com/user-attachments/assets/9acd1340-1682-4c56-bc0f-6a1da6f30526" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
## PROGRAM:
```
DECLARE
    n NUMBER := 7;       
    a NUMBER := 0;       
    b NUMBER := 1;       
    c NUMBER;            
    i NUMBER := 3;       
    result VARCHAR2(1000);
BEGIN
   
    result := TO_CHAR(a) || ', ' || TO_CHAR(b);
    
    
    WHILE i <= n LOOP
        c := a + b;
        result := result || ', ' || TO_CHAR(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence: ' || result);
END;
/
```
**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8
## OUTPUT:
<img width="1012" height="628" alt="image" src="https://github.com/user-attachments/assets/5e91ed7c-1ae4-46ff-a574-cab7291fbbf9" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
## PROGRAM:
```
DECLARE
    n NUMBER := 1535;
    rev NUMBER := 0;
    rem NUMBER;
    temp NUMBER;
BEGIN
    temp := n;  
    
    WHILE temp > 0 LOOP
        rem := MOD(temp, 10);         
        rev := (rev * 10) + rem;       
        temp := FLOOR(temp / 10);      
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/
```
**Expected Output:**  
n = 1535  
Reversed number is 5351
## OUTPUT:
<img width="1016" height="630" alt="image" src="https://github.com/user-attachments/assets/9d165e75-2492-4adb-ac70-9a4940665584" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
## PROGRAM:
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF (a >= b) AND (a >= c) THEN
        largest := a;
    ELSIF (b >= a) AND (b >= c) THEN
        largest := b;
    ELSE
        largest := c;
    END IF;

    DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
/
```
**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15
## OUTPUT:
<img width="1023" height="651" alt="image" src="https://github.com/user-attachments/assets/ed836baf-3ea3-464c-bd8a-86e4990994fc" />

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.

