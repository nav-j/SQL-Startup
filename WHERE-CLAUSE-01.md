# SQL Task with WHERE Clause (Task + Solution)

 SQL practice tasks using the **WHERE** clause along with their solutions and expected outputs.

---

## 📌 Table: Employees

| EmpID | Name   | Department | Salary | City      |
|-------|--------|------------|--------|-----------|
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |
| 6     | Meena  | IT         | 70000  | Pune      |

---

## Tasks, Solutions & Expected Outputs

### **Task 1**
**Employees who work in the IT department**

```sql
SELECT * 
FROM Employees
WHERE Department = 'IT';
````

**Expected Output:**

| EmpID | Name  | Department | Salary | City   |
| ----- | ----- | ---------- | ------ | ------ |
| 2     | Priya | IT         | 55000  | Mumbai |
| 4     | Neha  | IT         | 45000  | Delhi  |
| 6     | Meena | IT         | 70000  | Pune   |

---

### **Task 2**

**Employees whose salary is greater than 50,000**

```sql
SELECT * 
FROM Employees
WHERE Salary > 50000;
```

**Expected Output:**

| EmpID | Name  | Department | Salary | City      |
| ----- | ----- | ---------- | ------ | --------- |
| 2     | Priya | IT         | 55000  | Mumbai    |
| 3     | Anil  | Finance    | 60000  | Bangalore |
| 6     | Meena | IT         | 70000  | Pune      |

---

### **Task 3**

**Employees who live in Delhi**

```sql
SELECT * 
FROM Employees
WHERE City = 'Delhi';
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City  |
| ----- | ------ | ---------- | ------ | ----- |
| 1     | Ramesh | HR         | 40000  | Delhi |
| 4     | Neha   | IT         | 45000  | Delhi |

---

### **Task 4**

**HR employees with salary less than 35,000**

```sql
SELECT * 
FROM Employees
WHERE Department = 'HR' AND Salary < 35000;
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City    |
| ----- | ------ | ---------- | ------ | ------- |
| 5     | Suresh | HR         | 30000  | Chennai |

---

### **Task 5**

**Employees whose city is not Mumbai**

```sql
SELECT * 
FROM Employees
WHERE City <> 'Mumbai';
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |
| 6     | Meena  | IT         | 70000  | Pune      |

---

### **Task 6**

**Employees with salary between 40,000 and 60,000**

```sql
SELECT * 
FROM Employees
WHERE Salary BETWEEN 40000 AND 60000;
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 4     | Neha   | IT         | 45000  | Delhi     |

---
