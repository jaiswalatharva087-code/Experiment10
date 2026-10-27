# Student Management REST API

A lightweight backend REST API built with **Node.js, Express.js, and SQLite3**. This project demonstrates complete CRUD (Create, Read, Update, Delete) operations for managing student records, with support for testing using Postman.

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Database Schema](#-database-schema)
- [Getting Started](#-getting-started)
- [API Endpoints](#-api-endpoints)
- [Request and Response Examples](#-request-and-response-examples)
- [Error Handling](#-error-handling)
- [License](#-license)

## 📌 Overview

This project provides a RESTful API for managing student records using an SQLite database (`mydatabase.db`). It supports creating, retrieving, updating, and deleting student information. The database schema is initialized automatically when the application starts.

## ✨ Features

- **CRUD Operations:** Create, read, update, and delete student records.
- **RESTful Architecture:** Uses standard HTTP methods and status codes.
- **SQLite Database:** Stores student information locally.
- **Automatic Database Initialization:** Creates the required database schema on startup.
- **JSON Support:** Parses incoming JSON request bodies.
- **Modular Structure:** Separates database configuration from API routes.
- **Postman Testing:** Supports testing API endpoints using Postman.

## 🛠️ Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** SQLite3
- **API Testing:** Postman

## 📂 Project Structure

```text
student-rest-api/
├── app.js           # Main application and API routes
├── db.js            # Database connection and initialization
├── mydatabase.db    # SQLite database file (created automatically)
├── package.json     # Project metadata and dependencies
└── README.md        # Project documentation
```

## 🗄️ Database Schema

The application uses a `students` table with the following columns:

| Column | Data Type | Constraint | Description |
|---|---|---|---|
| `id` | INTEGER | Primary Key, Auto Increment | Unique student ID |
| `name` | TEXT | NOT NULL | Student's full name |
| `age` | INTEGER | — | Student's age |
| `grade` | TEXT | — | Student's grade |

## ⚙️ Getting Started

### Prerequisites

Make sure you have installed:

- [Node.js](https://nodejs.org/) (version 14 or higher)
- npm (included with Node.js)
- [Postman](https://www.postman.com/) (optional, for API testing)

### Installation

**1. Clone the repository**

Replace the URL below with your actual GitHub repository URL.

```bash
git clone https://github.com/your-username/student-rest-api.git
```

**2. Navigate to the project directory**

```bash
cd student-rest-api
```

**3. Install dependencies**

```bash
npm install
```

### Running the Server

Start the server using:

```bash
npm start
```

Alternatively, run the application directly:

```bash
node app.js
```

Once the server starts, the API will be available at:

```text
http://localhost:3000
```

The application initializes the SQLite database when configured to do so in `db.js`.

## 🔗 API Endpoints

| HTTP Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Display the welcome message |
| GET | `/students` | Retrieve all students |
| GET | `/students/:id` | Retrieve a student by ID |
| POST | `/students` | Create a new student |
| PUT | `/students/:id` | Update an existing student |
| DELETE | `/students/:id` | Delete a student by ID |

## 🧪 Request and Response Examples

Replace `:id` with the actual student ID when testing the endpoints.

### 1. Welcome Message

**Method:** `GET`

**URL:** `http://localhost:3000/`

**Response (200 OK):**

```text
Welcome to the Student Management REST API
```

### 2. Get All Students

**Method:** `GET`

**URL:** `http://localhost:3000/students`

**Response (200 OK):**

```json
[
  {
    "id": 1,
    "name": "John Doe",
    "age": 20,
    "grade": "A"
  },
  {
    "id": 2,
    "name": "Hemanth",
    "age": 22,
    "grade": "B"
  }
]
```

### 3. Get a Student by ID

**Method:** `GET`

**URL:** `http://localhost:3000/students/1`

**Response (200 OK):**

```json
{
  "id": 1,
  "name": "John Doe",
  "age": 20,
  "grade": "A"
}
```

### 4. Create a New Student

**Method:** `POST`

**URL:** `http://localhost:3000/students`

**Header:**

```text
Content-Type: application/json
```

**Request Body:**

```json
{
  "name": "Hemanth",
  "age": 22,
  "grade": "B"
}
```

**Example Response (201 Created):**

```json
{
  "id": 2
}
```

### 5. Update a Student

**Method:** `PUT`

**URL:** `http://localhost:3000/students/1`

**Header:**

```text
Content-Type: application/json
```

**Request Body:**

```json
{
  "name": "Madhu",
  "age": 22,
  "grade": "A+"
}
```

**Example Response (200 OK):**

```json
{
  "updatedID": "1"
}
```

### 6. Delete a Student

**Method:** `DELETE`

**URL:** `http://localhost:3000/students/2`

**Example Response (200 OK):**

```json
{
  "deletedID": "2"
}
```

> **Note:** The response examples are based on the described API behavior. Actual responses may differ depending on your implementation in `app.js`.

## ⚠️ Error Handling

The API can return error responses for common situations.

**Student Not Found (404 Not Found):**

```json
{
  "error": "Student not found"
}
```

**Internal Server Error (500 Internal Server Error):**

```json
{
  "error": "Database error details..."
}
```

## 📜 License

This project is available under the **MIT License**. Ensure that an MIT `LICENSE` file is included in the repository if you intend to distribute it under this license.
