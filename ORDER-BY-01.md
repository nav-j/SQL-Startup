### **Task 1**

**List all employees ordered by salary in ascending order**

```sql
SELECT * 
FROM Employees
ORDER BY Salary ASC;
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 5     | Suresh | HR         | 30000  | Chennai   |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 6     | Meena  | IT         | 70000  | Pune      |

---

### **Task 2**

**List all employees ordered by salary in descending order**

```sql
SELECT * 
FROM Employees
ORDER BY Salary DESC;
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 6     | Meena  | IT         | 70000  | Pune      |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |

---

### **Task 3**

**List all employees ordered by Department alphabetically, and within each department by Salary descending**

```sql
SELECT * 
FROM Employees
ORDER BY Department ASC, Salary DESC;
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 6     | Meena  | IT         | 70000  | Pune      |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |

