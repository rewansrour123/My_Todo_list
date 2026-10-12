# Lab 2: Login & To-Do Application

A web-based Login and To-Do Management System developed using Flask and MySQL for the **Introduction to Database Systems** course at Alexandria National University. The application allows users to create accounts, log in securely, and manage their personal tasks.

## 👥 1. Team Members

| Name | Student ID | Responsibilities |
|---|---|---|
| Rewan Mahmoud Mohamed | 2304098 | Database Design, Flask Backend, Authentication, and To-Do List |

## 🛠️ 2. Technologies & Tools

- **Backend:** Python, Flask
- **Frontend:** HTML, CSS, JavaScript
- **Database:** MySQL
- **Database Connector:** PyMySQL
- **Password Security:** bcrypt
- **Session Management:** Flask Sessions
- **Environment Variables:** python-dotenv
- **Version Control:** Git and GitHub

## ✨ 3. Features

- User registration and login.
- Duplicate email handling.
- Secure password hashing using bcrypt.
- Session-based authentication.
- Protected pages for authenticated users.
- Private task lists for each user.
- Add, edit, and delete tasks.
- Mark tasks as completed or incomplete.
- Delete confirmation.
- Client-side and server-side input validation.
- Maximum task title length of 200 characters.
- Parameterized SQL queries to help prevent SQL injection.
- Responsive user interface.
- Dark Mode and Light Mode.

## 📁 4. Project Structure

```text
My_Todo_list/
│
├── app.py
├── schema.sql
├── env.example
├── .gitignore
├── README.md
│
├── login.html
├── register.html
├── todos.html
│
├── style.css
├── theme.js
│
├── Screenshot 2026-10-12 121621.png
├── Screenshot 2026-10-12 121837.png
├── Screenshot 2026-10-12 121945.png
└── Screenshot 2026-10-12 122026.png
```

## 🚀 5. Installation & Setup

### Step 1 — Install Requirements

Make sure Python and MySQL are installed on your computer.

Install the required Python packages:

```bash
pip install flask pymysql bcrypt python-dotenv
```

### Step 2 — Set Up the Database

1. Open MySQL Workbench or your preferred MySQL client.
2. Open `schema.sql`.
3. Execute the SQL script to create the database and required tables.

### Step 3 — Configure Environment Variables

1. Create a copy of `env.example`.
2. Rename the copy to `.env`.
3. Update the database credentials and Flask secret key according to your local configuration.

**Important:** Never upload your actual `.env` file or expose your database password or Flask secret key on GitHub.

### Step 4 — Run the Application

From the project directory, run:

```bash
python app.py
```

### Step 5 — Open the Website

Open the following URL in your browser:

**Registration page:** http://127.0.0.1:5000/register

Register a new account, log in, and start managing your personal tasks.

## 📸 6. Screenshots

### 1. Registration Page

![Registration Page](Screenshot%202026-10-12%20121621.png)

### 2. Login Page

![Login Page](Screenshot%202026-10-12%20121837.png)

### 3. To-Do List Management

![To-Do List](Screenshot%202026-10-12%20121945.png)

### 4. Responsive Design

![Responsive Design](Screenshot%202026-10-12%20122026.png)

## 🗄️ 7. Database & Security Questions

### A. Why do UPDATE and DELETE queries include `AND user_id = %s`?

This condition ensures that users can update or delete only their own tasks. It prevents users from modifying another user's tasks by supplying a different task ID.

### B. What happens if a to-do references a nonexistent `user_id`?

If a foreign key constraint is defined and enforced, MySQL rejects the operation because the referenced user does not exist. This maintains referential integrity between the users and todos tables.

### C. Why store a password hash instead of the original password?

Storing a password hash avoids saving passwords in plaintext. bcrypt uses a salt and a computationally expensive hashing process to make password-guessing attacks more difficult.

### D. Why validate an empty name if the database column is `NOT NULL`?

The `NOT NULL` constraint prevents NULL values, but it does not necessarily prevent empty strings or strings containing only spaces. Application-level validation is needed to reject these values.

### E. Why use both client-side and server-side validation?

Client-side validation provides immediate feedback to users. Server-side validation protects the application when browser validation is bypassed or requests are sent directly to the server.

### F. Why use parameterized SQL queries?

Parameterized queries separate SQL commands from user-provided values, helping protect against SQL injection.

## ✅ 8. Conclusion

This project demonstrates the development of a web application using Flask and MySQL, including user authentication, secure password storage, database integration, and personal task management.

It also applies input validation, session handling, parameterized SQL queries, and database constraints to improve security and reliability.

## 🎓 Course Information

- **University:** Alexandria National University
- **Faculty:** Faculty of Engineering
- **Course:** Introduction to Database Systems
- **Lab:** Lab 2 — Login & To-Do Application
- **Semester:** Fall 2026
