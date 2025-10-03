# SQL Task – DELETE

## 📌 Original Table: Employees

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

### **Task 1**

👉 Delete the employee with **EmpID = 5**

```sql
DELETE FROM Employees
WHERE EmpID = 5;
```

---

### **Task 2**

👉 Delete all employees from the **HR department**

```sql
DELETE FROM Employees
WHERE Department = 'HR';
```

---

### **Task 3**

👉 Delete all employees who live in **Delhi**

```sql
DELETE FROM Employees
WHERE City = 'Delhi';
```

---

### **Task 4**

👉 Delete employees whose **salary is less than 40,000**

```sql
DELETE FROM Employees
WHERE Salary < 40000;
```

---

### **Task 5**

👉 Delete all records from the table (⚠ use carefully)

```sql
DELETE FROM Employees;
```
