# Lab 2: Login & To-Do Application

A web-based Login and To-Do Management System built using Flask and MySQL. The application allows users to register, log in securely, and manage their personal tasks.

---

## 👥 1. Team Members

| Name | Student ID | Responsibilities |
|---|---|---|
| Rewan Mahmoud Mohamed | 2304098 | Database Design, Flask Backend, Authentication, and To-Do List |

---

## 🛠️ 2. Technologies & Tools

- **Backend:** Python, Flask
- **Frontend:** HTML, CSS, JavaScript
- **Database:** MySQL
- **Database Connector:** PyMySQL
- **Password Security:** bcrypt
- **Session Management:** Flask Sessions
- **Environment Variables:** python-dotenv

---

## ✨ 3. Features

- User registration and login.
- Duplicate email handling.
- Secure password hashing using bcrypt.
- Session-based authentication.
- Private task lists for each user.
- Add new tasks.
- Edit existing task titles.
- Mark tasks as completed or incomplete.
- Delete tasks with confirmation.
- Client-side and server-side input validation.
- Maximum task title length of 200 characters.
- Parameterized SQL queries.
- Responsive user interface.
- Dark Mode and Light Mode.

---

## 🚀 4. Installation & Setup

### Step 1 — Install Requirements

Make sure Python and MySQL are installed on your computer.

```bash
pip install -r requirements.txt
```

### Step 2 — Set Up the Database

Execute the SQL script located at `database/schema.sql` in MySQL to create the required database and tables.

### Step 3 — Configure Environment Variables

Copy `.env.example` and rename the copy to `.env`.

Configure the required database credentials and a secure, randomly generated Flask secret key.

Do not upload your actual `.env` file or expose your database password or secret key on GitHub.

### Step 4 — Run the Application

```bash
python app.py
```

### Step 5 — Open the Website

Open the following URL in your browser:

http://127.0.0.1:5000/register

Register a new account, log in, and start managing your tasks.

---

## 📸 5. Screenshots

### 1. Registration Page

Displays the user registration form and input validation.

![Registration Page](screenshots/registration.png)

### 2. Login Page

Displays the login form for existing users.

![Login Page](screenshots/login.png)

### 3. To-Do List Management

Displays the task management interface, including task actions and completed tasks.

![To-Do List](screenshots/todo-list.png)

### 4. Responsive Design

Demonstrates the application's appearance in a phone-sized browser viewport.

![Responsive Design](screenshots/responsive.png)

---

## 🗄️ 6. Database & Security Questions

### A. Why do UPDATE and DELETE queries include `AND user_id = %s`?

This condition ensures that users can only update or delete their own tasks. It prevents a user from modifying another user's task by supplying a different task ID.

### B. What happens if a to-do references a nonexistent `user_id`?

If a foreign key constraint is defined and enforced, MySQL rejects the operation because the referenced user does not exist. This maintains referential integrity between the users and todos tables.

### C. Why store a password hash instead of the original password?

Storing a password hash avoids saving passwords in plaintext. bcrypt uses a salt and a computationally expensive hashing process, making password-guessing attacks more difficult.

### D. Why validate an empty name if the database column is `NOT NULL`?

The `NOT NULL` constraint prevents NULL values, but it does not prevent empty strings or strings containing only spaces. Application-level validation is needed to reject these values.

### E. Why use both client-side and server-side validation?

Client-side validation provides immediate feedback to users. Server-side validation protects the application even if browser validation is bypassed or a request is sent directly to the server.

### F. Why use parameterized SQL queries?

Parameterized queries separate SQL commands from user-provided values, helping protect against SQL injection.

---

## ✅ 7. Conclusion

This project demonstrates the development of a web application using Flask and MySQL, including user authentication, secure password storage, database integration, and personal task management.

It also applies input validation, session handling, parameterized SQL queries, and database constraints to improve security and reliability.

---

**Course:** Introduction to Database Systems  
**Lab:** Lab 2 — Login & To-Do Application  
**Semester:** Fall 2026