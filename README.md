# Project and Task Management Backend API

A backend REST API for managing users, projects, project members, tasks, subtasks, and notes.

The project is built using Node.js, Express.js, MongoDB, and Mongoose, with JWT-based authentication, request validation, centralized error handling, and email-related authentication flows.

---

## Features

- User registration and authentication
- JWT-based access and refresh token authentication
- Email verification
- Forgot-password and reset-password flow
- Project creation and management
- Project member management
- Task management
- Subtask management
- Notes management
- Role-based authorization
- Request validation using Express Validator
- Centralized API error handling
- Standardized API responses
- MongoDB integration using Mongoose
- File upload middleware using Multer
- Health check endpoint

---

## Tech Stack

- Node.js
- Express.js
- MongoDB
- Mongoose
- JSON Web Token (JWT)
- bcrypt
- Express Validator
- Nodemailer
- Mailgen
- Multer
- Cookie Parser
- CORS
- Dotenv

---

## Project Structure

```text
src/
│
├── controllers/
│   ├── auth.controllers.js
│   ├── healthcheck.controllers.js
│   ├── note.controllers.js
│   ├── project.controllers.js
│   └── task.controllers.js
│
├── models/
│   ├── user.models.js
│   ├── project.models.js
│   ├── projectmember.model.js
│   ├── task.models.js
│   ├── subtask.models.js
│   └── note.models.js
│
├── routes/
│   ├── auth.routes.js
│   ├── healthcheck.routes.js
│   ├── note.routes.js
│   ├── project.routes.js
│   └── task.routes.js
│
├── middlewares/
│   ├── auth.middleware.js
│   ├── error.middleware.js
│   ├── multer.middleware.js
│   └── validator.middleware.js
│
├── utils/
│   ├── api-error.js
│   ├── api-response.js
│   ├── async-handler.js
│   ├── constants.js
│   └── mail.js
│
├── db/
├── validators/
├── app.js
└── index.js
```

````md
## Installation

Clone the repository:

```bash
git clone <your-repository-url>
```
````

Move into the project directory:

```bash
cd project-task-management-backend
```

Install dependencies:

```bash
npm install
```

---

## Environment Variables

Create a `.env` file in the root directory.

Example:

```env
PORT=8000
MONGO_URI=your_mongodb_connection_string

ACCESS_TOKEN_SECRET=your_access_token_secret
ACCESS_TOKEN_EXPIRY=1d

REFRESH_TOKEN_SECRET=your_refresh_token_secret
REFRESH_TOKEN_EXPIRY=10d

MAILTRAP_SMTP_HOST=
MAILTRAP_SMTP_PORT=
MAILTRAP_SMTP_USER=
MAILTRAP_SMTP_PASS=

FORGOT_PASSWORD_REDIRECT_URL=
```

Note : No need to commit `.env` file to GitHub.

---

## Running the Project

Start the development server:

```bash
npm run dev
```

Start normally:

```bash
npm start
```

The server runs on the configured port.

Example:

```text
http://localhost:8000
```

---

## API Architecture

The project follows a controller-route-model based backend structure.

A typical request flows through:

```text
Client
  ↓
Route
  ↓
Validation / Authentication Middleware
  ↓
Controller
  ↓
Mongoose Model
  ↓
MongoDB
  ↓
API Response
```

Errors are handled through centralized error-handling middleware.

---

## Main Modules

### Authentication

Handles:

- Registration
- Login
- Logout
- Email verification
- Access tokens
- Refresh tokens
- Forgot password
- Reset password

### Projects

Handles project-related operations and project member management.

### Tasks

Handles tasks and subtasks associated with projects.

### Notes

Allows notes to be created and managed within the application.

### Health Check

Provides an endpoint to verify that the backend server is running.

---
