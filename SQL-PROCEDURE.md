# MySQL Stored Procedures – Task with Solutions (Using Python + MySQL + XAMPP)

##  Prerequisites
- XAMPP installed (MySQL running)
- Jupyter Notebook or Python
- `mysql-connector-python` installed
- Database: `mydatabase`

---

## 🗄️ Step 1 – Create Database
```sql
CREATE DATABASE mydatabase;
````

---

## Step 2 – Create Customers Table

```sql
CREATE TABLE IF NOT EXISTS customers (
    customer_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    city VARCHAR(50)
);
```

---

## Task 1 – Create Stored Procedure to Insert Customer

### ✔️ Procedure

```sql
DROP PROCEDURE IF EXISTS AddCustomer;
CREATE PROCEDURE AddCustomer(
    IN cust_name VARCHAR(100),
    IN cust_email VARCHAR(100),
    IN cust_city VARCHAR(50)
)
BEGIN
    INSERT INTO customers (name, email, city) VALUES (cust_name, cust_email, cust_city);
END;
```

### ✔️ Call Procedure

```sql
CALL AddCustomer('Aman Singh', 'aman@mail.com', 'Delhi');
CALL AddCustomer('Priya Verma', 'priya@gmail.com', 'Mumbai');
```

---

## ✅ Task 2 – Create Procedure to Get Customers by City

### ✔️ Procedure

```sql
DROP PROCEDURE IF EXISTS GetCustomersByCity;
CREATE PROCEDURE GetCustomersByCity(IN cityName VARCHAR(50))
BEGIN
    SELECT * FROM customers WHERE city = cityName;
END;
```

### ✔️ Call Procedure

```sql
CALL GetCustomersByCity('Mumbai');
```

---

## ✅ Task 3 – Update Customer Email

### ✔️ Procedure

```sql
DROP PROCEDURE IF EXISTS UpdateCustomerEmail;
CREATE PROCEDURE UpdateCustomerEmail(IN cid INT, IN newEmail VARCHAR(100))
BEGIN
    UPDATE customers SET email = newEmail WHERE customer_id = cid;
END;
```

### ✔️ Call Procedure

```sql
CALL UpdateCustomerEmail(1, 'aman_new@mail.com');
```

---

## ✅ Bonus Task – Delete a Customer

### ✔️ Procedure

```sql
DROP PROCEDURE IF EXISTS DeleteCustomer;
CREATE PROCEDURE DeleteCustomer(IN cid INT)
BEGIN
    DELETE FROM customers WHERE customer_id = cid;
END;
```

### ✔️ Call Procedure

```sql
CALL DeleteCustomer(2);
```

---

## 🔎 Final Table Output

```sql
SELECT * FROM customers;
```

---

## ✅ Full Python Code (Using mysql.connector)

```python
import mysql.connector

conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="mydatabase"
)
cursor = conn.cursor()

cursor.execute("""CREATE TABLE IF NOT EXISTS customers (
    customer_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    city VARCHAR(50)
)""")

cursor.execute("DROP PROCEDURE IF EXISTS AddCustomer")
cursor.execute("""
CREATE PROCEDURE AddCustomer(IN cust_name VARCHAR(100), IN cust_email VARCHAR(100), IN cust_city VARCHAR(50))
BEGIN
    INSERT INTO customers(name, email, city) VALUES(cust_name, cust_email, cust_city);
END
""")
cursor.execute("CALL AddCustomer('Aman Singh', 'aman@mail.com', 'Delhi')")
cursor.execute("CALL AddCustomer('Priya Verma', 'priya@gmail.com', 'Mumbai')")

cursor.execute("DROP PROCEDURE IF EXISTS GetCustomersByCity")
cursor.execute("""
CREATE PROCEDURE GetCustomersByCity(IN cityName VARCHAR(50))
BEGIN
    SELECT * FROM customers WHERE city = cityName;
END
""")
cursor.execute("CALL GetCustomersByCity('Mumbai')")
print(cursor.fetchall())

cursor.execute("DROP PROCEDURE IF EXISTS UpdateCustomerEmail")
cursor.execute("""
CREATE PROCEDURE UpdateCustomerEmail(IN cid INT, IN newEmail VARCHAR(100))
BEGIN
    UPDATE customers SET email = newEmail WHERE customer_id = cid;
END
""")
cursor.execute("CALL UpdateCustomerEmail(1, 'aman_new@mail.com')")

cursor.execute("DROP PROCEDURE IF EXISTS DeleteCustomer")
cursor.execute("""
CREATE PROCEDURE DeleteCustomer(IN cid INT)
BEGIN
    DELETE FROM customers WHERE customer_id = cid;
END
""")
cursor.execute("CALL DeleteCustomer(2)")

conn.commit()
cursor.execute("SELECT * FROM customers")
print(cursor.fetchall())

cursor.close()
conn.close()
```

---

## ✅ Output Example

```
(1, 'Aman Singh', 'aman_new@mail.com', 'Delhi')
```
