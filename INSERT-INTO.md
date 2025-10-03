# SQL Task – INSERT INTO (Solutions + Outputs)

## 📌 Original Table: Employees

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 1     | Ramesh | HR         | 40000  | Delhi     |
| 2     | Priya  | IT         | 55000  | Mumbai    |
| 3     | Anil   | Finance    | 60000  | Bangalore |
| 4     | Neha   | IT         | 45000  | Delhi     |
| 5     | Suresh | HR         | 30000  | Chennai   |
| 6     | Meena  | IT         | 70000  | Pune      |

---

### **Task 1**

👉 Insert a new employee **(EmpID = 7, Name = 'Rajesh', Department = 'Finance', Salary = 50000, City = 'Hyderabad')**

```sql
INSERT INTO Employees (EmpID, Name, Department, Salary, City)
VALUES (7, 'Rajesh', 'Finance', 50000, 'Hyderabad');
```

**Updated Table (new row added):**

| EmpID | Name   | Department | Salary | City      |
| ----- | ------ | ---------- | ------ | --------- |
| 7     | Rajesh | Finance    | 50000  | Hyderabad |

---

### **Task 2**

👉 Insert a new employee into Employees table **without specifying column names** (values must match column order).

```sql
INSERT INTO Employees 
VALUES (8, 'Kavita', 'IT', 65000, 'Chennai');
```

**Updated Table (new row added):**

| EmpID | Name   | Department | Salary | City    |
| ----- | ------ | ---------- | ------ | ------- |
| 8     | Kavita | IT         | 65000  | Chennai |

---

### **Task 3**

👉 Insert multiple employees in one query:

```sql
INSERT INTO Employees (EmpID, Name, Department, Salary, City)
VALUES 
(9, 'Arjun', 'HR', 35000, 'Delhi'),
(10, 'Simran', 'Finance', 72000, 'Mumbai');
```

**Updated Table (new rows added):**

| EmpID | Name   | Department | Salary | City   |
| ----- | ------ | ---------- | ------ | ------ |
| 9     | Arjun  | HR         | 35000  | Delhi  |
| 10    | Simran | Finance    | 72000  | Mumbai |
