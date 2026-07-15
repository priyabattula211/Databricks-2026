# SQL Practice: Day 2 - Operators in SQL

This README contains SQL practice questions for comparison operators, logical operators, IN/NOT IN, BETWEEN, and LIKE, using the same Employees table from Day 1.

---

## 1) Comparison Operators

### Question 1: Find employees with salary >= 80000.

```sql
SELECT *
FROM Employees
WHERE salary >= 80000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 2: Find employees with experience <= 3.

```sql
SELECT *
FROM Employees
WHERE experience <= 3;
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

### Question 3: Find employees whose salary <> 45000.

```sql
SELECT *
FROM Employees
WHERE salary <> 45000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
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

### Question 4: Find employees with salary < 50000.

```sql
SELECT *
FROM Employees
WHERE salary < 50000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 102 | Anjali | HR | 45000 | Chennai | 3 |
| 105 | Aman | HR | 39000 | Pune | 2 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 113 | Tarun | Sales | 46000 | Chennai | 2 |

### Question 5: Find employees with experience > 5.

```sql
SELECT *
FROM Employees
WHERE experience > 5;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

---

## 2) Logical Operators

### Question 1: Find employees from IT department AND salary greater than 70000.

```sql
SELECT *
FROM Employees
WHERE department = 'IT' AND salary > 70000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 2: Find employees from Hyderabad OR Bangalore.

```sql
SELECT *
FROM Employees
WHERE city = 'Hyderabad' OR city = 'Bangalore';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 3: Find employees from HR department AND experience less than 3.

```sql
SELECT *
FROM Employees
WHERE department = 'HR' AND experience < 3;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 105 | Aman | HR | 39000 | Pune | 2 |

### Question 4: Find employees with salary greater than 60000 OR experience greater than 6.

```sql
SELECT *
FROM Employees
WHERE salary > 60000 OR experience > 6;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 5: Find employees NOT from Sales department.

```sql
SELECT *
FROM Employees
WHERE department <> 'Sales';
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
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 111 | Vikas | HR | 52000 | Pune | 3 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 115 | Manoj | Finance | 58000 | Mumbai | 4 |

---

## 3) IN and NOT IN Operators

### Question 1: Find employees working in ('Hyderabad', 'Mumbai').

```sql
SELECT *
FROM Employees
WHERE city IN ('Hyderabad', 'Mumbai');
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 2: Find employees whose department IN ('IT', 'Finance').

```sql
SELECT *
FROM Employees
WHERE department IN ('IT', 'Finance');
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 115 | Manoj | Finance | 58000 | Mumbai | 4 |

### Question 3: Find employees whose city NOT IN ('Chennai', 'Pune').

```sql
SELECT *
FROM Employees
WHERE city NOT IN ('Chennai', 'Pune');
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 115 | Manoj | Finance | 58000 | Mumbai | 4 |

### Question 4: Find employees whose salary IN (45000, 75000, 91000).

```sql
SELECT *
FROM Employees
WHERE salary IN (45000, 75000, 91000);
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 102 | Anjali | HR | 45000 | Chennai | 3 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |

### Question 5: Find employees whose department NOT IN ('HR', 'Sales').

```sql
SELECT *
FROM Employees
WHERE department NOT IN ('HR', 'Sales');
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |
| 115 | Manoj | Finance | 58000 | Mumbai | 4 |

---

## 4) BETWEEN Operator

### Question 1: Find employees with salary BETWEEN 50000 AND 80000.

```sql
SELECT *
FROM Employees
WHERE salary BETWEEN 50000 AND 80000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 111 | Vikas | HR | 52000 | Pune | 3 |
| 115 | Manoj | Finance | 58000 | Mumbai | 4 |

### Question 2: Find employees with experience BETWEEN 3 AND 6.

```sql
SELECT *
FROM Employees
WHERE experience BETWEEN 3 AND 6;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 102 | Anjali | HR | 45000 | Chennai | 3 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 111 | Vikas | HR | 52000 | Pune | 3 |

### Question 3: Find employees whose emp_id BETWEEN 105 AND 112.

```sql
SELECT *
FROM Employees
WHERE emp_id BETWEEN 105 AND 112;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 105 | Aman | HR | 39000 | Pune | 2 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 111 | Vikas | HR | 52000 | Pune | 3 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |

### Question 4: Find employees with salary NOT BETWEEN 40000 AND 60000.

```sql
SELECT *
FROM Employees
WHERE salary NOT BETWEEN 40000 AND 60000;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 105 | Aman | HR | 39000 | Pune | 2 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 5: Find employees with experience BETWEEN 2 AND 4.

```sql
SELECT *
FROM Employees
WHERE experience BETWEEN 2 AND 4;
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 102 | Anjali | HR | 45000 | Chennai | 3 |
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 105 | Aman | HR | 39000 | Pune | 2 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 111 | Vikas | HR | 52000 | Pune | 3 |
| 113 | Tarun | Sales | 46000 | Chennai | 2 |

---

## 5) LIKE Operator

### Question 1: Find employees whose names start with 'R'.

```sql
SELECT *
FROM Employees
WHERE emp_name LIKE 'R%';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 101 | Rahul | IT | 75000 | Hyderabad | 5 |
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |

### Question 2: Find employees whose names end with 'a'.

```sql
SELECT *
FROM Employees
WHERE emp_name LIKE '%a';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 104 | Sneha | Finance | 67000 | Hyderabad | 4 |
| 110 | Pooja | IT | 73000 | Mumbai | 4 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 3: Find employees whose names contain 'v'.

```sql
SELECT *
FROM Employees
WHERE emp_name LIKE '%v%';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 106 | Ravi | Finance | 91000 | Mumbai | 8 |
| 107 | Divya | IT | 55000 | Chennai | 3 |
| 111 | Vikas | HR | 52000 | Pune | 3 |
| 114 | Kavya | IT | 97000 | Hyderabad | 9 |

### Question 4: Find employees whose city starts with 'B'.

```sql
SELECT *
FROM Employees
WHERE city LIKE 'B%';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 103 | Kiran | IT | 82000 | Bangalore | 6 |
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 112 | Nisha | Finance | 88000 | Bangalore | 7 |

### Question 5: Find employees whose department ends with 's'.

```sql
SELECT *
FROM Employees
WHERE department LIKE '%s';
```

Expected Output:

| emp_id | emp_name | department | salary | city | experience |
|---|---|---|---:|---|---:|
| 108 | Meena | Sales | 48000 | Bangalore | 2 |
| 109 | Arjun | Sales | 61000 | Hyderabad | 5 |
| 113 | Tarun | Sales | 46000 | Chennai | 2 |

---

## Summary

This Day 2 worksheet covers:
- Comparison operators such as =, <>, >=, <=, <, >
- Logical operators such as AND, OR, NOT
- IN and NOT IN for multiple value matching
- BETWEEN for range checks
- LIKE for pattern matching

Enjoy practicing SQL! 🌟

