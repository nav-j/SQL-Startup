# SQL Task – UNION and UNION ALL

This document contains SQL practice tasks using **`UNION`** and **`UNION ALL`** in MySQL.  
Both commands are used to **combine the results of two or more SELECT statements**.

---

## Difference Between UNION and UNION ALL

| Operator | Description | Removes Duplicates? |
|-----------|--------------|----------------------|
| **UNION** | Combines results and removes duplicate rows | ✅ Yes |
| **UNION ALL** | Combines results and keeps all duplicates | ❌ No |

---

## Table 1: Employees_2024

| EmpID | Name   | Department | City      |
|-------|--------|-------------|-----------|
| 1     | Ramesh | HR          | Delhi     |
| 2     | Priya  | IT          | Mumbai    |
| 3     | Anil   | Finance     | Bangalore |
| 4     | Neha   | IT          | Delhi     |

---

## Table 2: Employees_2025

| EmpID | Name   | Department | City      |
|-------|--------|-------------|-----------|
| 5     | Suresh | HR          | Chennai   |
| 6     | Meena  | IT          | Pune      |
| 7     | Anil   | Finance     | Bangalore |
| 8     | Kavita | IT          | Chennai   |

---

## Tasks with Solutions and Outputs

---

### **Task 1**
**Combine employee records from both years (remove duplicates).**

```sql
SELECT Name, Department, City
FROM Employees_2024
UNION
SELECT Name, Department, City
FROM Employees_2025;
````

**✅ Sample Output:**

| Name   | Department | City      |
| ------ | ---------- | --------- |
| Ramesh | HR         | Delhi     |
| Priya  | IT         | Mumbai    |
| Anil   | Finance    | Bangalore |
| Neha   | IT         | Delhi     |
| Suresh | HR         | Chennai   |
| Meena  | IT         | Pune      |
| Kavita | IT         | Chennai   |

*(Duplicate “Anil” record appears only once)*

---

### **Task 2**

**Combine employee records from both years (include duplicates).**

```sql
SELECT Name, Department, City
FROM Employees_2024
UNION ALL
SELECT Name, Department, City
FROM Employees_2025;
```

**✅ Sample Output:**

| Name   | Department | City      |
| ------ | ---------- | --------- |
| Ramesh | HR         | Delhi     |
| Priya  | IT         | Mumbai    |
| Anil   | Finance    | Bangalore |
| Neha   | IT         | Delhi     |
| Suresh | HR         | Chennai   |
| Meena  | IT         | Pune      |
| Anil   | Finance    | Bangalore |
| Kavita | IT         | Chennai   |

*(All rows from both tables are included — duplicates retained)*

---

### **Task 3**

**Display all IT department employees from both tables.**

```sql
SELECT Name, City
FROM Employees_2024
WHERE Department = 'IT'
UNION
SELECT Name, City
FROM Employees_2025
WHERE Department = 'IT';
```

**✅ Sample Output:**

| Name   | City    |
| ------ | ------- |
| Priya  | Mumbai  |
| Neha   | Delhi   |
| Meena  | Pune    |
| Kavita | Chennai |

---

### **Task 4**

**List all cities (without duplicates) where employees are working.**

```sql
SELECT City
FROM Employees_2024
UNION
SELECT City
FROM Employees_2025;
```

**✅ Sample Output:**

| City      |
| --------- |
| Delhi     |
| Mumbai    |
| Bangalore |
| Chennai   |
| Pune      |

---

### **Task 5**

**List all employees who are in the HR department from both years (include duplicates).**

```sql
SELECT Name, City
FROM Employees_2024
WHERE Department = 'HR'
UNION ALL
SELECT Name, City
FROM Employees_2025
WHERE Department = 'HR';
```

**✅ Sample Output:**

| Name   | City    |
| ------ | ------- |
| Ramesh | Delhi   |
| Suresh | Chennai |

---

### **Task 6**

**Count total number of combined records using UNION and UNION ALL.**

```sql
-- Using UNION
SELECT COUNT(*) AS Unique_Records FROM (
    SELECT Name, Department, City FROM Employees_2024
    UNION
    SELECT Name, Department, City FROM Employees_2025
) AS CombinedUnique;

-- Using UNION ALL
SELECT COUNT(*) AS All_Records FROM (
    SELECT Name, Department, City FROM Employees_2024
    UNION ALL
    SELECT Name, Department, City FROM Employees_2025
) AS CombinedAll;
```

**✅ Sample Output:**

| Type           | Count |
| -------------- | ----- |
| Unique_Records | 7     |
| All_Records    | 8     |

---

## ✅ Concepts Covered

* `UNION` – Combine and remove duplicates
* `UNION ALL` – Combine and keep duplicates
* `WHERE` + `UNION` combinations
* Counting total vs unique combined rows

---
