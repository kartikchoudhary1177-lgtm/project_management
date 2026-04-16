# Project Management API

This is a simple backend project built using Django and Django REST Framework.
It provides APIs to manage users, projects, and tasks.

---

## Setup Instructions

1. Clone the repository

```bash
git clone https://github.com/kartikchoudhary1177-lgtm/project_management.git
cd project_management
```

2. Create virtual environment

```bash
python -m venv venv
```

Activate it:

* Windows:

```bash
venv\Scripts\activate
```

* Mac/Linux:

```bash
source venv/bin/activate
```

3. Install dependencies

```bash
pip install -r requirements.txt
```

4. Run migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

---

## How to run the project

Start the server:

```bash
python manage.py runserver
```

Open in browser:

```
http://127.0.0.1:8000/
```

---

## API Endpoints

### Users

* POST /api/users/ → create user
* GET /api/users/ → list users
* GET /api/users/{id}/ → get single user
* PUT /api/users/{id}/ → update user
* PATCH /api/users/{id}/ → partial update
* DELETE /api/users/{id}/ → delete user

---

### Projects

* POST /api/projects/ → create project
* GET /api/projects/ → list projects
* GET /api/projects/{id}/ → get single project
* PUT /api/projects/{id}/ → update project
* PATCH /api/projects/{id}/ → partial update
* DELETE /api/projects/{id}/ → delete project

---

### Tasks

* POST /api/tasks/ → create task
* GET /api/tasks/ → list tasks
* GET /api/tasks/{id}/ → get single task
* PUT /api/tasks/{id}/ → update task
* PATCH /api/tasks/{id}/ → partial update
* DELETE /api/tasks/{id}/ → delete task

---

## API Testing (Postman)

You can test all APIs using Postman or any API testing tool.

### Base URL

```
http://127.0.0.1:8000/api/
```

---

### Create User

POST `/api/users/`

Request:

```json
{
  "name": "Kartik",
  "email": "kartik@example.com",
  "password": "123456"
}
```

Response (201 Created):

```json
{
  "id": 1,
  "name": "Kartik",
  "email": "kartik@example.com"
}
```

---

### Create Project

POST `/api/projects/`

Request:

```json
{
  "title": "Test Project",
  "description": "This is a sample project"
}
```

Response (201 Created):

```json
{
  "id": 1,
  "title": "Test Project",
  "description": "This is a sample project",
  "created_at": "2026-04-15T10:00:00Z"
}
```

---

### Create Task

POST `/api/tasks/`

Request:

```json
{
  "title": "Test Task",
  "description": "This is a sample task",
  "status": "pending",
  "project": 1,
  "assigned_to": 1
}
```

Response (201 Created):

```json
{
  "id": 1,
  "title": "Test Task",
  "description": "This is a sample task",
  "status": "pending",
  "project": 1,
  "assigned_to": 1,
  "created_at": "2026-04-15T10:05:00Z"
}
```

---

### Important Points

* Use `Content-Type: application/json`
* Make sure user and project exist before creating task
* Use correct ID in URL like `/api/tasks/1/`

---

## Notes

* Task must be linked to a valid project
* Task must be assigned to a valid user
* Status can be: pending, in-progress, or completed

---


