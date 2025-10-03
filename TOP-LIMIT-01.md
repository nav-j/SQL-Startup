# SQL Task – Display Top Records (MySQL LIMIT)

## 📌 Table: Employees

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

👉 Display the **top 3 employees**

```sql
SELECT * 
FROM Employees
LIMIT 3;
```

---

### **Task 2**

👉 Display the **top 5 highest-paid employees**

```sql
SELECT * 
FROM Employees
ORDER BY Salary DESC
LIMIT 5;
```

---

### **Task 3**

👉 Display the **2nd and 3rd employees** from the table (skip the first record, then fetch 2 records)

```sql
SELECT * 
FROM Employees
LIMIT 1, 2;
```

---

### **Task 4**

👉 Display the **top 2 employees from the IT department**

```sql
SELECT * 
FROM Employees
WHERE Department = 'IT'
LIMIT 2;
```

---

### **Task 5**

👉 Display the **top 3 employees with the lowest salary**

```sql
SELECT * 
FROM Employees
ORDER BY Salary ASC
LIMIT 3;
```
