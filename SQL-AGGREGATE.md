# SQL Task – Aggregate Functions

This document contains SQL practice tasks to understand and apply **Aggregate Functions** in MySQL.

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

## Tasks

### **Task 1**
**Find the total number of employees in the company**

```sql
SELECT COUNT(*) AS TotalEmployees
FROM Employees;
````

---

### **Task 2**

**Find the average salary of all employees**

```sql
SELECT AVG(Salary) AS AverageSalary
FROM Employees;
```

---

### **Task 3**

**Find the highest and lowest salary in the company**

```sql
SELECT MAX(Salary) AS HighestSalary, MIN(Salary) AS LowestSalary
FROM Employees;
```

---

### **Task 4**

**Find the total salary paid to all employees**

```sql
SELECT SUM(Salary) AS TotalSalary
FROM Employees;
```

---

### **Task 5**

**Find the average salary by department**

```sql
SELECT Department, AVG(Salary) AS AverageSalary
FROM Employees
GROUP BY Department;
```

---

### **Task 6**

**Find the number of employees in each department**

```sql
SELECT Department, COUNT(*) AS TotalEmployees
FROM Employees
GROUP BY Department;
```

---

### **Task 7**

**Find the total salary of employees in each city**

```sql
SELECT City, SUM(Salary) AS TotalCitySalary
FROM Employees
GROUP BY City;
```

---

### **Task 8**

**Display departments having average salary greater than 50,000**

```sql
SELECT Department, AVG(Salary) AS AverageSalary
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 50000;
```

---

##  Concepts Covered

* `COUNT()` — Count total rows
* `SUM()` — Calculate total sum
* `AVG()` — Find average value
* `MIN()` — Get minimum value
* `MAX()` — Get maximum value
* `GROUP BY` — Group results by column
* `HAVING` — Filter grouped results
