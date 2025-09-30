## Syntax for Auto Increment ID

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(150),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Explanation:

* `id INT AUTO_INCREMENT` → ID will automatically increase (1, 2, 3, …).
* `PRIMARY KEY` → ensures uniqueness.
* `created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP` → stores the time when record is added.

---

## Insert Data (No need to insert `id`)

```sql
INSERT INTO users (name, email) 
VALUES ('Navjot', 'navjot@example.com'),
       ('Aman', 'aman@example.com');
```

### Output in `users` table:

| id | name   | email                                           | created_at          |
| -- | ------ | ----------------------------------------------- | ------------------- |
| 1  | Navjot | [navjot@example.com](mailto:navjot@example.com) | 2025-09-29 11:20:00 |
| 2  | Aman   | [aman@example.com](mailto:aman@example.com)     | 2025-09-29 11:21:00 |

---

## Alter Existing Table to Add Auto Increment

If you already have a table without `AUTO_INCREMENT`, you can modify it:

```sql
ALTER TABLE users 
MODIFY id INT AUTO_INCREMENT PRIMARY KEY;
```

---

## Reset Auto Increment (optional)

If you delete rows and want to reset numbering:

```sql
ALTER TABLE users AUTO_INCREMENT = 1;
```

---
