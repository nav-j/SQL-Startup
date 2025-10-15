# SQL Task – Using SQL CASE Statement

The **`CASE`** statement is used in SQL to perform conditional logic —  
similar to `IF...ELSE` in programming languages.

---

##  Table: Employees

| EmpID | Name   | Department | Salary | City      |
|-------|--------|-------------|--------|-----------|
| 1     | Ramesh | HR          | 40000  | Delhi     |
| 2     | Priya  | IT          | 55000  | Mumbai    |
| 3     | Anil   | Finance     | 60000  | Bangalore |
| 4     | Neha   | IT          | 45000  | Delhi     |
| 5     | Suresh | HR          | 30000  | Chennai   |
| 6     | Meena  | IT          | 70000  | Pune      |
| 7     | Rajesh | Finance     | 50000  | Hyderabad |
| 8     | Kavita | IT          | 65000  | Chennai   |
| 9     | Arjun  | HR          | 35000  | Delhi     |
| 10    | Simran | Finance     | 72000  | Mumbai    |

---

## **Task 1 – Categorize Employees Based on Salary**

Display all employees with a **Salary Grade** using the following conditions:  
- Salary ≥ 70,000 → `'High'`  
- Salary between 40,000–69,999 → `'Medium'`  
- Salary < 40,000 → `'Low'`

---

### ✅ **Solution**

```sql
SELECT 
    Name,
    Department,
    Salary,
    CASE
        WHEN Salary >= 70000 THEN 'High'
        WHEN Salary BETWEEN 40000 AND 69999 THEN 'Medium'
        ELSE 'Low'
    END AS SalaryGrade
FROM Employees;
````

---

### 📊 **Expected Output**

| Name   | Department | Salary | SalaryGrade |
| ------ | ---------- | ------ | ----------- |
| Ramesh | HR         | 40000  | Medium      |
| Priya  | IT         | 55000  | Medium      |
| Anil   | Finance    | 60000  | Medium      |
| Neha   | IT         | 45000  | Medium      |
| Suresh | HR         | 30000  | Low         |
| Meena  | IT         | 70000  | High        |
| Rajesh | Finance    | 50000  | Medium      |
| Kavita | IT         | 65000  | Medium      |
| Arjun  | HR         | 35000  | Low         |
| Simran | Finance    | 72000  | High        |

---

## 🎯 **Task 2 – Department Bonus Classification**

Add a new column **BonusPercent** based on department rules:

* IT → 10%
* HR → 8%
* Finance → 12%

---

### ✅ **Solution**

```sql
SELECT 
    Name,
    Department,
    Salary,
    CASE 
        WHEN Department = 'IT' THEN 0.10
        WHEN Department = 'HR' THEN 0.08
        WHEN Department = 'Finance' THEN 0.12
    END AS BonusPercent
FROM Employees;
```

---

### 📊 **Sample Output**

| Name   | Department | Salary | BonusPercent |
| ------ | ---------- | ------ | ------------ |
| Ramesh | HR         | 40000  | 0.08         |
| Priya  | IT         | 55000  | 0.10         |
| Anil   | Finance    | 60000  | 0.12         |
| Neha   | IT         | 45000  | 0.10         |
| Suresh | HR         | 30000  | 0.08         |
| Meena  | IT         | 70000  | 0.10         |
| Rajesh | Finance    | 50000  | 0.12         |
| Kavita | IT         | 65000  | 0.10         |
| Arjun  | HR         | 35000  | 0.08         |
| Simran | Finance    | 72000  | 0.12         |

---

## 🧠 **Bonus Task**

Show each employee’s **Performance Category** based on this rule:

* If Salary ≥ Average Salary → `'Above Average'`
* Otherwise → `'Below Average'`

```sql
SELECT 
    Name,
    Salary,
    CASE 
        WHEN Salary >= (SELECT AVG(Salary) FROM Employees) THEN 'Above Average'
        ELSE 'Below Average'
    END AS PerformanceCategory
FROM Employees;
```

---

## ✅ **Concepts Covered**

* Conditional logic with `CASE`
* Nested comparisons inside queries
* Derived (calculated) columns using `CASE`
* Combining `CASE` with subqueries

Would you like me to create the **next task on “SQL Subqueries (nested queries)”** next?
```
