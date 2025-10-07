# SQL Task – MIN() and MAX() Functions

This document contains SQL practice tasks focused on the **MIN()** and **MAX()** aggregate functions in MySQL, along with their sample outputs.

---

## Table: Employees

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |
| 6     | Meena  | IT         | 70000  | Pune      |
| 7     | Rajesh | Finance    | 50000  | Hyderabad |
| 8     | Kavita | IT         | 65000  | Chennai   |
| 9     | Arjun  | HR         | 35000  | Delhi     |
| 10    | Simran | Finance    | 72000  | Mumbai    |

---

## Tasks with Solutions and Outputs

---

### **Task 1** - Find the minimum salary in the company.

```sql
SELECT MIN(Salary) AS MinimumSalary
FROM Employees;
````

**✅ Sample Output:**

| MinimumSalary |
| ------------- |
| 30000         |

---

### **Task 2** - Find the maximum salary in the company.

```sql
SELECT MAX(Salary) AS MaximumSalary
FROM Employees;
```

**✅ Sample Output:**

| MaximumSalary |
| ------------- |
| 72000         |

---

### **Task 3** - Find the minimum and maximum salary in each department.

```sql
SELECT Department, MIN(Salary) AS MinSalary, MAX(Salary) AS MaxSalary
FROM Employees
GROUP BY Department;
```

**✅ Sample Output:**

| Department | MinSalary | MaxSalary |
| ---------- | --------- | --------- |
| Finance    | 50000     | 72000     |
| HR         | 30000     | 40000     |
| IT         | 45000     | 70000     |

---

### **Task 4** - Find the employee(s) with the maximum salary.

```sql
SELECT * 
FROM Employees
WHERE Salary = (SELECT MAX(Salary) FROM Employees);
```

**✅ Sample Output:**

| EmpID | Name   | Department | Salary | City   |
| ----- | ------ | ---------- | ------ | ------ |
| 10    | Simran | Finance    | 72000  | Mumbai |

---

### **Task 5** - Find the employee(s) with the minimum salary in the IT department.

```sql
SELECT * 
FROM Employees
WHERE Salary = (
  SELECT MIN(Salary) 
  FROM Employees 
  WHERE Department = 'IT'
);
```

**✅ Sample Output:**

| EmpID | Name | Department | Salary | City  |
| ----- | ---- | ---------- | ------ | ----- |
| 4     | Neha | IT         | 45000  | Delhi |

---

## ✅ Concepts Covered

* `MIN()` → Returns the smallest value in a column
* `MAX()` → Returns the largest value in a column
* Use of **`GROUP BY`** to find min/max per group
* Use of **subqueries** to retrieve detailed rows

---

📘 **Practice Goal:**
Learn how to extract **minimum and maximum values** and identify corresponding employees or departments using SQL aggregate functions.
