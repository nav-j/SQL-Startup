# SQL Task – Using EXISTS

This task helps you understand how to use the **`EXISTS`** operator in MySQL.  
`EXISTS` is used to test whether a subquery returns any record — it returns **TRUE** if the subquery has at least one matching row.

---

## Table 1: Employees

| EmpID | Name   | DepartmentID | Salary |
|-------|--------|---------------|--------|
| 1     | Ramesh | 101           | 40000  |
| 2     | Priya  | 102           | 55000  |
| 3     | Anil   | 103           | 60000  |
| 4     | Neha   | 102           | 45000  |
| 5     | Suresh | 104           | 30000  |
| 6     | Meena  | 102           | 70000  |

---

## Table 2: Departments

| DepartmentID | DepartmentName | Location  |
|--------------|----------------|-----------|
| 101          | HR             | Delhi     |
| 102          | IT             | Mumbai    |
| 103          | Finance        | Bangalore |
| 105          | Marketing      | Chennai   |

---

##  **Task**

Display all employees who **belong to a department that exists in the Departments table**.

---

### ✅ **Solution**

```sql
SELECT Name, DepartmentID, Salary
FROM Employees e
WHERE EXISTS (
    SELECT 1
    FROM Departments d
    WHERE d.DepartmentID = e.DepartmentID
);
````

---

### 📊 **Expected Output**

| Name   | DepartmentID | Salary |
| ------ | ------------ | ------ |
| Ramesh | 101          | 40000  |
| Priya  | 102          | 55000  |
| Anil   | 103          | 60000  |
| Neha   | 102          | 45000  |
| Meena  | 102          | 70000  |

*(Suresh is excluded because DepartmentID = 104 does not exist in the Departments table.)*

---

## 🧠 **Task 2 (Bonus)**

Display all departments that **have at least one employee** in the Employees table.

```sql
SELECT DepartmentName
FROM Departments d
WHERE EXISTS (
    SELECT 1
    FROM Employees e
    WHERE e.DepartmentID = d.DepartmentID
);
```

**✅ Sample Output:**

| DepartmentName |
| -------------- |
| HR             |
| IT             |
| Finance        |

*(Marketing has no employees, so it’s excluded.)*

---

## ✅ **Concepts Covered**

* `EXISTS` with subqueries
* Checking relationships between two tables
* Filtering data based on subquery results

---
