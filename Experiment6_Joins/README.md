# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

## Question 1:

Display employee names along with their department names using INNER JOIN.

```
SELECT employees.employee_name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

## Output:


<img width="950" height="386" alt="image" src="https://github.com/user-attachments/assets/9f5794a8-0c5b-4862-9242-4b1204ed8c33" />


## Question 2:

Display all employees along with their department names using LEFT JOIN.

```
SELECT employees.employee_name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

## Output:


<img width="967" height="402" alt="image" src="https://github.com/user-attachments/assets/159b364d-3943-4e4b-8d52-c84b91c1afc6" />


## Question 3:
Display all departments along with the employees working in them using RIGHT JOIN.

```
SELECT employees.employee_name, departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```


## Output:


<img width="940" height="382" alt="image" src="https://github.com/user-attachments/assets/1d610801-f2fa-4ad6-8473-6b255f501deb" />


## Question 4:

Display all employees and departments using FULL OUTER JOIN.

```
SELECT employees.employee_name, departments.department_name
FROM employees
FULL OUTER JOIN departments
ON employees.department_id = departments.department_id;
```

## Output:


<img width="941" height="455" alt="image" src="https://github.com/user-attachments/assets/04f8a803-0425-4272-a38d-8ff1029131a9" />


## Question 5:

Display employee names, department names, and salaries using INNER JOIN.

```
SELECT employees.employee_name,
       departments.department_name,
       employees.salary
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

## Output:


<img width="956" height="448" alt="image" src="https://github.com/user-attachments/assets/4aa64350-f464-468d-95fd-abc7273b160e" />


## Question 6:

Display employees who are assigned to a department.

```
SELECT employees.employee_name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```
## Output:


<img width="977" height="432" alt="image" src="https://github.com/user-attachments/assets/8b97fe04-e8c6-4c97-809c-86641ab5a655" />


## Question 7:

Display all employees, including employees who are not assigned to any department

```
SELECT employees.employee_name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

## Output:


<img width="922" height="441" alt="image" src="https://github.com/user-attachments/assets/d4699d21-53fa-4558-a551-e21de6a4268b" />


## Question 8:

Display all departments, including departments that have no employees.

```
SELECT departments.department_name, employees.employee_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```

## Output:


<img width="931" height="437" alt="image" src="https://github.com/user-attachments/assets/bf09c66f-2f13-4288-a007-158069b7d8b4" />


## Question 9:

Display the employee name, department name, and salary for employees earning more than 50,000.

```
SELECT employees.employee_name,
       departments.department_name,
       employees.salary
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id
WHERE employees.salary > 50000;
```

## Output:


<img width="885" height="385" alt="image" src="https://github.com/user-attachments/assets/dfe76b01-41d0-40ad-bb47-9a2d626c8ca5" />


## Question 10:
Display the number of employees in each department using JOIN and GROUP BY.

```
SELECT departments.department_name,
       COUNT(employees.employee_id) AS employee_count
FROM departments
LEFT JOIN employees
ON departments.department_id = employees.department_id
GROUP BY departments.department_name;
```

## Output:


<img width="942" height="421" alt="image" src="https://github.com/user-attachments/assets/dd7e604c-1af8-426a-913f-5fc7686de9bf" />



## RESULT:
Thus, the SQL queries to implement different types of joins have been executed successfully.
