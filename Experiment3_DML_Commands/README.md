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
## Commom table 
```
CREATE TABLE Student (
    student_id NUMBER,
    student_name VARCHAR2(30),
    department VARCHAR2(20),
    marks NUMBER
);
```
## Output:
<img width="977" height="358" alt="image" src="https://github.com/user-attachments/assets/f1c3b018-b25d-43e7-aa49-ec4a26c44d80" />

**Question 1**
```
INSERT INTO Student (student_id, student_name, department, marks)
VALUES (101, 'Ravi', 'CSE', 85);

COMMIT;
```

**Output:**

<img width="1078" height="366" alt="image" src="https://github.com/user-attachments/assets/9e500895-7dc9-4291-97a1-8ace5a453dd1" />

**Question 2**
---
```
INSERT ALL
    INTO Student VALUES (102, 'Priya', 'ECE', 78)
    INTO Student VALUES (103, 'Arun', 'CSE', 92)
    INTO Student VALUES (104, 'Meena', 'IT', 88)
SELECT * FROM dual;

COMMIT;
```

**Output:**
<img width="955" height="387" alt="image" src="https://github.com/user-attachments/assets/606b90fd-2e81-48ef-8f6e-67846fe5b7b7" />


**Question 3**
```
SELECT * FROM Student;
```

**Output:**

<img width="1135" height="417" alt="image" src="https://github.com/user-attachments/assets/ce96048d-0242-4403-9ae0-5294657559c4" />

**Question 4**
```
SELECT * FROM Student
WHERE department = 'CSE';
```

**Output:**
<img width="1102" height="433" alt="image" src="https://github.com/user-attachments/assets/0ad7ac2a-7aed-47a1-951c-e8808504419a" />

**Question 5**
```
UPDATE Student
SET marks = 90
WHERE student_id = 101;

COMMIT;
```

**Output:**
<img width="1043" height="381" alt="image" src="https://github.com/user-attachments/assets/dc6986a8-08b9-43db-8ee2-b74fa1086b71" />


**Question 6**
```
UPDATE Student
SET department = 'CSE'
WHERE student_id = 102;

COMMIT;
```

**Output:**
<img width="926" height="381" alt="image" src="https://github.com/user-attachments/assets/831b7c0d-008b-466d-8014-97714e625208" />

**Question 7**
```
DELETE FROM Student
WHERE student_id = 104;

COMMIT;
```

**Output:**
<img width="922" height="392" alt="image" src="https://github.com/user-attachments/assets/63634972-87c2-4432-a47a-8dcf6013e9b3" />


**Question 8**
```
SELECT * FROM Student
WHERE marks > 85;
```

**Output:**
<img width="1027" height="318" alt="image" src="https://github.com/user-attachments/assets/c1efd02b-aa7f-4b1a-bd9a-5b15467af15d" />

**Question 9**
```
CREATE TABLE CSE_Students (
    student_id NUMBER,
    student_name VARCHAR2(30),
    department VARCHAR2(20),
    marks NUMBER
);
INSERT INTO CSE_Students
SELECT * FROM Student
WHERE department = 'CSE';

COMMIT;
SELECT * FROM CSE_Students;
```

**Output:**
<img width="927" height="376" alt="image" src="https://github.com/user-attachments/assets/070c9ee6-4692-44f5-82ab-973415024654" />


**Question 10**
DELETE FROM CSE_Students;

COMMIT;

**Output:**
<img width="971" height="405" alt="image" src="https://github.com/user-attachments/assets/a2145cfb-c654-4a0d-8eb1-e3fdf913ab02" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
