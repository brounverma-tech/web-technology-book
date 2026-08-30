# 💻 Appendix C: Practical Programs

> **BCA Web Technology — Practical File Companion**  
> Beginner se advanced tak lab-ready programs with aim, code, expected result aur viva points.

---

## 🎯 Practical Work Ka Format

Har practical file mein yeh headings likhein:

1. **Practical Number**
2. **Aim**
3. **Requirements**
4. **Algorithm / Steps**
5. **Source Code**
6. **Expected Output**
7. **Test Cases**
8. **Result**
9. **Viva Questions**

> ✅ Code run karke khud screenshot/output attach karein. Sirf copy karna practical learning nahi hai.

---

# Part A — HTML and CSS Practicals

## Practical 1: Semantic Personal Profile Page

### Aim

Semantic HTML se accessible profile page banana.

### Code — `profile.html`

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Aditi Sharma | Student Profile</title>
  <meta
    name="description"
    content="BCA student profile of Aditi Sharma."
  >
</head>
<body>
  <header>
    <h1>Aditi Sharma</h1>
    <p>BCA Student and Web Development Learner</p>
  </header>

  <nav aria-label="Profile navigation">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#contact">Contact</a>
  </nav>

  <main>
    <section id="about">
      <h2>About Me</h2>
      <p>
        I am learning HTML, CSS, JavaScript, PHP and MySQL.
      </p>
    </section>

    <section id="skills">
      <h2>Skills</h2>
      <ul>
        <li>Semantic HTML</li>
        <li>Responsive CSS</li>
        <li>JavaScript Fundamentals</li>
      </ul>
    </section>

    <section id="contact">
      <h2>Contact</h2>
      <address>
        Email:
        <a href="mailto:aditi@example.com">
          aditi@example.com
        </a>
      </address>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 Aditi Sharma</p>
  </footer>
</body>
</html>
```

### Expected Result

Browser mein structured header, navigation, main sections and footer dikhenge.

### Viva

- Semantic HTML kya hai?
- `main` aur `section` ka purpose kya hai?
- Email link ka protocol kya hai?

---

## Practical 2: Student Marksheet Table

### Aim

Accessible table mein marks and total show karna.

```html
<table>
  <caption>BCA Semester 1 Marksheet</caption>
  <thead>
    <tr>
      <th scope="col">Subject</th>
      <th scope="col">Maximum</th>
      <th scope="col">Obtained</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Web Technology</th>
      <td>100</td>
      <td>88</td>
    </tr>
    <tr>
      <th scope="row">Programming</th>
      <td>100</td>
      <td>82</td>
    </tr>
    <tr>
      <th scope="row">Mathematics</th>
      <td>100</td>
      <td>76</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row">Total</th>
      <td>300</td>
      <td>246</td>
    </tr>
  </tfoot>
</table>
```

### Expected Result

Subjects, maximum/obtained marks and total structured table mein show honge.

---

## Practical 3: Accessible Registration Form

### Aim

Different input controls ke saath student registration form banana.

```html
<form action="register.php" method="post">
  <div>
    <label for="roll">Roll Number</label>
    <input
      id="roll"
      name="roll_number"
      type="text"
      pattern="[A-Z0-9-]{3,20}"
      required
    >
  </div>

  <div>
    <label for="name">Full Name</label>
    <input
      id="name"
      name="name"
      type="text"
      minlength="2"
      maxlength="100"
      autocomplete="name"
      required
    >
  </div>

  <div>
    <label for="email">Email</label>
    <input
      id="email"
      name="email"
      type="email"
      autocomplete="email"
      required
    >
  </div>

  <div>
    <label for="course">Course</label>
    <select id="course" name="course" required>
      <option value="">Select course</option>
      <option value="BCA">BCA</option>
      <option value="BBA">BBA</option>
      <option value="BCOM">B.Com</option>
    </select>
  </div>

  <fieldset>
    <legend>Study Mode</legend>
    <label>
      <input type="radio" name="mode" value="regular" required>
      Regular
    </label>
    <label>
      <input type="radio" name="mode" value="online">
      Online
    </label>
  </fieldset>

  <label>
    <input type="checkbox" name="terms" value="1" required>
    I accept the terms.
  </label>

  <button type="submit">Register</button>
</form>
```

### Test Cases

- valid form;
- empty required field;
- invalid email;
- lowercase/invalid roll pattern;
- terms unchecked.

---

## Practical 4: Colorful Responsive Card Grid

### Aim

CSS Grid se responsive course cards banana.

### HTML

```html
<main class="container">
  <h1>Our Courses</h1>

  <div class="course-grid">
    <article class="card">
      <h2>BCA</h2>
      <p>Computer applications and web development.</p>
      <a href="#">View Course</a>
    </article>

    <article class="card">
      <h2>BBA</h2>
      <p>Business administration and management.</p>
      <a href="#">View Course</a>
    </article>

    <article class="card">
      <h2>B.Com</h2>
      <p>Commerce, accounting and finance.</p>
      <a href="#">View Course</a>
    </article>
  </div>
</main>
```

### CSS

```css
:root {
  --primary: #2563eb;
  --secondary: #7c3aed;
  --surface: #ffffff;
  --text: #172033;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: system-ui, sans-serif;
  color: var(--text);
  background:
    linear-gradient(135deg, #dbeafe, #f3e8ff);
}

.container {
  width: min(1100px, 92%);
  margin: 3rem auto;
}

.course-grid {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.25rem;
}

.card {
  padding: 1.5rem;
  border-radius: 1rem;
  background: var(--surface);
  box-shadow: 0 14px 35px rgb(15 23 42 / 12%);
  transition:
    transform 180ms ease,
    box-shadow 180ms ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 18px 40px rgb(37 99 235 / 18%);
}

.card a {
  display: inline-block;
  padding: 0.65rem 1rem;
  border-radius: 0.6rem;
  color: white;
  background:
    linear-gradient(90deg, var(--primary), var(--secondary));
  text-decoration: none;
}

.card a:focus-visible {
  outline: 3px solid #f59e0b;
  outline-offset: 3px;
}
```

### Expected Result

Cards available width ke according columns change karengi.

---

## Practical 5: Flexbox Navigation Bar

### Aim

Responsive navigation with Flexbox.

```html
<nav class="navbar" aria-label="Main navigation">
  <a class="brand" href="#">College Connect</a>

  <div class="nav-links">
    <a href="#">Home</a>
    <a href="#">Courses</a>
    <a href="#">Contact</a>
    <a class="login" href="#">Login</a>
  </div>
</nav>
```

```css
.navbar,
.nav-links {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.navbar {
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 1rem 5%;
  background: #172033;
}

.navbar a {
  color: white;
  text-decoration: none;
}

.brand {
  font-size: 1.25rem;
  font-weight: 800;
}

.login {
  padding: 0.5rem 0.8rem;
  border-radius: 0.5rem;
  background: #2563eb;
}

@media (max-width: 600px) {
  .navbar,
  .nav-links {
    flex-direction: column;
    align-items: stretch;
  }
}
```

---

# Part B — JavaScript Practicals

## Practical 6: Simple Calculator

### Aim

Functions, DOM and events se calculator banana.

```html
<label for="first">First Number</label>
<input id="first" type="number">

<label for="second">Second Number</label>
<input id="second" type="number">

<button type="button" data-operation="add">Add</button>
<button type="button" data-operation="subtract">Subtract</button>
<button type="button" data-operation="multiply">Multiply</button>
<button type="button" data-operation="divide">Divide</button>

<p id="result" role="status"></p>

<script>
  const first = document.querySelector("#first");
  const second = document.querySelector("#second");
  const result = document.querySelector("#result");

  document.addEventListener("click", (event) => {
    const operation = event.target.dataset.operation;

    if (!operation) return;

    const a = Number(first.value);
    const b = Number(second.value);

    if (!Number.isFinite(a) || !Number.isFinite(b)) {
      result.textContent = "Enter two valid numbers.";
      return;
    }

    const operations = {
      add: () => a + b,
      subtract: () => a - b,
      multiply: () => a * b,
      divide: () => b === 0 ? "Cannot divide by zero" : a / b,
    };

    result.textContent = `Result: ${operations[operation]()}`;
  });
</script>
```

### Test Cases

`10 + 5`, `10 - 5`, `10 × 5`, `10 ÷ 0`, empty input.

---

## Practical 7: Grade Calculator

### Aim

Conditions se percentage and grade calculate karna.

```javascript
function calculateGrade(marks) {
  if (
    !Array.isArray(marks) ||
    marks.length === 0 ||
    marks.some((mark) =>
      !Number.isFinite(mark) || mark < 0 || mark > 100
    )
  ) {
    throw new Error("Marks must be between 0 and 100.");
  }

  const total = marks.reduce((sum, mark) => sum + mark, 0);
  const percentage = total / marks.length;

  let grade;

  if (percentage >= 75) grade = "A";
  else if (percentage >= 60) grade = "B";
  else if (percentage >= 50) grade = "C";
  else if (percentage >= 40) grade = "D";
  else grade = "F";

  return {
    total,
    percentage: percentage.toFixed(2),
    grade,
    result: percentage >= 40 ? "Pass" : "Fail",
  };
}

console.log(calculateGrade([88, 82, 76, 91, 79]));
```

---

## Practical 8: Array Statistics

### Aim

Array methods se total, average, highest and lowest find karna.

```javascript
const marks = [78, 91, 66, 84, 89];

const total = marks.reduce((sum, mark) => sum + mark, 0);
const average = total / marks.length;
const highest = Math.max(...marks);
const lowest = Math.min(...marks);
const passed = marks.filter((mark) => mark >= 40);

console.table({
  total,
  average,
  highest,
  lowest,
  passedSubjects: passed.length,
});
```

### Expected Result

Console table mein summary values show hongi.

---

## Practical 9: DOM To-Do List

### Aim

DOM creation, arrays and event delegation use karna.

```html
<form id="todo-form">
  <label for="task">New Task</label>
  <input id="task" name="task" required>
  <button type="submit">Add</button>
</form>

<ul id="todo-list"></ul>

<script>
  const form = document.querySelector("#todo-form");
  const input = document.querySelector("#task");
  const list = document.querySelector("#todo-list");

  form.addEventListener("submit", (event) => {
    event.preventDefault();

    const text = input.value.trim();

    if (text === "") return;

    const item = document.createElement("li");
    const label = document.createElement("span");
    const button = document.createElement("button");

    label.textContent = text;
    button.type = "button";
    button.textContent = "Delete";
    button.dataset.action = "delete";

    item.append(label, " ", button);
    list.append(item);

    form.reset();
    input.focus();
  });

  list.addEventListener("click", (event) => {
    if (event.target.dataset.action === "delete") {
      event.target.closest("li")?.remove();
    }
  });
</script>
```

---

## Practical 10: Client-Side Registration Validation

### Aim

Form submit se pehle clear validation errors show karna.

```javascript
const form = document.querySelector("#register-form");
const status = document.querySelector("#form-status");

form.addEventListener("submit", (event) => {
  event.preventDefault();

  const data = new FormData(form);
  const name = String(data.get("name") ?? "").trim();
  const email = String(data.get("email") ?? "").trim();
  const semester = Number(data.get("semester"));

  const errors = [];

  if (name.length < 2) {
    errors.push("Name must have at least 2 characters.");
  }

  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
    errors.push("Enter a valid email.");
  }

  if (!Number.isInteger(semester) || semester < 1 || semester > 8) {
    errors.push("Semester must be between 1 and 8.");
  }

  if (errors.length > 0) {
    status.textContent = errors.join(" ");
    return;
  }

  status.textContent = "Client validation passed.";
  // Server par submit/fetch still required.
});
```

> Server validation must repeat all important rules.

---

## Practical 11: Fetch JSON and Render Cards

### Aim

Fetch API se JSON data load and safe DOM render karna.

### `students.json`

```json
{
  "students": [
    {
      "id": 101,
      "name": "Aditi Sharma",
      "course": "BCA"
    },
    {
      "id": 102,
      "name": "Rahul Verma",
      "course": "BCA"
    }
  ]
}
```

### JavaScript

```javascript
async function loadStudents() {
  const list = document.querySelector("#students");
  const status = document.querySelector("#status");

  status.textContent = "Loading…";

  try {
    const response = await fetch("./students.json");

    if (!response.ok) {
      throw new Error(`HTTP ${response.status}`);
    }

    const data = await response.json();
    const fragment = document.createDocumentFragment();

    for (const student of data.students) {
      const card = document.createElement("article");
      const heading = document.createElement("h2");
      const course = document.createElement("p");

      heading.textContent = student.name;
      course.textContent = `Course: ${student.course}`;

      card.append(heading, course);
      fragment.append(card);
    }

    list.replaceChildren(fragment);
    status.textContent = `${data.students.length} students loaded.`;
  } catch (error) {
    console.error(error);
    status.textContent = "Students could not be loaded.";
  }
}

loadStudents();
```

---

# Part C — PHP Practicals

## Practical 12: PHP Grade Program

### Aim

PHP condition and function se grade calculate karna.

```php
<?php
declare(strict_types=1);

function grade(float $percentage): string
{
    return match (true) {
        $percentage < 0 || $percentage > 100
            => 'Invalid percentage',
        $percentage >= 75 => 'A',
        $percentage >= 60 => 'B',
        $percentage >= 50 => 'C',
        $percentage >= 40 => 'D',
        default => 'F',
    };
}

$percentage = 82.5;

echo "Percentage: $percentage%<br>";
echo 'Grade: ' . grade($percentage);
```

---

## Practical 13: Secure PHP Form Processing

### Aim

POST method, validation and escaped output use karna.

```php
<?php
declare(strict_types=1);

function e(?string $value): string
{
    return htmlspecialchars(
        $value ?? '',
        ENT_QUOTES | ENT_SUBSTITUTE,
        'UTF-8'
    );
}

if ($_SERVER['REQUEST_METHOD'] !== 'POST') {
    http_response_code(405);
    exit('Method not allowed.');
}

$name = trim($_POST['name'] ?? '');
$email = trim($_POST['email'] ?? '');

$errors = [];

if (mb_strlen($name) < 2) {
    $errors[] = 'Enter a valid name.';
}

if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
    $errors[] = 'Enter a valid email.';
}

if ($errors !== []) {
    http_response_code(422);

    foreach ($errors as $error) {
        echo '<p>' . e($error) . '</p>';
    }

    exit;
}

echo '<h1>Registration Received</h1>';
echo '<p>Name: ' . e($name) . '</p>';
echo '<p>Email: ' . e($email) . '</p>';
```

---

## Practical 14: File Write and Read

### Aim

PHP se text file safely append and display karna.

```php
<?php
declare(strict_types=1);

$path = __DIR__ . '/messages.txt';
$message = trim($_POST['message'] ?? '');

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    if ($message === '' || mb_strlen($message) > 500) {
        exit('Message must contain 1–500 characters.');
    }

    file_put_contents(
        $path,
        $message . PHP_EOL,
        FILE_APPEND | LOCK_EX
    );
}

$content = file_exists($path)
    ? file_get_contents($path)
    : '';

echo '<pre>';
echo htmlspecialchars(
    $content,
    ENT_QUOTES | ENT_SUBSTITUTE,
    'UTF-8'
);
echo '</pre>';
```

User-provided filesystem path accept nahi kiya gaya.

---

## Practical 15: Secure Image Upload

### Aim

File size and detected MIME type validate karke random filename se save karna.

```php
<?php
declare(strict_types=1);

$allowed = [
    'image/jpeg' => 'jpg',
    'image/png' => 'png',
    'image/webp' => 'webp',
];

$file = $_FILES['photo'] ?? null;

if (!$file || $file['error'] !== UPLOAD_ERR_OK) {
    exit('Upload failed.');
}

if ($file['size'] > 2 * 1024 * 1024) {
    exit('Image must be 2 MB or smaller.');
}

$mime = (new finfo(FILEINFO_MIME_TYPE))
    ->file($file['tmp_name']);

if (!isset($allowed[$mime])) {
    exit('Only JPEG, PNG and WebP are allowed.');
}

$filename = bin2hex(random_bytes(16))
    . '.'
    . $allowed[$mime];

$uploadDirectory = dirname(__DIR__) . '/private-uploads';
$destination = $uploadDirectory . '/' . $filename;

if (!is_dir($uploadDirectory)) {
    exit('Upload directory is not configured.');
}

if (!move_uploaded_file($file['tmp_name'], $destination)) {
    exit('Could not save image.');
}

echo 'Image uploaded successfully.';
```

### Test Cases

Valid file, oversized file, text renamed as image, no file.

---

## Practical 16: Session Login and Logout

### Aim

Password verification and secure session use karna.

### Login Success Core

```php
<?php
declare(strict_types=1);

session_set_cookie_params([
    'lifetime' => 0,
    'path' => '/',
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Lax',
]);

session_start();

// $user database prepared query se fetched hai.
if (
    $user &&
    password_verify($password, $user['password_hash'])
) {
    session_regenerate_id(true);

    $_SESSION['user_id'] = (int) $user['user_id'];
    $_SESSION['role'] = $user['role'];

    header('Location: /dashboard.php');
    exit;
}

echo 'Email or password is incorrect.';
```

### Logout

```php
<?php
session_start();

$_SESSION = [];

if (ini_get('session.use_cookies')) {
    $params = session_get_cookie_params();

    setcookie(session_name(), '', [
        'expires' => time() - 42000,
        'path' => $params['path'],
        'domain' => $params['domain'],
        'secure' => $params['secure'],
        'httponly' => $params['httponly'],
        'samesite' => $params['samesite'] ?? 'Lax',
    ]);
}

session_destroy();

header('Location: /login.php');
exit;
```

Local HTTP development mein secure cookie setting environment-aware karein; production HTTPS par true.

---

## Practical 17: OOP Student Class

### Aim

Constructor, property, method and encapsulation demonstrate karna.

```php
<?php
declare(strict_types=1);

final class Student
{
    public function __construct(
        private int $id,
        private string $name,
        private array $marks
    ) {
        if ($name === '') {
            throw new InvalidArgumentException(
                'Name is required.'
            );
        }
    }

    public function average(): float
    {
        if ($this->marks === []) {
            return 0.0;
        }

        return array_sum($this->marks)
            / count($this->marks);
    }

    public function result(): string
    {
        return $this->average() >= 40
            ? 'Pass'
            : 'Fail';
    }

    public function summary(): array
    {
        return [
            'id' => $this->id,
            'name' => $this->name,
            'average' => round($this->average(), 2),
            'result' => $this->result(),
        ];
    }
}

$student = new Student(
    101,
    'Aditi Sharma',
    [88, 82, 76, 91]
);

print_r($student->summary());
```

---

# Part D — MySQL Practicals

## Practical 18: College Database and Tables

### Aim

Keys and constraints ke saath relational schema create karna.

```sql
CREATE DATABASE college_lab
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;

USE college_lab;

CREATE TABLE courses (
    course_id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    course_code VARCHAR(20) NOT NULL UNIQUE,
    title VARCHAR(100) NOT NULL
);

CREATE TABLE students (
    student_id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    roll_number VARCHAR(20) NOT NULL UNIQUE,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL UNIQUE,
    semester TINYINT UNSIGNED NOT NULL,
    course_id INT UNSIGNED NOT NULL,

    CHECK (semester BETWEEN 1 AND 8),

    FOREIGN KEY (course_id)
        REFERENCES courses(course_id)
        ON DELETE RESTRICT
);
```

---

## Practical 19: SQL CRUD Operations

```sql
-- CREATE
INSERT INTO courses (course_code, title)
VALUES ('BCA', 'Bachelor of Computer Applications');

INSERT INTO students
(roll_number, name, email, semester, course_id)
VALUES
('BCA-101', 'Aditi Sharma', 'aditi@example.com', 1, 1),
('BCA-102', 'Rahul Verma', 'rahul@example.com', 3, 1);

-- READ
SELECT student_id, roll_number, name
FROM students
ORDER BY name;

-- UPDATE
UPDATE students
SET semester = 2
WHERE roll_number = 'BCA-101';

-- DELETE
DELETE FROM students
WHERE roll_number = 'BCA-102';
```

Before update/delete same `WHERE` with `SELECT` verify karein.

---

## Practical 20: Joins and Reports

### Aim

Related tables se combined report create karna.

```sql
CREATE TABLE subjects (
    subject_id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    subject_code VARCHAR(20) NOT NULL UNIQUE,
    subject_name VARCHAR(100) NOT NULL
);

CREATE TABLE enrollments (
    student_id INT UNSIGNED NOT NULL,
    subject_id INT UNSIGNED NOT NULL,
    marks DECIMAL(5, 2),

    PRIMARY KEY (student_id, subject_id),

    FOREIGN KEY (student_id)
        REFERENCES students(student_id)
        ON DELETE CASCADE,

    FOREIGN KEY (subject_id)
        REFERENCES subjects(subject_id)
        ON DELETE RESTRICT,

    CHECK (marks IS NULL OR marks BETWEEN 0 AND 100)
);
```

Report:

```sql
SELECT
    s.roll_number,
    s.name,
    sub.subject_code,
    sub.subject_name,
    e.marks,
    CASE
        WHEN e.marks IS NULL THEN 'Pending'
        WHEN e.marks >= 40 THEN 'Pass'
        ELSE 'Fail'
    END AS result
FROM enrollments AS e
JOIN students AS s
    ON e.student_id = s.student_id
JOIN subjects AS sub
    ON e.subject_id = sub.subject_id
ORDER BY s.roll_number, sub.subject_code;
```

Unenrolled students:

```sql
SELECT s.student_id, s.name
FROM students AS s
LEFT JOIN enrollments AS e
    ON s.student_id = e.student_id
WHERE e.student_id IS NULL;
```

---

# Part E — PHP + MySQL Practicals

## Practical 21: PDO Insert and List Students

### Aim

Prepared statements se MySQL data insert/read karna.

### Connection

```php
<?php
$pdo = new PDO(
    'mysql:host=127.0.0.1;dbname=college_lab;charset=utf8mb4',
    'college_user',
    'local-password',
    [
        PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
        PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
        PDO::ATTR_EMULATE_PREPARES => false,
    ]
);
```

### Insert

```php
$stmt = $pdo->prepare(
    'INSERT INTO students
     (roll_number, name, email, semester, course_id)
     VALUES
     (:roll_number, :name, :email, :semester, :course_id)'
);

$stmt->execute([
    'roll_number' => $rollNumber,
    'name' => $name,
    'email' => $email,
    'semester' => $semester,
    'course_id' => $courseId,
]);
```

### List

```php
$stmt = $pdo->query(
    'SELECT
        s.student_id,
        s.roll_number,
        s.name,
        s.email,
        s.semester,
        c.course_code
     FROM students AS s
     JOIN courses AS c
        ON s.course_id = c.course_id
     ORDER BY s.student_id DESC'
);

$students = $stmt->fetchAll();
```

Output:

```php
<?php foreach ($students as $student): ?>
  <tr>
    <td><?= e($student['roll_number']) ?></td>
    <td><?= e($student['name']) ?></td>
    <td><?= e($student['email']) ?></td>
    <td><?= (int) $student['semester'] ?></td>
    <td><?= e($student['course_code']) ?></td>
  </tr>
<?php endforeach; ?>
```

---

## Practical 22: AJAX Live Search

### Aim

Reload ke bina student search.

### PHP Endpoint

```php
<?php
declare(strict_types=1);

require __DIR__ . '/database.php';

header('Content-Type: application/json; charset=utf-8');

$query = trim($_GET['q'] ?? '');

if (mb_strlen($query) > 100) {
    http_response_code(422);
    echo json_encode([
        'message' => 'Search text is too long.',
    ]);
    exit;
}

$stmt = $pdo->prepare(
    'SELECT student_id, roll_number, name
     FROM students
     WHERE name LIKE :name_term
        OR roll_number LIKE :roll_term
     ORDER BY name
     LIMIT 20'
);

$term = '%' . $query . '%';

$stmt->execute([
    'name_term' => $term,
    'roll_term' => $term,
]);

echo json_encode([
    'students' => $stmt->fetchAll(),
], JSON_UNESCAPED_UNICODE);
```

### JavaScript

```javascript
const input = document.querySelector("#search");
const results = document.querySelector("#results");
const status = document.querySelector("#status");

let timer;
let controller;

input.addEventListener("input", () => {
  clearTimeout(timer);

  timer = setTimeout(async () => {
    controller?.abort();
    controller = new AbortController();

    status.textContent = "Searching…";

    try {
      const params = new URLSearchParams({
        q: input.value.trim(),
      });

      const response = await fetch(
        `search.php?${params}`,
        { signal: controller.signal }
      );

      const data = await response.json();

      if (!response.ok) {
        throw new Error(data.message ?? "Search failed");
      }

      results.replaceChildren();

      for (const student of data.students) {
        const item = document.createElement("li");
        item.textContent =
          `${student.name} (${student.roll_number})`;
        results.append(item);
      }

      status.textContent =
        `${data.students.length} result(s)`;
    } catch (error) {
      if (error.name === "AbortError") return;
      status.textContent = "Search failed.";
    }
  }, 300);
});
```

---

## Practical 23: JSON REST-Style API Endpoint

### Aim

Correct methods, status and JSON responses ke saath student endpoint banana.

```php
<?php
declare(strict_types=1);

require __DIR__ . '/database.php';

header('Content-Type: application/json; charset=utf-8');

function respond(mixed $data, int $status = 200): never
{
    http_response_code($status);

    echo json_encode(
        $data,
        JSON_UNESCAPED_UNICODE |
        JSON_UNESCAPED_SLASHES |
        JSON_THROW_ON_ERROR
    );

    exit;
}

$method = $_SERVER['REQUEST_METHOD'];

if ($method === 'GET') {
    $students = $pdo->query(
        'SELECT student_id, roll_number, name, semester
         FROM students
         ORDER BY student_id DESC
         LIMIT 100'
    )->fetchAll();

    respond(['data' => $students]);
}

if ($method === 'POST') {
    try {
        $data = json_decode(
            file_get_contents('php://input'),
            true,
            512,
            JSON_THROW_ON_ERROR
        );
    } catch (JsonException) {
        respond([
            'title' => 'Invalid JSON',
            'status' => 400,
        ], 400);
    }

    if (
        !is_array($data) ||
        trim($data['name'] ?? '') === ''
    ) {
        respond([
            'title' => 'Validation failed',
            'status' => 422,
        ], 422);
    }

    $stmt = $pdo->prepare(
        'INSERT INTO students
         (roll_number, name, email, semester, course_id)
         VALUES
         (:roll_number, :name, :email, :semester, :course_id)'
    );

    $stmt->execute([
        'roll_number' => trim($data['roll_number']),
        'name' => trim($data['name']),
        'email' => trim($data['email']),
        'semester' => (int) $data['semester'],
        'course_id' => (int) $data['course_id'],
    ]);

    respond([
        'data' => [
            'student_id' => (int) $pdo->lastInsertId(),
        ],
    ], 201);
}

header('Allow: GET, POST');

respond([
    'title' => 'Method not allowed',
    'status' => 405,
], 405);
```

Production endpoint authentication, authorization, CSRF/token strategy, full validation, rate limit and exception logging require karega.

---

## Practical 24: CSRF-Protected Delete

### Form

```php
<form method="post" action="delete-student.php">
  <input
    type="hidden"
    name="student_id"
    value="<?= (int) $student['student_id'] ?>"
  >
  <input
    type="hidden"
    name="csrf_token"
    value="<?= e($_SESSION['csrf_token']) ?>"
  >
  <button type="submit">Delete</button>
</form>
```

### Handler

```php
<?php
declare(strict_types=1);

session_start();
require __DIR__ . '/database.php';

if ($_SERVER['REQUEST_METHOD'] !== 'POST') {
    http_response_code(405);
    exit;
}

$submitted = $_POST['csrf_token'] ?? null;
$stored = $_SESSION['csrf_token'] ?? '';

if (
    $submitted === null ||
    $stored === '' ||
    !hash_equals($stored, $submitted)
) {
    http_response_code(403);
    exit('Invalid request token.');
}

// Admin authorization bhi verify karein.
if (($_SESSION['role'] ?? '') !== 'admin') {
    http_response_code(403);
    exit('Forbidden.');
}

$id = filter_input(
    INPUT_POST,
    'student_id',
    FILTER_VALIDATE_INT
);

if ($id === false || $id === null || $id < 1) {
    http_response_code(400);
    exit('Invalid ID.');
}

$stmt = $pdo->prepare(
    'DELETE FROM students
     WHERE student_id = :id'
);
$stmt->execute(['id' => $id]);

header('Location: /students.php?deleted=1');
exit;
```

---

# Part F — Advanced Practical

## Practical 25: Offline Page with Service Worker

### Aim

Basic PWA offline navigation fallback implement karna.

### Register

```javascript
if ("serviceWorker" in navigator) {
  window.addEventListener("load", () => {
    navigator.serviceWorker.register("/service-worker.js")
      .catch((error) => {
        console.error("Service worker failed:", error);
      });
  });
}
```

### `service-worker.js`

```javascript
const CACHE_NAME = "college-app-v1";
const PRECACHE = [
  "/",
  "/offline.html",
  "/assets/app.css",
  "/assets/app.js",
];

self.addEventListener("install", (event) => {
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then((cache) => cache.addAll(PRECACHE))
  );
});

self.addEventListener("activate", (event) => {
  event.waitUntil(
    caches.keys().then((keys) =>
      Promise.all(
        keys
          .filter((key) =>
            key.startsWith("college-app-") &&
            key !== CACHE_NAME
          )
          .map((key) => caches.delete(key))
      )
    )
  );
});

self.addEventListener("fetch", (event) => {
  if (
    event.request.method === "GET" &&
    event.request.mode === "navigate"
  ) {
    event.respondWith(
      fetch(event.request).catch(() =>
        caches.match("/offline.html")
      )
    );
  }
});
```

### Test

- HTTPS/localhost;
- online first visit;
- DevTools Offline;
- navigation fallback;
- update cache version;
- private pages not cached.

---

# Part G — Mini Project Options

## Practical 26: Choose One Mini Project

| Project | Core Modules | Advanced Extension |
|---|---|---|
| Library System | Books, members, borrow/return | Due alerts and reports |
| Student Portal | Students, courses, results | AJAX search and PWA |
| Expense Tracker | Categories, transactions | Charts and export |
| Appointment System | Users, slots, bookings | Email/webhook |
| Inventory System | Products, suppliers, stock | Low-stock alerts |
| Complaint Portal | Users, complaints, status | Role workflow and audit |
| Quiz System | Questions, attempts, score | Timer and question API |
| Event Registration | Events, participants | QR/check-in extension |

### Minimum Requirements

- semantic responsive frontend;
- MySQL relationships and constraints;
- PHP PDO CRUD;
- authentication and authorization;
- server validation;
- prepared statements;
- escaped output;
- CSRF protection;
- search and pagination;
- test cases;
- README and schema;
- Git history.

---

# Part H — Practical Record Index

| No. | Practical | Technology | Level |
|---:|---|---|---|
| 1 | Semantic Profile Page | HTML | Beginner |
| 2 | Marksheet Table | HTML | Beginner |
| 3 | Registration Form | HTML | Beginner |
| 4 | Responsive Card Grid | CSS Grid | Beginner |
| 5 | Navigation Bar | Flexbox | Beginner |
| 6 | Calculator | JavaScript DOM | Beginner |
| 7 | Grade Calculator | JavaScript | Beginner |
| 8 | Array Statistics | JavaScript | Beginner |
| 9 | To-Do List | DOM/Events | Intermediate |
| 10 | Form Validation | JavaScript | Intermediate |
| 11 | JSON Cards | Fetch/JSON | Intermediate |
| 12 | PHP Grade | PHP | Beginner |
| 13 | Form Processing | PHP | Intermediate |
| 14 | File Read/Write | PHP | Intermediate |
| 15 | Image Upload | PHP/Security | Intermediate |
| 16 | Login/Logout | PHP/Session | Intermediate |
| 17 | Student Class | PHP OOP | Intermediate |
| 18 | Database Schema | MySQL | Beginner |
| 19 | CRUD Queries | SQL | Beginner |
| 20 | Joins/Reports | SQL | Intermediate |
| 21 | PDO Insert/List | PHP/MySQL | Intermediate |
| 22 | Live Search | AJAX/PHP | Advanced |
| 23 | JSON API | REST/PHP | Advanced |
| 24 | Protected Delete | Web Security | Advanced |
| 25 | Offline Page | PWA | Advanced |
| 26 | Mini Project | Full Stack | Advanced |

---

## ✅ Final Practical Checklist

- [ ] Code runs without warnings/errors?
- [ ] Names and indentation clear?
- [ ] Valid and invalid test cases?
- [ ] Responsive output?
- [ ] Keyboard and labels checked?
- [ ] Server validation present?
- [ ] SQL parameterized?
- [ ] Output escaped?
- [ ] Correct status/redirect?
- [ ] Secrets and real data absent?
- [ ] Screenshot and result written?
- [ ] Viva answers prepared?
- [ ] Git commit created?

---

## 🔁 Practical Viva Pattern

Har program ke liye answer ready rakhein:

1. Program ka aim kya hai?
2. Input and expected output?
3. Main tags/functions/commands?
4. Validation kahan hoti hai?
5. Ek alternative method?
6. Common error kya aaya?
7. Security risk and defense?
8. Program ko future mein kaise improve karenge?

---

[⬅️ Previous: Appendix B](b-html-css-javascript-php-sql-quick-reference.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: Appendix D — Viva Questions ➡️**
