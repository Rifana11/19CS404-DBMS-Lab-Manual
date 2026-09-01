# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

**Expected Output:**  
Square of 6 is 36

## Query:

```
SET SERVEROUTPUT ON;

CREATE OR REPLACE PROCEDURE find_square(n IN NUMBER)
IS
    square NUMBER;
BEGIN
    square := n * n;

    DBMS_OUTPUT.PUT_LINE('Square of ' || n || ' is ' || square);
END;
/
```
## Output:
<img width="992" height="367" alt="image" src="https://github.com/user-attachments/assets/3e3d61f4-2bcc-4d9b-9440-c0417dbf230f" />


## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**Expected Output:**  
Factorial of 5 is 120
## Query:
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE FUNCTION get_factorial(n IN NUMBER)
RETURN NUMBER
IS
    fact NUMBER := 1;
BEGIN
    FOR i IN 1..n
    LOOP
        fact := fact * i;
    END LOOP;

    RETURN fact;
END;
/
```
## Output:
<img width="1093" height="387" alt="image" src="https://github.com/user-attachments/assets/b64c99f9-e97e-4d3d-966c-f98d3b04ebb5" />


## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
12 is Even

## Query:
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE PROCEDURE check_even_odd(n IN NUMBER)
IS
BEGIN
    IF MOD(n, 2) = 0 THEN
        DBMS_OUTPUT.PUT_LINE(n || ' is Even');
    ELSE
        DBMS_OUTPUT.PUT_LINE(n || ' is Odd');
    END IF;
END;
/
```
 ## Output:
<img width="1060" height="387" alt="WhatsApp Image 2026-09-01 at 2 18 17 PM" src="https://github.com/user-attachments/assets/5e636f52-00fb-43f6-891f-f1f1c9e191bb" />


## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**Expected Output:**  
Reversed number of 1234 is 4321

## Query:
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE FUNCTION reverse_number(n IN NUMBER)
RETURN NUMBER
IS
    num NUMBER := n;
    rev NUMBER := 0;
    digit NUMBER;
BEGIN
    WHILE num > 0
    LOOP
        digit := MOD(num, 10);
        rev := rev * 10 + digit;
        num := TRUNC(num / 10);
    END LOOP;

    RETURN rev;
END;
/
```
## Output:
<img width="1055" height="383" alt="image" src="https://github.com/user-attachments/assets/ccc245bd-dee2-40f9-a05c-3c214d87a4d8" />


## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50
## Query:
```
SET SERVEROUTPUT ON;

CREATE OR REPLACE PROCEDURE print_table(n IN NUMBER)
IS
BEGIN
    DBMS_OUTPUT.PUT_LINE('Multiplication table of ' || n || ':');

    FOR i IN 1..10
    LOOP
        DBMS_OUTPUT.PUT_LINE(n || ' x ' || i || ' = ' || (n * i));
    END LOOP;
END;
/
```
**Output:
<img width="925" height="392" alt="image" src="https://github.com/user-attachments/assets/3adb746f-f57e-4cf4-9763-d1853facf73f" />

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
