# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

## Common Table:
```
-- EXPERIMENT 5: SUBQUERIES AND VIEWS

-- COMMON TABLE

CREATE TABLE employees (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    department VARCHAR2(50),
    salary NUMBER
);

INSERT INTO employees VALUES (101, 'Arun', 'IT', 50000);
INSERT INTO employees VALUES (102, 'Bala', 'HR', 30000);
INSERT INTO employees VALUES (103, 'Charan', 'IT', 60000);
INSERT INTO employees VALUES (104, 'Divya', 'HR', 40000);
INSERT INTO employees VALUES (105, 'Esha', 'Finance', 45000);

COMMIT;
```
## Output:
<img width="991" height="401" alt="image" src="https://github.com/user-attachments/assets/3b11df88-9f63-409a-8975-7670617473c4" />

**Question 1**
```
SELECT *
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

**Output:**
<img width="970" height="322" alt="image" src="https://github.com/user-attachments/assets/47837cbe-9761-4c70-9c2e-43399e958ec7" />

**Question 2**
```
CREATE TABLE employees (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    department VARCHAR2(50),
    salary NUMBER
);
```

**Output:**
<img width="1032" height="402" alt="image" src="https://github.com/user-attachments/assets/64f79b08-61cb-4e7c-9cc0-e2313ac7670c" />

**Question 3**
```
SELECT *
FROM employees
WHERE department IN (
    SELECT department
    FROM employees
    WHERE salary > 40000
);
```

**Output:**
<img width="1043" height="417" alt="image" src="https://github.com/user-attachments/assets/d076ad59-ee22-40c9-9744-6370f01f332e" />

**Question 4**
```
SELECT *
FROM employees
WHERE salary > ANY (
    SELECT salary
    FROM employees
    WHERE department = 'HR'
);
```


**Output:**
<img width="942" height="422" alt="image" src="https://github.com/user-attachments/assets/c0d50264-b3c7-4463-87d8-d6ac4e53a30a" />

**Question 5**
```
SELECT *
FROM employees
WHERE salary > ALL (
    SELECT salary
    FROM employees
    WHERE department = 'HR'
);
```

**Output:**
<img width="1105" height="412" alt="image" src="https://github.com/user-attachments/assets/262a9f3b-02f7-41b5-a109-794ce6d952e4" />

**Question 6**
```
SELECT e.emp_id, e.emp_name, e.department, e.salary
FROM employees e
WHERE e.salary > (
    SELECT AVG(e2.salary)
    FROM employees e2
    WHERE e2.department = e.department
);
```

**Output:**
<img width="1012" height="328" alt="image" src="https://github.com/user-attachments/assets/7f80a0cd-a5e6-423f-86cc-ac6e99fe3f37" />

**Question 7**
```
CREATE VIEW it_employees AS
SELECT emp_id, emp_name, salary
FROM employees
WHERE department = 'IT';

SELECT * FROM it_employees;
```


**Output:**

<img width="965" height="343" alt="image" src="https://github.com/user-attachments/assets/31ffa7a7-4045-4206-bfa6-4d38bc12b6ad" />

**Question 8**
```
CREATE VIEW high_salary_employees AS
SELECT emp_id, emp_name, department, salary
FROM employees
WHERE salary > 40000;

SELECT * FROM high_salary_employees;

```

**Output:**

<img width="992" height="465" alt="image" src="https://github.com/user-attachments/assets/02f89daf-b04c-49a1-b792-637dd546fc34" />

**Question 9**
```
CREATE VIEW department_avg_salary AS
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department;

SELECT * FROM department_avg_salary;

```

**Output:**

<img width="877" height="345" alt="image" src="https://github.com/user-attachments/assets/f3a86ec3-7dc5-4063-afad-1ee2784675b0" />

**Question 10**
```
DROP VIEW high_salary_employees;
```

**Output:**

<img width="937" height="390" alt="image" src="https://github.com/user-attachments/assets/9e4d59db-9338-4242-ae8f-04ba695f1aef" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
