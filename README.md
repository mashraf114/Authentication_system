# Authentication System

A simple authentication system built with Django, Django REST Framework, and Djoser.

## 🔐 Features

- Username and password-based authentication
- Token-based authentication using JWT

> **Note:** Email support planned for future improvement.

## ✅ Status

**Completed**

---

## 🛠️ How to Create the Auth App

### 1. Start the Django Project

```bash
django-admin startproject auth_project
```
### 2. Enter the Project Folder
```bash
cd auth_project
```
### 3. Create the Authentication App

```bash
python manage.py startapp accounts
```
### 4. Create a Virtual Environment and Install Dependencies

```bash
python -m venv venv
source venv/bin/activate
pip install django djangorestframework djoser djangorestframework-simplejwt
```
### 5. Update settings.py
In the INSTALLED_APPS section, add the following:

```bash
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    "rest_framework",
    "rest_framework_simplejwt",
    "djoser",
    "accounts",
]
```
## In the REST_FRAMEWORK section, configure JWT authentication:

```bash
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': (
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ),
}
```
#### In the DJOSER section, add configurations for user login and registration:

```bash
DJOSER = {
    'LOGIN_FIELD': 'username',
    'USER_CREATE_PASSWORD_RETYPE': True,
    'SERIALIZERS': {},
}
```
### 6. Apply Migrations and Run the Server

```bash
python manage.py migrate
python manage.py runserver
```
## 📌 Future Improvements
Add email support for registration and login