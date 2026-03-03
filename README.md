# User Management API

A Django REST API project with a custom user model for managing user data.

## Tech Stack

- Python
- Django 6.0.2
- Django REST Framework 3.16.1
- SQLite

## Features

- Custom `User` model
- Email-based authentication field (`USERNAME_FIELD = email`)
- User list API endpoint
- Test API endpoint
- Admin panel support

## Prerequisites

- Python 3.11 or newer
- pip
- PowerShell (Windows)

## Setup

### 1) Open project folder

```powershell
cd E:\Projects\user_management_api
```

### 2) Create virtual environment (if not already created)

```powershell
python -m venv venv
```

### 3) Activate virtual environment

```powershell
.\venv\Scripts\Activate.ps1
```

### 4) Install dependencies

```powershell
pip install -r requirements.txt
```

### 5) Configure environment variables

Create a `.env` file in the project root and add:
These values are loaded automatically by `config/settings.py` at startup.

```env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=127.0.0.1,localhost
```

### 6) Apply migrations

```powershell
python manage.py makemigrations
python manage.py migrate
```

### 7) Create superuser (optional)

```powershell
python manage.py createsuperuser
```

### 8) Run development server

```powershell
python manage.py runserver
```

## Base URLs

- App: `http://127.0.0.1:8000/`
- API: `http://127.0.0.1:8000/api/`
- Admin: `http://127.0.0.1:8000/admin/`

## API Endpoints

### GET `/api/test/`

Purpose: Check API is running.

Example response:

```json
{
  "message": "Hello from TestView"
}
```

### GET `/api/users/`

Purpose: Return all users.

Response fields:

- `id`
- `username`
- `email`
- `first_name`
- `last_name`
- `phone_number`
- `date_of_birth`
- `bio`
- `is_verified`
- `created_at`
- `updated_at`

## Custom User Model

- Model path: `accounts.User`
- `email` is unique
- `USERNAME_FIELD` is `email`
- Required fields: `username`, `first_name`, `last_name`

## Project Structure

```text
user_management_api/
├── accounts/
├── config/
├── manage.py
├── requirements.txt
├── db.sqlite3
└── README.md
```

## Troubleshooting

### PowerShell script execution blocked

Run once:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### Dependencies not found

Make sure virtual environment is active, then install requirements again:

```powershell
pip install -r requirements.txt
```

### Port already in use

Run on a different port:

```powershell
python manage.py runserver 8001
```

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
