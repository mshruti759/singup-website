# Signup Form with PHP and MySQL

A simple web-based **Signup Form** project built using **HTML, PHP, and MySQL**.
The project collects user information through an HTML form and stores the submitted data in a MySQL database.

## 📌 Project Overview

This project demonstrates how a frontend HTML form can communicate with a PHP backend and store form data in a MySQL database.

The user enters:

* Name
* Email
* Website
* Comment
* Gender

After clicking **Submit**, the data is sent to `submit.php`, which connects to the MySQL database and inserts the information into the `users` table.

## 🛠️ Technologies Used

* HTML5
* PHP
* MySQL
* Apache / Nginx
* Linux / AWS EC2

## 📂 Project Structure

```text
signup-project/
│
├── signup.html
├── submit.php
└── README.md
```

## 🔄 Project Workflow

```text
User
  │
  ▼
signup.html
  │
  │ POST request
  ▼
submit.php
  │
  ▼
MySQL Database
  │
  ▼
FCT Database
  │
  ▼
users Table
```

## 📝 signup.html

The `signup.html` file contains the signup form.

The form collects:

```text
Name
Email
Website
Comment
Gender
```

The form sends the submitted data to:

```text
submit.php
```

using the HTTP `POST` method.

## 🐘 submit.php

The `submit.php` file:

1. Receives the form data.
2. Connects to MySQL.
3. Selects the `FCT` database.
4. Inserts the submitted information into the `users` table.
5. Displays a success message after successful insertion.
6. Displays an error message if the database operation fails.

## 🗄️ Database Configuration

The current PHP configuration uses:

```text
Server: localhost
Username: root
Password: root
Database: FCT
```

### Create Database

Open MySQL and run:

```sql
CREATE DATABASE FCT;
```

Select the database:

```sql
USE FCT;
```

Create the `users` table:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(150),
    website VARCHAR(255),
    comment TEXT,
    gender VARCHAR(20)
);
```

## ▶️ How to Run the Project

### 1. Install a Web Server

You need a web server with PHP and MySQL installed.

For example:

* Apache
* Nginx
* PHP
* MySQL

### 2. Place Project Files

Copy the project files into your web server directory.

For example, on a Linux server:

```bash
/var/www/html/signup-project/
```

Place:

```text
signup.html
submit.php
```

inside this directory.

### 3. Start Required Services

Make sure your web server, PHP, and MySQL services are running.

For example:

```bash
sudo systemctl start nginx
sudo systemctl start mysql
```

### 4. Open the Website

Open your browser and enter:

```text
http://YOUR_SERVER_IP/signup-project/signup.html
```

If you are using AWS EC2, replace `YOUR_SERVER_IP` with your EC2 public IP address.

## ✅ Expected Result

The signup form appears in the browser.

After entering the information and clicking **Submit**, the PHP script connects to MySQL and stores the data.

A successful submission displays:

```text
✅ New record created successfully!
```

along with the submitted information.

## 🔍 Verify Data in MySQL

To check the stored records:

```sql
USE FCT;

SELECT * FROM users;
```

You should see the submitted user information.

## ☁️ AWS Deployment

This project can also be deployed on an **AWS EC2 instance**.

Example architecture:

```text
Internet
   │
   ▼
AWS EC2
   │
   ├── Nginx / Apache
   │
   ├── PHP
   │
   └── MySQL
        │
        ▼
      FCT Database
        │
        ▼
      users Table
```

## 🔐 Security Note

The current `submit.php` uses direct SQL string construction. This is suitable for understanding the basic concept, but it is **not recommended for a production application**.

For a real-world application, use:

* Prepared statements
* Input validation
* Secure database credentials
* Environment variables
* HTTPS
* Proper error handling

## 🚀 Future Improvements

Possible improvements include:

* Add CSS styling
* Add JavaScript form validation
* Use PHP prepared statements
* Add user login/logout
* Add an admin dashboard
* Display database records
* Add edit/delete functionality
* Deploy using AWS EC2
* Use Amazon RDS instead of local MySQL
* Enable HTTPS with SSL/TLS

## output


## 👩‍💻 Author

**Shruti More**


