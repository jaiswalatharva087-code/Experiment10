# Student Management API

## 📌 Project Description

The Student Management API is a backend web application developed using Node.js, Express.js, and SQLite. It provides a simple and efficient way to manage student records through RESTful API endpoints.

The application allows users to create, retrieve, update, and delete student information. Student details are stored in an SQLite database, making the application lightweight and easy to use.

This project demonstrates the implementation of CRUD operations, REST API development, database connectivity, request handling, and error management.

## 🎯 Objectives

- To develop a RESTful API using Node.js and Express.js.
- To perform CRUD operations on student records.
- To connect an application with an SQLite database.
- To understand HTTP methods and API endpoints.
- To handle requests and responses using JSON.

## 🛠️ Technologies Used

- **Node.js:** JavaScript runtime environment used to execute the application.
- **Express.js:** Framework used to create the web server and API routes.
- **SQLite:** Lightweight database used to store student information.
- **JavaScript:** Programming language used to implement the application.
- **Postman:** Tool used to test API endpoints.
- **Git and GitHub:** Used for version control and project hosting.

## ✨ Features

- Add new student records.
- Retrieve all student records.
- Search for a student using their ID.
- Update existing student information.
- Delete student records.
- Store student details in an SQLite database.
- Handle invalid requests and server errors.
- Return responses in JSON format.

## 📂 Project Structure

```text
Experiment10/
│
├── app.js
├── db.js
├── mydatabase.db
├── package.json
├── package-lock.json
└── README.md
```

- **app.js:** Contains the Express server configuration and API endpoints.
- **db.js:** Handles SQLite database initialization and table creation.
- **mydatabase.db:** Stores student records.
- **package.json:** Contains project information, dependencies, and scripts.
- **package-lock.json:** Records the exact dependency versions.
- **README.md:** Provides project documentation and usage instructions.

## 🗄️ Database Design

The application uses SQLite to store student details in a table named `students`.

The table contains the following fields:

| Field | Description |
|---|---|
| `id` | Unique student ID generated automatically |
| `name` | Name of the student |
| `age` | Age of the student |
| `grade` | Grade obtained by the student |

The database table is created automatically if it does not already exist.

```sql
CREATE TABLE IF NOT EXISTS students (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    age INTEGER,
    grade TEXT
);
```

## 🔗 API Endpoints

The application provides the following REST API endpoints.

| HTTP Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Displays the welcome message |
| GET | `/students` | Retrieves all students |
| GET | `/students/:id` | Retrieves a student by ID |
| POST | `/students` | Adds a new student |
| PUT | `/students/:id` | Updates student information |
| DELETE | `/students/:id` | Deletes a student record |

### 1. Get All Students

**Endpoint:** `GET /students`

Retrieves all student records stored in the database.

### 2. Get Student by ID

**Endpoint:** `GET /students/:id`

Retrieves the details of a specific student using their unique ID.

### 3. Add a New Student

**Endpoint:** `POST /students`

Adds a new student to the database.

**Example request body:**

```json
{
  "name": "Alice",
  "age": 18,
  "grade": "A"
}
```

### 4. Update Student Details

**Endpoint:** `PUT /students/:id`

Updates the details of an existing student.

**Example request body:**

```json
{
  "name": "Alice",
  "age": 19,
  "grade": "A+"
}
```

### 5. Delete a Student

**Endpoint:** `DELETE /students/:id`

Deletes a student record using the specified student ID.

## ⚙️ Installation and Execution

Follow these steps to run the project on your local system.

### Prerequisites

Install the following software:

- Node.js
- npm (Node Package Manager)
- A code editor such as Visual Studio Code
- Postman (optional, for API testing)

### Step 1: Clone the Repository

```bash
git clone https://github.com/padarthidivyasri/Experiment10.git
```

### Step 2: Navigate to the Project Folder

```bash
cd Experiment10
```

### Step 3: Install Dependencies

```bash
npm install
```

### Step 4: Start the Application

```bash
npm start
```

### Step 5: Access the API

Once the server is running, use the following base URL to access the API:

```text
http://localhost:3000
```

## 🧪 Testing the API

The API can be tested using Postman or any HTTP client.

Use the following URLs with the appropriate HTTP methods:

```text
GET     http://localhost:3000/
GET     http://localhost:3000/students
GET     http://localhost:3000/students/1
POST    http://localhost:3000/students
PUT     http://localhost:3000/students/1
DELETE  http://localhost:3000/students/1
```

For POST and PUT requests, select **Body → raw → JSON** in Postman and enter the student details in JSON format.

## ⚠️ Error Handling

The application handles common errors, including:

- Student records that cannot be found.
- Invalid or incomplete student information.
- Database-related errors.
- Internal server errors.

Appropriate HTTP status codes and JSON responses are returned to communicate the result of each request.

## 📚 Learning Outcomes

Through this project, the following concepts are demonstrated:

- Backend development using Node.js.
- Creating RESTful APIs using Express.js.
- Implementing CRUD operations.
- Connecting an application to an SQLite database.
- Handling HTTP requests and JSON responses.
- Testing API functionality using Postman.
- Organizing and documenting a software project.

## 🏁 Conclusion

The Student Management API successfully demonstrates how to build a simple backend application for managing student records. By combining Node.js, Express.js, and SQLite, the project provides the basic functionality required to create, retrieve, update, and delete student information.

This project helps develop a practical understanding of REST API development, database integration, and backend application design.
