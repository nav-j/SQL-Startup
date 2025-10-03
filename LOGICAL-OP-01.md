### **Task 1**

**Employees who work in the IT department AND have salary greater than 50,000**

```sql
SELECT * 
FROM Employees
WHERE Department = 'IT' AND Salary > 50000;
```

**Expected Output:**

| EmpID | Name  | Department | Salary | City   |
| ----- | ----- | ---------- | ------ | ------ |
| 2     | Priya | IT         | 55000  | Mumbai |
| 6     | Meena | IT         | 70000  | Pune   |

---

### **Task 2**

**Employees who work in the HR department OR live in Delhi**

```sql
SELECT * 
FROM Employees
WHERE Department = 'HR' OR City = 'Delhi';
```

**Expected Output:**

| EmpID | Name   | Department | Salary | City    |
| ----- | ------ | ---------- | ------ | ------- |
| 1     | Ramesh | HR         | 40000  | Delhi   |
| 4     | Neha   | IT         | 45000  | Delhi   |
| 5     | Suresh | HR         | 30000  | Chennai |

---

### **Task 3**

**Employees whose city is NOT Mumbai**

```sql
SELECT * 
FROM Employees
WHERE NOT City = 'Mumbai';
```

*(OR `WHERE City <> 'Mumbai';`)*

**Expected Output:**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |
| 6     | Meena  | IT         | 70000  | Pune      |

---

### **Task 4**

**Employees who are in IT department AND (salary > 60000 OR city = 'Delhi')**

```sql
SELECT * 
FROM Employees
WHERE Department = 'IT' AND (Salary > 60000 OR City = 'Delhi');
```

**Expected Output:**

| EmpID | Name  | Department | Salary | City  |
| ----- | ----- | ---------- | ------ | ----- |
| 4     | Neha  | IT         | 45000  | Delhi |
| 6     | Meena | IT         | 70000  | Pune  |
