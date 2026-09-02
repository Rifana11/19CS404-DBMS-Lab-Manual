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

## Question 1:

Find the minimum salary of all staff members.

```
SELECT MIN(salary) AS minimum_salary
FROM staff;

```

## Output:

<img width="877" height="367" alt="image" src="https://github.com/user-attachments/assets/81e61a6e-840b-4718-8877-9912ede1288a" />


## Question 2:

Find the maximum salary of all staff members.

```
SELECT MAX(salary) AS maximum_salary
FROM staff;

```

## Output:

<img width="875" height="425" alt="image" src="https://github.com/user-attachments/assets/456a7ed9-5602-42df-b391-c0e389293913" />


## Question 3:

Find the total salary of all staff members.

```
SELECT SUM(salary) AS total_salary
FROM staff;

```

## Output:

<img width="898" height="355" alt="image" src="https://github.com/user-attachments/assets/0ce9b96e-9cb2-43ca-bc5f-97fa01fbb033" />


## Question 4:

Find the average salary of all staff members.

```
SELECT AVG(salary) AS average_salary
FROM staff;
```

## Output:

<img width="762" height="412" alt="image" src="https://github.com/user-attachments/assets/5aa14133-4491-4cd0-b5a2-a543b90875a1" />

## Question 5:

Find the total number of staff members.

```
SELECT COUNT(*) AS total_staff
FROM staff;

```

## Output:

<img width="852" height="402" alt="image" src="https://github.com/user-attachments/assets/9ca0af21-c454-44e5-9f13-a04825daa986" />


## Question 6:

Find the number of staff members in each department.


```
SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department;

```

## Output:

<img width="842" height="391" alt="image" src="https://github.com/user-attachments/assets/ee1992b0-f966-4f74-a4fd-4ae80f23802e" />

## Question 7:

Find the total salary paid in each department.

```
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department;

```

## Output:

<img width="882" height="393" alt="image" src="https://github.com/user-attachments/assets/750b4716-9719-43e9-bff4-abf92476b336" />


## Question 8:

Find the average salary in each department.

```
SELECT department, AVG(salary) AS average_salary
FROM staff
GROUP BY department;

```

## Output:

<img width="901" height="355" alt="image" src="https://github.com/user-attachments/assets/07d340a9-e281-4761-8114-1020b69412e7" />

## Question 9:

Display departments having more than 2 staff members.

```
SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department
HAVING COUNT(*) > 2;
```

## Output:

<img width="842" height="367" alt="image" src="https://github.com/user-attachments/assets/8c4e3826-ec03-4e3e-bc8f-5aa77b51e44d" />


## Question 10:

Display departments whose total salary is greater than 150000.

```
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department
HAVING SUM(salary) > 150000;

```

## Output:

<img width="906" height="347" alt="image" src="https://github.com/user-attachments/assets/e43a4f1b-8953-4211-80cb-e7e000b1d200" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
