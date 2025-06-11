## Organizations Module Documentation

## Overview

The **Organization** module is responsible for handling all operations related to organizations. This includes creation and managements of a specific organization .

---

## Features

- **Organization Creation and Management**  
  Enable to create and edit organizations within the system.

- **Organization Deactivation/Activation**  
  Supports activation and deactivation of Organization.

- **Organization Archive**  
  Supports soft-deletion(archive) of Organization.

- **Two Factor Authentication**  
  Supports 2 Factor Authentication via email for more secured login.

---

## API Endpoints

> Below is a list of commonly used endpoints. This may vary based on the backend framework (e.g., Express, Django, Laravel).

### Authentication

| Method | Endpoint                                 | Description             |
| ------ | ---------------------------------------- | ----------------------- |
| POST   | `/api/auth/login`                        | Authenticates a user    |
| POST   | `/api/auth/logout`                       | Logs out the user       |
| POST   | `/api/auth/password/change/`             | Change Password         |
| POST   | `/api/auth/password/reset/`              | Reset Password          |
| POST   | `/api/auth/verify-2fa/", { user, code }` | 2 Factor Authentication |

### User Management

| Method  | Endpoint                                | Description                  |
| ------- | --------------------------------------- | ---------------------------- |
| GET     | `/api/users`                            | List all users (admin only). |
| POST    | `/api/user/archive/:id/`                | Archive Users                |
| GET     | `/api/users/{id}`                       | Retrieve a specific user.    |
| PUT     | `/api/users/{id}`                       | Update user info.            |
| DELETE  | `/api/users/{id}`                       | Deactivate or delete a user. |
| Filters |
| GET     | `api/users/search/?search={name/email}` | Search Users                 |
| GET     | `/api/users/active/`                    | List of Active Users         |

---

## Data Model

### Authentication

```json
{
  "email": "string",
  "password": "string"
}
```

### User

````json
{
  "id": "uuid",
  "email": "string",
  "first_name": "string",
  "last_name": "string",
  "is_online": "boolean",
  "last_activity": "datetime",
  "is_active": "boolean",
  "is_deleted": "boolean",
  "role": "admin | client admin | staff | ptorviders",
  "phone_number": "string",
  "provider_signature": "boolean",
  "provider_signature_url": "string",
  "npi": "string",
  "primary_practice_address": "string",
  "first_time_login": "boolean",
  "organization": "string",
  "location": "array",
  "provider": "array",
  "physician_only_results": "boolean",
  "email_2fa_enabled": "boolean",
  "title": "string"
}
```
````
