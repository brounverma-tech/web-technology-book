# 🐬 Chapter 35: MySQL — Tables and CRUD Operations

> **BCA Web Technology — Beginner to Advanced**  
> Is chapter mein hum MySQL database par practical CRUD operations karenge.

---

## 🎯 Learning Objectives

Is chapter ke baad aap:

- MySQL server, client aur database ka role samjhenge;
- databases aur tables create, inspect aur modify karenge;
- suitable MySQL data types aur constraints choose karenge;
- `INSERT`, `SELECT`, `UPDATE` aur `DELETE` se CRUD operations karenge;
- filtering, sorting, pagination aur aggregate functions use karenge;
- safe query practices aur common errors identify karenge;
- ek complete **Student Management Database** practical bana payenge.

---

## 1. 🐬 MySQL Kya Hai?

**MySQL** *(माई-एस-क्यू-एल)* ek relational database management system hai. Yeh data ko related tables mein store karta hai aur SQL commands ke through manage karta hai.

MySQL ka use websites, content-management systems, e-commerce applications aur business software mein hota hai.

### MySQL Environment ke Main Parts

| Part | Kaam |
|---|---|
| MySQL Server | Databases aur queries process karta hai |
| MySQL Client | Server ko commands bhejta hai |
| MySQL Workbench | Graphical interface |
| Command Line Client | Terminal se SQL chalata hai |
| Database | Related tables ka collection |
| Table | Rows aur columns mein structured data |

> 💡 **Pronunciation:** Query *(क्वेरी)*, Schema *(स्कीमा)*, Constraint *(कन्स्ट्रेन्ट)*, Aggregate *(एग्रीगेट)*.

---

## 2. 🔌 MySQL Se Connect Karna

Command line se connection:

```bash
mysql -u root -p
```

- `-u root`: username;
- `-p`: password prompt;
- password command mein directly likhna avoid karein.

Connection ke baad version dekhne ke liye:

```sql
SELECT VERSION();
```

Server se bahar aane ke liye:

```sql
EXIT;
```

> ⚠️ Production application ko `root` account se connect na karein. Minimum permissions wala separate user use karein.

---

## 3. 🗃️ Database Operations

### 3.1 Databases Dekhna

```sql
SHOW DATABASES;
```

### 3.2 Database Create Karna

```sql
CREATE DATABASE student_management
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

`utf8mb4` multilingual text aur emoji store kar sakta hai.

### 3.3 Database Select Karna

```sql
USE student_management;
```

Current database:

```sql
SELECT DATABASE();
```

### 3.4 Database Delete Karna

```sql
DROP DATABASE student_management;
```

> 🚨 `DROP DATABASE` poora database delete karta hai. Practice database par hi use karein aur important data ka backup rakhein.

---

## 4. 🧱 Table Create Karna

```sql
CREATE TABLE students (
    student_id INT UNSIGNED AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL,
    phone VARCHAR(15),
    date_of_birth DATE,
    course VARCHAR(50) NOT NULL,
    semester TINYINT UNSIGNED NOT NULL,
    fees DECIMAL(10, 2) NOT NULL DEFAULT 0.00,
    active BOOLEAN NOT NULL DEFAULT TRUE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,

    CONSTRAINT pk_students PRIMARY KEY (student_id),
    CONSTRAINT uq_students_email UNIQUE (email),
    CONSTRAINT chk_students_semester
        CHECK (semester BETWEEN 1 AND 8),
    CONSTRAINT chk_students_fees
        CHECK (fees >= 0)
);
```

### Structure Samjhein

| Definition | Meaning |
|---|---|
| `AUTO_INCREMENT` | New row ko automatic increasing number |
| `NOT NULL` | Value dena compulsory |
| `DEFAULT` | Value absent ho to predefined value |
| `PRIMARY KEY` | Har row ki unique identity |
| `UNIQUE` | Duplicate value prevent |
| `CHECK` | Condition enforce |
| `CURRENT_TIMESTAMP` | Current date-time automatically |

> 📌 `BOOLEAN` MySQL mein usually numeric truth value ke roop mein handled hota hai: zero false aur nonzero true.

---

## 5. 🔢 Important MySQL Data Types

### Numeric Types

| Type | Use |
|---|---|
| `TINYINT` | Small whole numbers |
| `INT` | General whole numbers |
| `BIGINT` | Very large whole numbers |
| `DECIMAL(p,s)` | Exact decimal, especially money |
| `FLOAT` / `DOUBLE` | Approximate decimal/scientific values |

`DECIMAL(10,2)` mein maximum 10 total digits aur decimal ke baad 2 digits hote hain.

### String Types

| Type | Use |
|---|---|
| `CHAR(n)` | Fixed-length text |
| `VARCHAR(n)` | Variable-length text |
| `TEXT` | Long text |
| `ENUM` | Fixed allowed string list; portability/design carefully consider karein |
| `BLOB` | Binary data |

### Date and Time Types

| Type | Example |
|---|---|
| `DATE` | `2026-08-30` |
| `TIME` | `14:30:00` |
| `DATETIME` | `2026-08-30 14:30:00` |
| `TIMESTAMP` | Commonly created/updated time tracking |
| `YEAR` | `2026` |

> ✅ Database mein file/image bytes store kiye ja sakte hain, lekin web apps often file storage mein file aur database mein uska path/metadata rakhte hain.

---

## 6. 🔍 Table Inspect Karna

```sql
SHOW TABLES;

DESCRIBE students;

SHOW CREATE TABLE students;
```

- `SHOW TABLES` current database ki tables dikhata hai;
- `DESCRIBE` columns, types aur keys ka quick view deta hai;
- `SHOW CREATE TABLE` exact table definition dikhata hai.

---

## 7. 🛠️ ALTER TABLE

Existing table ki structure change karne ke liye `ALTER TABLE` use hota hai.

### Column Add

```sql
ALTER TABLE students
ADD COLUMN city VARCHAR(60) AFTER phone;
```

### Column Modify

```sql
ALTER TABLE students
MODIFY COLUMN phone VARCHAR(20);
```

### Column Rename

```sql
ALTER TABLE students
RENAME COLUMN course TO program;
```

### Column Drop

```sql
ALTER TABLE students
DROP COLUMN date_of_birth;
```

### Table Rename

```sql
RENAME TABLE students TO college_students;
RENAME TABLE college_students TO students;
```

> ⚠️ Structure changes se data loss ya application break ho sakti hai. Production mein backup, migration aur testing zaroor karein.

---

## 8. ♻️ CRUD Ka Meaning

CRUD four basic data operations ka short form hai:

| Letter | Operation | SQL |
|---|---|---|
| C | Create record | `INSERT` |
| R | Read record | `SELECT` |
| U | Update record | `UPDATE` |
| D | Delete record | `DELETE` |

```mermaid
flowchart LR
    C["Create<br/>INSERT"] --> R["Read<br/>SELECT"]
    R --> U["Update<br/>UPDATE"]
    U --> D["Delete<br/>DELETE"]
```

---

## 9. ➕ CREATE: INSERT Operations

### Single Row Insert

```sql
INSERT INTO students
(name, email, phone, city, program, semester, fees)
VALUES
('Aditi Sharma', 'aditi@example.com', '9876543210',
 'Delhi', 'BCA', 1, 25000.00);
```

### Multiple Rows Insert

```sql
INSERT INTO students
(name, email, phone, city, program, semester, fees, active)
VALUES
('Rahul Verma', 'rahul@example.com', '9876500011',
 'Jaipur', 'BCA', 3, 26000.00, TRUE),
('Neha Singh', 'neha@example.com', NULL,
 'Lucknow', 'BCA', 5, 27500.00, TRUE),
('Arjun Kumar', 'arjun@example.com', '9876500033',
 NULL, 'BCA', 2, 25500.00, FALSE);
```

### Insert Result Check

```sql
SELECT LAST_INSERT_ID();
```

> ✅ Column names explicitly likhna safer hai. Table structure change hone par query samajhna aur maintain karna easy rehta hai.

---

## 10. 👀 READ: SELECT Operations

### All Columns

```sql
SELECT * FROM students;
```

### Selected Columns

```sql
SELECT student_id, name, email
FROM students;
```

Production queries mein required columns hi select karna generally better hai.

### Alias

```sql
SELECT
    name AS student_name,
    fees AS annual_fees
FROM students;
```

### Unique Values

```sql
SELECT DISTINCT city
FROM students;
```

---

## 11. 🎯 WHERE Se Filtering

### Comparison Operators

```sql
SELECT name, semester
FROM students
WHERE semester >= 3;
```

Operators: `=`, `<>` or `!=`, `>`, `<`, `>=`, `<=`.

### Logical Operators

```sql
SELECT name, city, semester
FROM students
WHERE program = 'BCA'
  AND semester >= 3
  AND active = TRUE;
```

`AND`, `OR` aur `NOT` conditions combine karte hain. Parentheses se intended logic clear karein.

### BETWEEN

```sql
SELECT name, fees
FROM students
WHERE fees BETWEEN 25000 AND 27000;
```

`BETWEEN` dono boundaries include karta hai.

### IN

```sql
SELECT name, city
FROM students
WHERE city IN ('Delhi', 'Jaipur', 'Lucknow');
```

### LIKE Pattern Matching

```sql
SELECT name
FROM students
WHERE name LIKE 'A%';
```

- `%`: zero ya many characters;
- `_`: exactly one character.

Examples:

```sql
WHERE name LIKE '%Kumar%'
WHERE name LIKE '_eha%'
```

### NULL Check

```sql
SELECT name
FROM students
WHERE phone IS NULL;

SELECT name
FROM students
WHERE city IS NOT NULL;
```

`NULL` ke saath `=` ya `!=` use nahi karna chahiye.

---

## 12. ↕️ Sorting aur Pagination

### ORDER BY

```sql
SELECT name, semester, fees
FROM students
ORDER BY semester ASC, name ASC;
```

- `ASC`: ascending, default;
- `DESC`: descending.

### LIMIT aur OFFSET

```sql
SELECT student_id, name
FROM students
ORDER BY student_id
LIMIT 10 OFFSET 0;
```

Next page:

```sql
SELECT student_id, name
FROM students
ORDER BY student_id
LIMIT 10 OFFSET 10;
```

> 📌 Pagination ke saath stable `ORDER BY` rakhein, warna page results inconsistent ho sakte hain.

---

## 13. ✏️ UPDATE Operations

### One Student Update

```sql
UPDATE students
SET city = 'Noida',
    fees = 26500.00
WHERE student_id = 1;
```

### Multiple Matching Rows Update

```sql
UPDATE students
SET fees = fees + 1000
WHERE program = 'BCA'
  AND active = TRUE;
```

### Safe Update Workflow

```sql
-- 1. Pehle affected rows check karein
SELECT student_id, name, fees
FROM students
WHERE program = 'BCA' AND active = TRUE;

-- 2. Phir same condition se update karein
UPDATE students
SET fees = fees + 1000
WHERE program = 'BCA' AND active = TRUE;

-- 3. Result verify karein
SELECT student_id, name, fees
FROM students
WHERE program = 'BCA' AND active = TRUE;
```

> 🚨 `UPDATE students SET active = FALSE;` sab rows change kar dega, kyunki `WHERE` absent hai.

---

## 14. 🗑️ DELETE Operations

### Selected Row Delete

```sql
DELETE FROM students
WHERE student_id = 4;
```

### Matching Rows Delete

```sql
DELETE FROM students
WHERE active = FALSE;
```

### All Rows Delete

```sql
DELETE FROM students;
```

### DELETE vs TRUNCATE vs DROP

| Command | Data | Table Structure | Filter |
|---|---|---|---|
| `DELETE` | Selected/all rows remove | Remains | `WHERE` possible |
| `TRUNCATE TABLE` | All rows remove | Remains | No |
| `DROP TABLE` | All data remove | Removed | No |

Exact transaction aur auto-increment behavior MySQL version, engine aur context ke according check karein.

---

## 15. 🧮 Aggregate Functions

Aggregate functions multiple rows se single summary value banati hain.

```sql
SELECT
    COUNT(*) AS total_students,
    AVG(fees) AS average_fees,
    MIN(fees) AS minimum_fees,
    MAX(fees) AS maximum_fees,
    SUM(fees) AS total_fees
FROM students;
```

### GROUP BY

```sql
SELECT
    semester,
    COUNT(*) AS total_students,
    AVG(fees) AS average_fees
FROM students
GROUP BY semester
ORDER BY semester;
```

### HAVING

```sql
SELECT
    city,
    COUNT(*) AS total_students
FROM students
WHERE active = TRUE
GROUP BY city
HAVING COUNT(*) >= 2;
```

| Clause | Filters |
|---|---|
| `WHERE` | Grouping se pehle individual rows |
| `HAVING` | Grouping ke baad groups |

> 🧠 `COUNT(*)` rows count karta hai. `COUNT(phone)` sirf non-NULL phone values count karta hai.

---

## 16. 🔤 Useful String, Numeric aur Date Functions

```sql
SELECT
    UPPER(name) AS uppercase_name,
    LOWER(email) AS lowercase_email,
    CHAR_LENGTH(name) AS name_length
FROM students;
```

```sql
SELECT
    fees,
    ROUND(fees / 12, 2) AS monthly_fees
FROM students;
```

```sql
SELECT
    name,
    created_at,
    DATE(created_at) AS created_date,
    YEAR(created_at) AS created_year
FROM students;
```

Functions DBMS-specific ho sakte hain. Portable application banate waqt official documentation check karein.

---

## 17. 🔐 Safe CRUD Practices

### SQL Injection Risk

Unsafe application logic:

```php
// Unsafe concept — user input query mein jod diya
$sql = "SELECT * FROM students WHERE email = '$email'";
```

Safe prepared statement:

```php
$stmt = $pdo->prepare(
    'SELECT * FROM students WHERE email = ?'
);
$stmt->execute([$email]);
$student = $stmt->fetch();
```

Prepared statements user data ko SQL code se separate rakhte hain.

### Important Safety Rules

- application ke liye limited-privilege database user banayein;
- input validate karein, par security ke liye prepared statements bhi use karein;
- production errors mein passwords/query secrets show na karein;
- mass update/delete transaction ke andar test karein;
- regular backups lein aur restoration verify karein;
- sensitive data public GitHub repository mein upload na karein.

---

## 18. 🧪 Complete Practical: Student Management Database

### Step 1: Fresh Database

```sql
CREATE DATABASE IF NOT EXISTS student_management
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;

USE student_management;
```

### Step 2: Departments Table

```sql
CREATE TABLE departments (
    department_id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    department_name VARCHAR(100) NOT NULL UNIQUE,
    office_phone VARCHAR(20)
);
```

### Step 3: Students Table

```sql
CREATE TABLE students (
    student_id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    roll_number VARCHAR(20) NOT NULL UNIQUE,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL UNIQUE,
    city VARCHAR(60),
    semester TINYINT UNSIGNED NOT NULL,
    fees DECIMAL(10, 2) NOT NULL DEFAULT 0.00,
    department_id INT UNSIGNED NOT NULL,
    active BOOLEAN NOT NULL DEFAULT TRUE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,

    CONSTRAINT chk_semester CHECK (semester BETWEEN 1 AND 8),
    CONSTRAINT chk_fees CHECK (fees >= 0),
    CONSTRAINT fk_student_department
        FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);
```

### Step 4: Sample Data

```sql
INSERT INTO departments
(department_name, office_phone)
VALUES
('Computer Applications', '011-40001001'),
('Commerce', '011-40001002');

INSERT INTO students
(roll_number, name, email, city, semester, fees, department_id)
VALUES
('BCA-101', 'Aditi Sharma', 'aditi@example.com',
 'Delhi', 1, 25000.00, 1),
('BCA-102', 'Rahul Verma', 'rahul@example.com',
 'Jaipur', 3, 26000.00, 1),
('BCA-103', 'Neha Singh', 'neha@example.com',
 'Lucknow', 5, 27500.00, 1),
('BCOM-101', 'Aman Gupta', 'aman@example.com',
 'Delhi', 1, 22000.00, 2);
```

### Step 5: CRUD Queries

```sql
-- CREATE
INSERT INTO students
(roll_number, name, email, city, semester, fees, department_id)
VALUES
('BCA-104', 'Sara Khan', 'sara@example.com',
 'Agra', 2, 25500.00, 1);

-- READ
SELECT student_id, roll_number, name, semester
FROM students
WHERE department_id = 1
ORDER BY semester, name;

-- UPDATE
UPDATE students
SET city = 'Noida', semester = 2
WHERE roll_number = 'BCA-101';

-- DELETE
DELETE FROM students
WHERE roll_number = 'BCA-104';
```

### Step 6: Reports

```sql
-- Semester-wise report
SELECT
    semester,
    COUNT(*) AS students,
    ROUND(AVG(fees), 2) AS average_fees
FROM students
WHERE active = TRUE
GROUP BY semester
ORDER BY semester;

-- Search by name
SELECT roll_number, name, email
FROM students
WHERE name LIKE '%Verma%';

-- Highest fee first
SELECT roll_number, name, fees
FROM students
ORDER BY fees DESC
LIMIT 3;
```

### Step 7: Test Constraints

In commands ko separately run karke error observe karein:

```sql
-- Duplicate email: UNIQUE error
INSERT INTO students
(roll_number, name, email, semester, fees, department_id)
VALUES
('BCA-999', 'Test User', 'aditi@example.com', 1, 1000, 1);

-- Invalid semester: CHECK error
UPDATE students
SET semester = 10
WHERE roll_number = 'BCA-101';

-- Missing department: FOREIGN KEY error
INSERT INTO students
(roll_number, name, email, semester, fees, department_id)
VALUES
('BCA-998', 'Demo User', 'demo@example.com', 1, 1000, 999);
```

> ✅ Errors bhi learning ka part hain. Error message read karke constraint aur offending value identify karein.

---

## 19. 🐞 Common Errors and Solutions

| Problem | Possible Reason | Solution |
|---|---|---|
| No database selected | `USE` nahi chalaya | `USE database_name;` |
| Table doesn't exist | Name/database wrong | `SHOW TABLES;` check karein |
| Duplicate entry | Primary/unique value repeat | Unique value use karein |
| Cannot add/update child row | Invalid foreign key | Parent row pehle create karein |
| Column cannot be null | Required value absent | `NOT NULL` column ki value dein |
| Data too long | Column size small | Input/type inspect karein |
| Unknown column | Typo ya wrong alias | `DESCRIBE table;` use karein |
| Safe update restriction | Key-based condition absent | Precise key condition use karein |

---

## 20. ✅ Best-Practice Checklist

- [ ] Database aur tables ke clear names rakhe?
- [ ] Har table mein primary key hai?
- [ ] Money ke liye `DECIMAL` use kiya?
- [ ] Required fields par `NOT NULL` hai?
- [ ] Duplicate business values par `UNIQUE` hai?
- [ ] Relationships foreign keys se enforce ki?
- [ ] CRUD se pehle correct database select kiya?
- [ ] `UPDATE`/`DELETE` ka `WHERE` pehle `SELECT` se test kiya?
- [ ] Application mein prepared statements use kiye?
- [ ] Backup aur restore process tested hai?

---

## 21. 🧾 Chapter Summary

- MySQL ek relational database management system hai.
- `CREATE DATABASE` aur `CREATE TABLE` structure banate hain.
- Correct data types storage, validation aur calculations improve karte hain.
- `ALTER TABLE` existing structure modify karta hai.
- CRUD ka meaning Create, Read, Update aur Delete hai.
- `INSERT` rows add, `SELECT` read, `UPDATE` change aur `DELETE` remove karta hai.
- `WHERE` filtering, `ORDER BY` sorting aur `LIMIT` result size control karta hai.
- Aggregate functions summary banati hain; `GROUP BY` groups aur `HAVING` grouped result filter karta hai.
- Constraints invalid aur duplicate data prevent karti hain.
- Prepared statements, least privilege aur backups safe database applications ke liye essential hain.

---

## 22. 📝 MCQs

1. MySQL mein automatic numeric ID ke liye kya use hota hai?  
   A. `AUTO_INCREMENT`  B. `AUTO_ID`  C. `SERIALIZE`  D. `COUNT`

2. CRUD mein R ka meaning hai:  
   A. Remove  B. Read  C. Rename  D. Restore

3. Duplicate email prevent karne ke liye suitable constraint hai:  
   A. `DEFAULT`  B. `UNIQUE`  C. `ORDER BY`  D. `LIMIT`

4. Result sort karne ke liye use hota hai:  
   A. `GROUP BY`  B. `SORT`  C. `ORDER BY`  D. `ARRANGE`

5. Grouped result ko filter karta hai:  
   A. `HAVING`  B. `VALUES`  C. `SET`  D. `USE`

6. Missing value ka correct test hai:  
   A. `= NULL`  B. `IS NULL`  C. `== NULL`  D. `NULL = TRUE`

7. SQL injection se protection ka important method hai:  
   A. More columns  B. Prepared statements  C. Longer IDs  D. `SELECT *`

**Answers:** 1-A, 2-B, 3-B, 4-C, 5-A, 6-B, 7-B

---

## 23. ✏️ Fill in the Blanks

1. Current database select karne ka command ______ hai.
2. Existing row change karne ke liye ______ command use hota hai.
3. All rows ki count ke liye ______ function use hota hai.
4. Result ki maximum rows control karne ke liye ______ clause use hota hai.
5. Table structure dekhne ke liye ______ command use kiya ja sakta hai.

**Answers:** 1. `USE`, 2. `UPDATE`, 3. `COUNT(*)`, 4. `LIMIT`, 5. `DESCRIBE`

---

## 24. ✔️ True or False

1. `VARCHAR` variable-length text ke liye use hota hai. — **True**
2. `UPDATE` without `WHERE` sirf first row change karta hai. — **False**
3. `BETWEEN` boundary values include karta hai. — **True**
4. `COUNT(column)` NULL values bhi count karta hai. — **False**
5. Prepared statements user data ko SQL code se separate rakhte hain. — **True**

---

## 25. 🎤 Viva Questions

1. MySQL server aur client mein kya difference hai?
2. `utf8mb4` use karne ka kya benefit hai?
3. `CHAR` aur `VARCHAR` compare karein.
4. `AUTO_INCREMENT` kya karta hai?
5. CRUD ko SQL commands se map karein.
6. `WHERE` aur `HAVING` mein difference kya hai?
7. `COUNT(*)` aur `COUNT(column)` mein kya difference hai?
8. `LIKE` mein `%` aur `_` kya represent karte hain?
9. `DELETE`, `TRUNCATE` aur `DROP` compare karein.
10. Mass update se pehle `SELECT` kyun run karna chahiye?
11. Prepared statement kya hai?
12. Foreign key error kab aata hai?

---

## 26. 🧪 Practical Exercises

### Beginner

1. `shop_db` database create karein.
2. `products` table banayein: ID, name, category, price, stock aur created time.
3. Five products insert karein.
4. Price ke descending order mein products show karein.
5. ₹500–₹2000 ke products filter karein.

### Intermediate

6. Ek product ki price aur stock update karein.
7. Zero-stock products delete karein.
8. Category-wise product count aur average price nikalein.
9. Product names mein keyword search karein.
10. Results ko five rows per page paginate karein.

### Advanced

11. `categories` table banakar products se foreign key connect karein.
12. Invalid category aur duplicate product code insert karke errors study karein.
13. Transaction ke andar bulk price update karke `ROLLBACK` test karein.
14. PHP PDO prepared statements se complete CRUD page banayein.

---

## 27. 📖 Exam-Oriented Questions

### Short Answer

1. MySQL ke main features likhiye.
2. MySQL numeric aur string data types examples ke saath likhiye.
3. CRUD define karke commands batayiye.
4. `WHERE`, `ORDER BY` aur `LIMIT` explain kijiye.
5. Aggregate functions kya hain?

### Long Answer

1. MySQL mein database aur constrained table create karne ki complete process explain kijiye.
2. `INSERT`, `SELECT`, `UPDATE` aur `DELETE` examples ke saath explain kijiye.
3. Filtering operators, pattern matching aur NULL handling describe kijiye.
4. `GROUP BY` aur `HAVING` ko suitable example se samjhaiye.
5. Student Management Database design aur implement kijiye.

---

## 28. 🔁 One-Minute Revision

```text
SHOW DATABASES → databases list
CREATE DATABASE → new database
USE → database select
CREATE TABLE → new table
DESCRIBE → table structure
ALTER TABLE → structure change
INSERT → create row
SELECT → read rows
UPDATE → modify rows
DELETE → remove rows
WHERE → row filter
ORDER BY → sorting
LIMIT → result limit
GROUP BY → groups
HAVING → group filter
```

---

## 29. 🔗 Official References

- [MySQL Tutorial](https://dev.mysql.com/doc/refman/en/tutorial.html)
- [MySQL CREATE TABLE Statement](https://dev.mysql.com/doc/refman/en/create-table.html)
- [MySQL INSERT Statement](https://dev.mysql.com/doc/refman/en/insert.html)
- [MySQL SELECT Statement](https://dev.mysql.com/doc/refman/en/select.html)
- [MySQL UPDATE Statement](https://dev.mysql.com/doc/refman/en/update.html)
- [MySQL DELETE Statement](https://dev.mysql.com/doc/refman/en/delete.html)

---

[⬅️ Previous Chapter](34-database-and-sql-fundamentals.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: Joins, Keys and Relationships ➡️**
