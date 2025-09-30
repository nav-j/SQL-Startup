# Create Auto-Increment ID in phpMyAdmin

### ✅ Step 1: Open phpMyAdmin

* Start **XAMPP Control Panel** → Start **Apache** + **MySQL**.
* Go to your browser → [http://localhost/phpmyadmin/](http://localhost/phpmyadmin/).

---

### ✅ Step 2: Create a Database

1. Click on **Databases** tab.
2. Enter a name (e.g., `mydb`).
3. Choose collation → `utf8_general_ci`.
4. Click **Create** ✅.

---

### ✅ Step 3: Create a Table

1. Select your database (`mydb`).
2. Enter table name → `users`.
3. Number of columns → `4`.
4. Click **Go**.

---

### ✅ Step 4: Define Columns

Fill in the columns like this:

| Column Name | Type      | Length | Index   | A_I (Auto Increment) | Default           |
| ----------- | --------- | ------ | ------- | -------------------- | ----------------- |
| id          | INT       | 11     | PRIMARY | ✅ (check this box)   | —                 |
| name        | VARCHAR   | 100    | —       | —                    | —                 |
| email       | VARCHAR   | 150    | —       | —                    | —                 |
| created_at  | TIMESTAMP | —      | —       | —                    | CURRENT_TIMESTAMP |

⚡ Important:

* For `id`: check **A_I** (Auto Increment) and set it as **PRIMARY**.
* For `created_at`: set **Default → CURRENT_TIMESTAMP**.

Click **Save** ✅

---

### ✅ Step 5: Insert Data

1. Go to **Insert** tab.
2. Enter values for `name` and `email` only (leave `id` and `created_at` blank).
   Example:

   * Name = `Navjot`
   * Email = `navjot@example.com`
3. Click **Go**.

phpMyAdmin will automatically generate:

* `id = 1`
* `created_at = current time`

---

### ✅ Step 6: View Data

Click on **Browse** → You’ll see your records with auto-generated `id` and `created_at`. 🎉
