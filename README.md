# Student Tracker API

A backend-only FastAPI application for managing student records using SQLite
and SQLAlchemy.

## Requirements

- Python 3.10 or newer
- pip

## Setup and run

```powershell
cd D:\Test_API
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m uvicorn app.main:app --reload --port 8000
```

Swagger UI: `http://127.0.0.1:8000/docs`

If port 8000 is blocked, use another port:

```powershell
python -m uvicorn app.main:app --reload --port 8002
```

## Folder structure

```text
app/
  api/routes/students.py
  models/student.py
  repositories/student_repository.py
  database.py
  main.py
tests/test_students.py
```

## API endpoints

| Method | URL | Description |
|---|---|---|
| POST | `/api/students` | Add a student |
| GET | `/api/students` | View all students |
| GET | `/api/students/{id}` | View a student by ID |
| PUT | `/api/students/{id}` | Update a student |
| DELETE | `/api/students/{id}` | Delete a student |

### Add a student

`POST http://127.0.0.1:8000/api/students`

```json
{
  "name": "Asha Rao",
  "email": "asha@example.com",
  "course": "Computer Science",
  "attendance": 92.5,
  "marks": 88.0
}
```

### View and delete students

- Browser/Postman: `GET http://127.0.0.1:8000/api/students`
- Browser/Postman: `GET http://127.0.0.1:8000/api/students/1`
- Postman/Swagger: `PUT http://127.0.0.1:8000/api/students/1`
- Postman/Swagger: `DELETE http://127.0.0.1:8000/api/students/1`

## Run tests

```powershell
python -m pytest -v
```
