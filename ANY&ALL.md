# SQL Task – Using ANY and ALL Operators

The **`ANY`** and **`ALL`** operators allow comparisons between a value and the results of a subquery.

- `ANY` → True if **any** of the subquery values satisfy the condition  
- `ALL` → True only if **all** of the subquery values satisfy the condition  

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

## **Task 1 – Using `ANY`**

Display employees whose salary is **greater than the salary of any employee in the HR department**.

### ✅ **Solution**

```sql
SELECT Name, Department, Salary
FROM Employees
WHERE Salary > ANY (
    SELECT Salary FROM Employees WHERE Department = 'HR'
);
````

### **Explanation**

* The subquery returns all HR salaries → (40000, 30000, 35000)
* `> ANY` means “greater than the lowest HR salary (30,000)”
* So it selects everyone with salary > 30,000

### **Sample Output**

| Name   | Department | Salary |
| ------ | ---------- | ------ |
| Ramesh | HR         | 40000  |
| Priya  | IT         | 55000  |
| Anil   | Finance    | 60000  |
| Neha   | IT         | 45000  |
| Meena  | IT         | 70000  |
| Rajesh | Finance    | 50000  |
| Kavita | IT         | 65000  |
| Simran | Finance    | 72000  |

---

## **Task 2 – Using `ALL`**

Display employees whose salary is **greater than the salary of all employees in the HR department**.

### **Solution**

```sql
SELECT Name, Department, Salary
FROM Employees
WHERE Salary > ALL (
    SELECT Salary FROM Employees WHERE Department = 'HR'
);
```

### **Explanation**

* HR salaries → (40000, 30000, 35000)
* `> ALL` means “greater than the highest HR salary (40,000)”
* So only employees earning **above ₹40,000** will be shown.

### **Sample Output**

| Name   | Department | Salary |
| ------ | ---------- | ------ |
| Priya  | IT         | 55000  |
| Anil   | Finance    | 60000  |
| Neha   | IT         | 45000  |
| Meena  | IT         | 70000  |
| Rajesh | Finance    | 50000  |
| Kavita | IT         | 65000  |
| Simran | Finance    | 72000  |

---

## **Bonus Task**

Display employees who earn **less than all IT employees**.

```sql
SELECT Name, Department, Salary
FROM Employees
WHERE Salary < ALL (
    SELECT Salary FROM Employees WHERE Department = 'IT'
);
```

### **Sample Output**

| Name   | Department | Salary |
| ------ | ---------- | ------ |
| Suresh | HR         | 30000  |
| Arjun  | HR         | 35000  |

---

## **Concepts Covered**

* Using subqueries with `ANY` and `ALL`
* Comparing values against multiple results
* Understanding difference between `ANY` and `ALL`
```

---

Would you like me to create the **next task on “SQL CASE statement”** (conditional logic in queries)?
```
