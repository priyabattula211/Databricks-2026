# SQL Practice: Employees Table

A clean and structured SQL practice worksheet for creating an Employees table, inserting records, and solving common SELECT, WHERE, GROUP BY, HAVING, TOP, and DISTINCT questions.

---

## 1) Table Creation

```sql
CREATE TABLE Employees (
    emp_id INT,
    emp_name VARCHAR(50),
    department VARCHAR(50),
    salary INT,
    city VARCHAR(50),
    experience INT
);
```

## 2) Insert Data into the Table

```sql
INSERT INTO Employees VALUES
(101, 'Rahul', 'IT', 75000, 'Hyderabad', 5),
(102, 'Anjali', 'HR', 45000, 'Chennai', 3),
(103, 'Kiran', 'IT', 82000, 'Bangalore', 6),
(104, 'Sneha', 'Finance', 67000, 'Hyderabad', 4),
(105, 'Aman', 'HR', 39000, 'Pune', 2),
(106, 'Ravi', 'Finance', 91000, 'Mumbai', 8),
(107, 'Divya', 'IT', 55000, 'Chennai', 3),
(108, 'Meena', 'Sales', 48000, 'Bangalore', 2),
(109, 'Arjun', 'Sales', 61000, 'Hyderabad', 5),
(110, 'Pooja', 'IT', 73000, 'Mumbai', 4),
(111, 'Vikas', 'HR', 52000, 'Pune', 3),
(112, 'Nisha', 'Finance', 88000, 'Bangalore', 7),
(113, 'Tarun', 'Sales', 46000, 'Chennai', 2),
(114, 'Kavya', 'IT', 97000, 'Hyderabad', 9),
(115, 'Manoj', 'Finance', 58000, 'Mumbai', 4);
```

---

## 3) SELECT Queries

### Question 1: Display all employee details.

```sql
SELECT *
FROM Employees;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 102 | Anjali | HR | 45000 | Chennai | 3 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 105 | Aman | HR | 39000 | Pune | 2 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 111 | Vikas | HR | 52000 | Pune | 3 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 113 | Tarun | Sales | 46000 | Chennai | 2 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 115 | Manoj | Finance | 58000 | Mumbai | 4 |

### Question 2: Display only employee names and salaries.

```sql
SELECT emp_name, salary
FROM Employees;
```

Expected Output:

| emp_name | salary |
|---|---:|
| Rahul | 75000 |
| Anjali | 45000 |
| Kiran | 82000 |
| Sneha | 67000 |
| Aman | 39000 |
| Ravi | 91000 |
| Divya | 55000 |
| Meena | 48000 |
| Arjun | 61000 |
| Pooja | 73000 |
| Vikas | 52000 |
| Nisha | 88000 |
| Tarun | 46000 |
| Kavya | 97000 |
| Manoj | 58000 |

### Question 3: Display employee names and departments.

```sql
SELECT emp_name, department
FROM Employees;
```

Expected Output:

| emp_name | department |
|---|---|
| Rahul | IT |
| Anjali | HR |
| Kiran | IT |
| Sneha | Finance |
| Aman | HR |
| Ravi | Finance |
| Divya | IT |
| Meena | Sales |
| Arjun | Sales |
| Pooja | IT |
| Vikas | HR |
| Nisha | Finance |
| Tarun | Sales |
| Kavya | IT |
| Manoj | Finance |

### Question 4: Display all employees from the IT department.

```sql
SELECT *
FROM Employees
WHERE department = 'IT';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 5: Display employee names and experience.

```sql
SELECT emp_name, experience
FROM Employees;
```

Expected Output:

| emp_name | experience |
|---|---:|
| Rahul | 5 |
| Anjali | 3 |
| Kiran | 6 |
| Sneha | 4 |
| Aman | 2 |
| Ravi | 8 |
| Divya | 3 |
| Meena | 2 |
| Arjun | 5 |
| Pooja | 4 |
| Vikas | 3 |
| Nisha | 7 |
| Tarun | 2 |
| Kavya | 9 |
| Manoj | 4 |

---

## 4) WHERE Queries

### Question 1: Find employees with salary greater than 70000.

```sql
SELECT *
FROM Employees
WHERE salary > 70000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 2: Find employees working in Hyderabad.

```sql
SELECT *
FROM Employees
WHERE city = 'Hyderabad';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 3: Find employees with experience less than 4 years.

```sql
SELECT *
FROM Employees
WHERE experience < 4;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 102 | Anjali | HR | 45000 | Chennai | 3 |
| 105 | Aman | HR | 39000 | Pune | 2 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 111 | Vikas | HR | 52000 | Pune | 3 |
| 113 | Tarun | Sales | 46000 | Chennai | 2 |

### Question 4: Find employees from Finance department.

```sql
SELECT *
FROM Employees
WHERE department = 'Finance';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 115 | Manoj | Finance | 58000 | Mumbai | 4 |

### Question 5: Find employees whose salary is equal to 52000.

```sql
SELECT *
FROM Employees
WHERE salary = 52000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 111 | Vikas | HR | 52000 | Pune | 3 |

---

## 5) GROUP BY Queries

### Question 1: Find total salary department-wise.

```sql
SELECT department, SUM(salary) AS total_salary
FROM Employees
GROUP BY department;
```

Expected Output:

| department | total_salary |
|---|---:|
| Finance | 304000 |
| HR | 136000 |
| IT | 382000 |
| Sales | 155000 |

### Question 2: Find average salary in each department.

```sql
SELECT department, AVG(salary) AS avg_salary
FROM Employees
GROUP BY department;
```

Expected Output:

| department | avg_salary |
|---|---:|
| Finance | 76000.0000 |
| HR | 45333.3333 |
| IT | 76400.0000 |
| Sales | 51666.6667 |

### Question 3: Count employees in each city.

```sql
SELECT city, COUNT(*) AS employee_count
FROM Employees
GROUP BY city;
```

Expected Output:

| city | employee_count |
|---|---:|
| Bangalore | 3 |
| Chennai | 3 |
| Hyderabad | 4 |
| Mumbai | 3 |
| Pune | 2 |

### Question 4: Find maximum salary in each department.

```sql
SELECT department, MAX(salary) AS max_salary
FROM Employees
GROUP BY department;
```

Expected Output:

| department | max_salary |
|---|---:|
| Finance | 91000 |
| HR | 52000 |
| IT | 97000 |
| Sales | 61000 |

### Question 5: Find minimum experience department-wise.

```sql
SELECT department, MIN(experience) AS min_experience
FROM Employees
GROUP BY department;
```

Expected Output:

| department | min_experience |
|---|---:|
| Finance | 4 |
| HR | 2 |
| IT | 3 |
| Sales | 2 |

---

## 6) HAVING Queries

### Question 1: Find departments having more than 3 employees.

```sql
SELECT department, COUNT(*) AS employee_count
FROM Employees
GROUP BY department
HAVING COUNT(*) > 3;
```

Expected Output:

| department | employee_count |
|---|---:|
| Finance | 4 |
| IT | 5 |

### Question 2: Find departments where average salary is greater than 60000.

```sql
SELECT department, AVG(salary) AS avg_salary
FROM Employees
GROUP BY department
HAVING AVG(salary) > 60000;
```

Expected Output:

| department | avg_salary |
|---|---:|
| Finance | 76000.0000 |
| IT | 76400.0000 |

### Question 3: Find cities having more than 2 employees.

```sql
SELECT city, COUNT(*) AS employee_count
FROM Employees
GROUP BY city
HAVING COUNT(*) > 2;
```

Expected Output:

| city | employee_count |
|---|---:|
| Bangalore | 3 |
| Chennai | 3 |
| Hyderabad | 4 |
| Mumbai | 3 |

### Question 4: Find departments where total salary is greater than 200000.

```sql
SELECT department, SUM(salary) AS total_salary
FROM Employees
GROUP BY department
HAVING SUM(salary) > 200000;
```

Expected Output:

| department | total_salary |
|---|---:|
| Finance | 304000 |
| IT | 382000 |

### Question 5: Find departments where maximum salary is above 90000.

```sql
SELECT department, MAX(salary) AS max_salary
FROM Employees
GROUP BY department
HAVING MAX(salary) > 90000;
```

Expected Output:

| department | max_salary |
|---|---:|
| Finance | 91000 |
| IT | 97000 |

---

## 7) TOP Queries

### Question 1: Display top 5 highest paid employees.

```sql
SELECT TOP 5 *
FROM Employees
ORDER BY salary DESC;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |

### Question 2: Display top 3 employees with highest experience.

```sql
SELECT TOP 3 *
FROM Employees
ORDER BY experience DESC;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |

### Question 3: Display top 2 salaries from Finance department.

```sql
SELECT TOP 2 *
FROM Employees
WHERE department = 'Finance'
ORDER BY salary DESC;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |

### Question 4: Display top 4 employees from Hyderabad.

```sql
SELECT TOP 4 *
FROM Employees
WHERE city = 'Hyderabad'
ORDER BY salary DESC;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |

### Question 5: Display top 1 highest salary employee.

```sql
SELECT TOP 1 *
FROM Employees
ORDER BY salary DESC;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

---

## 8) DISTINCT Queries

### Question 1: Display distinct department names.

```sql
SELECT DISTINCT department
FROM Employees;
```

Expected Output:

| department |
|---|
| Finance |
| HR |
| IT |
| Sales |

### Question 2: Display distinct city names.

```sql
SELECT DISTINCT city
FROM Employees;
```

Expected Output:

| city |
|---|
| Bangalore |
| Chennai |
| Hyderabad |
| Mumbai |
| Pune |

### Question 3: Display distinct salary values.

```sql
SELECT DISTINCT salary
FROM Employees;
```

Expected Output:

| salary |
|---:|
| 39000 |
| 45000 |
| 46000 |
| 48000 |
| 52000 |
| 55000 |
| 58000 |
| 61000 |
| 67000 |
| 73000 |
| 75000 |
| 82000 |
| 88000 |
| 91000 |
| 97000 |

### Question 4: Display distinct combinations of department and city.

```sql
SELECT DISTINCT department, city
FROM Employees;
```

Expected Output:

| department | city |
|---|---|
| IT | Hyderabad |
| HR | Chennai |
| IT | Bangalore |
| Finance | Hyderabad |
| HR | Pune |
| Finance | Mumbai |
| IT | Chennai |
| Sales | Bangalore |
| Sales | Hyderabad |
| IT | Mumbai |
| Finance | Bangalore |
| Sales | Chennai |

### Question 5: Display distinct experience values.

```sql
SELECT DISTINCT experience
FROM Employees;
```

Expected Output:

| experience |
|---:|
| 2 |
| 3 |
| 4 |
| 5 |
| 6 |
| 7 |
| 8 |
| 9 |

---

## 9) Summary

This worksheet covers:
- Table creation and data insertion
- Basic SELECT operations
- Filtering using WHERE
- Grouping and aggregation using GROUP BY
- Filtering grouped results using HAVING
- Retrieving top records using TOP
- Removing duplicates with DISTINCT



