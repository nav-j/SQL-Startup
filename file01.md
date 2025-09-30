## Step 1: Install and Start XAMPP

1. Download & install XAMPP → [Apache Friends](https://www.apachefriends.org/).
2. Open **XAMPP Control Panel**.
3. Start services:

   * ✅ **Apache** (for PHP server)
   * ✅ **MySQL** (for database)

---

## Step 2: Access phpMyAdmin (Database GUI)

1. Open your browser → go to:

   ```
   http://localhost/phpmyadmin/
   ```
2. You’ll see the **phpMyAdmin dashboard** (a GUI to manage MySQL/MariaDB).
3. By default:

   * Username = `root`
   * Password = (leave blank)

---

## Step 3: Create a Database

1. In phpMyAdmin → click **Databases** tab.
2. Enter a database name (e.g., `mydb`).
3. Choose collation (UTF8 is good: `utf8_general_ci`).
4. Click **Create** ✅

---

## Step 4: Create a Table

1. Select your database (`mydb`).
2. Click **Create Table**.
   Example: `users` table with columns:

   * `id` (INT, Primary Key, Auto Increment)
   * `name` (VARCHAR(100))
   * `email` (VARCHAR(150))
   * `created_at` (TIMESTAMP)

---

## Step 5: Insert Data

* Use **Insert tab** in phpMyAdmin to add data manually.
* Or run an **SQL query**:

  ```sql
  INSERT INTO users (name, email, created_at) 
  VALUES ('Navjot', 'navjot@example.com', NOW());
  ```

---

## Step 6: Fetch Data

Run SQL query:

```sql
SELECT * FROM users;
```

---

## Step 7: Use Database with PHP (optional)

In your `htdocs` folder (`C:\xampp\htdocs\`), create a file `test.php`:

```php
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "mydb";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// Run query
$sql = "SELECT id, name, email FROM users";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "ID: " . $row["id"]. " - Name: " . $row["name"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "0 results";
}
$conn->close();
?>
```

👉 Save → Run in browser:

```
http://localhost/test.php
```
