
## Task – Python + SQL (Exercise) To select all data from table.

```python
import mysql.connector

# Connect to MySQL

#  TODO: Write a SQL query to select all records from the table 'customers'

# TODO: Fetch and print all rows


cursor.close()
conn.close()
```

---

### 🎯 Instructions:

1. Create a Connection.
2. Replace the empty `cursor.execute("")` with the correct **SQL SELECT query**.
3. Fetch all results using the appropriate cursor method.
4. Print each row to display the table data.

## Solution Code :

---

## ✅ Solution Code

```python
import mysql.connector

# Connect to MySQL
conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",     # change if needed
    database="test"
)

cursor = conn.cursor()

# ✅ SQL query to select all records from the table 'customers'
cursor.execute("SELECT * FROM customers")

# ✅ Fetch and print all rows
print("📌 Customers Table Data:")
for row in cursor.fetchall():
    print(row)

cursor.close()
conn.close()
```

---

### Example Output:

```
(1, 'John Doe', '123 Main Street', 110001)
(2, 'Jane Smith', '456 Park Avenue', 220002)
(3, 'Alice Johnson', '789 Green Road', 330003)
```
