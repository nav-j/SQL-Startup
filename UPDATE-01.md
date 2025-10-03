# SQL Task – UPDATE (Solutions + Outputs)

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

👉 Update the salary of **Ramesh (EmpID = 1)** to **45,000**

```sql
UPDATE Employees
SET Salary = 45000
WHERE EmpID = 1;
```

**Updated Row:**

| EmpID | Name   | Department | Salary | City  |
| ----- | ------ | ---------- | ------ | ----- |
| 1     | Ramesh | HR         | 45000  | Delhi |

---

### **Task 2**

👉 Update the **city of all IT department employees** to **"Noida"**

```sql
UPDATE Employees
SET City = 'Noida'
WHERE Department = 'IT';
```

**Updated Rows:**

| EmpID | Name   | Department | Salary | City  |
| ----- | ------ | ---------- | ------ | ----- |
| 2     | Priya  | IT         | 55000  | Noida |
| 4     | Neha   | IT         | 45000  | Noida |
| 6     | Meena  | IT         | 70000  | Noida |
| 8     | Kavita | IT         | 65000  | Noida |

---

### **Task 3**

👉 Increase salary of all employees in the **HR department by 5,000**

```sql
UPDATE Employees
SET Salary = Salary + 5000
WHERE Department = 'HR';
```

**Updated Rows:**

| EmpID | Name   | Department | Salary | City    |
| ----- | ------ | ---------- | ------ | ------- |
| 1     | Ramesh | HR         | 50000  | Delhi   |
| 5     | Suresh | HR         | 35000  | Chennai |
| 9     | Arjun  | HR         | 40000  | Delhi   |

---

### **Task 4**

👉 Change the department of **Simran (EmpID = 10)** from **Finance to IT**

```sql
UPDATE Employees
SET Department = 'IT'
WHERE EmpID = 10;
```

**Updated Row:**

| EmpID | Name   | Department | Salary | City   |
| ----- | ------ | ---------- | ------ | ------ |
| 10    | Simran | IT         | 72000  | Mumbai |

---

✅ Now the Employees table reflects all the updates applied.
