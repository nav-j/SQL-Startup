# SQL Task – Using GROUP BY

This task will help you understand how to use the **`GROUP BY`** statement in SQL to summarize data.

---

## Table: Employees

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

## 🎯 **Task**

Find the **total salary** and **average salary** for each department.

---

### ✅ **Solution**

```sql
SELECT Department, 
       SUM(Salary) AS TotalSalary, 
       AVG(Salary) AS AverageSalary
FROM Employees
GROUP BY Department;
````

---

### 📊 **Expected Output**

| Department | TotalSalary | AverageSalary |
| ---------- | ----------- | ------------- |
| HR         | 105000      | 35000.00      |
| IT         | 235000      | 58750.00      |
| Finance    | 182000      | 60666.67      |

---

### 💡 **Explanation**

* **`GROUP BY Department`** groups all rows having the same department.
* **`SUM(Salary)`** calculates the total salary in each group.
* **`AVG(Salary)`** finds the average salary per department.

---
