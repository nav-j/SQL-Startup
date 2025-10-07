#  SQL Task – LIKE Operator

This document contains SQL practice tasks using the **`LIKE`** operator in MySQL to filter records based on pattern matching.  
The `LIKE` operator is often used with **wildcards**:
- `%` → Represents zero or more characters  
- `_` → Represents exactly one character  

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

### **Task 1** - Find employees whose names start with the letter ‘R’.

```sql
SELECT * 
FROM Employees
WHERE Name LIKE 'R%';
````

**✅ Sample Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 7     | Rajesh | Finance    | 50000  | Hyderabad |

---

### **Task 2** - Find employees whose names end with ‘a’.

```sql
SELECT * 
FROM Employees
WHERE Name LIKE '%a';
```

**✅ Sample Output:**

| EmpID | Name   | Department | Salary | City    |
| ----- | ------ | ---------- | ------ | ------- |
| 2     | Priya  | IT         | 55000  | Mumbai  |
| 6     | Meena  | IT         | 70000  | Pune    |
| 8     | Kavita | IT         | 65000  | Chennai |
| 10    | Simran | Finance    | 72000  | Mumbai  |

---

### **Task 3** - Find employees whose name contains ‘esh’.

```sql
SELECT * 
FROM Employees
WHERE Name LIKE '%esh%';
```

**✅ Sample Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 7     | Rajesh | Finance    | 50000  | Hyderabad |

---

### **Task 4** - Find employees whose city name starts with the letter ‘D’.

```sql
SELECT * 
FROM Employees
WHERE City LIKE 'D%';
```

**✅ Sample Output:**

| EmpID | Name   | Department | Salary | City  |
| ----- | ------ | ---------- | ------ | ----- |
| 1     | Ramesh | HR         | 40000  | Delhi |
| 4     | Neha   | IT         | 45000  | Delhi |
| 9     | Arjun  | HR         | 35000  | Delhi |

---

### **Task 5** - Find employees whose name has 5 characters only.

```sql
SELECT * 
FROM Employees
WHERE Name LIKE '_____';
```

**✅ Sample Output:**

| EmpID | Name  | Department | Salary | City      |
| ----- | ----- | ---------- | ------ | --------- |
| 3     | Anil  | Finance    | 60000  | Bangalore |
| 9     | Arjun | HR         | 35000  | Delhi     |

---

### **Task 6** - Find employees whose names do not start with ‘A’.

```sql
SELECT * 
FROM Employees
WHERE Name NOT LIKE 'A%';
```

**✅ Sample Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |
| 6     | Meena  | IT         | 70000  | Pune      |
| 7     | Rajesh | Finance    | 50000  | Hyderabad |
| 8     | Kavita | IT         | 65000  | Chennai   |
| 10    | Simran | Finance    | 72000  | Mumbai    |

---

## ✅ Concepts Covered

* `LIKE` operator for pattern matching
* `%` wildcard for multiple characters
* `_` wildcard for a single character
* `NOT LIKE` for opposite pattern filtering
