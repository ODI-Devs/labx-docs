# User Management Module Documentation

## Overview

---

The **User Management** module is responsible for handling all operations related to user accounts within the system. This includes user registration, authentication, role-based access control, and account settings.

![Alt text](../img/module%20screenshots/user_management/Usermanagement.png)

## User Roles

---

- **Admin**  
  This role oversees the entire system and has permission to access all modules and data within the system.

- **Client Admin**  
  Also known as the Laboratory Admin, this role oversees, manages, and handles data within the assigned organization.

- **Staff**  
  Staff users handle patient transactions such as registration, ordering, and appointments within the assigned organization and locations.

- **Providers**  
  Provider users have the same privileges as staff but are limited to their assigned patients within the organization.

## Features

---

### I. User Registration and Management

Allows creation and editing of users within the system.

???+ quote "User Creation"

    === "Creation - User Guide"

        1.  Navigate to **"User Management"** tab
        2.  Click **"Create User"** button
        3.  Fill in the required information from the form.
        4.  Click **"Create User"** button to create user

    === "Creation - Alternate Flows"

        **Scenario 1**: Duplicate Email

        1.  User enters existing email within the same Organization
        2.  System returns a error toaster saying **"Error creating user : user with this email already exist"**
        3.  User remain in the creation form modal to recheck

        **Scenario 2**: Invalid or Missing Input Format

        1.  User enters Invalid data or Miss a required field (e.g email)
        2.  System returns an input validation for that specific field **"Invalid email address"**
        3.  User remain in the creation form modal to recheck

???+ quote "User Update"

    === "Update - User Guide"

        1.  Navigate to **"User Management"** tab
        2.  Click **"..."** icon in the "Actions" column
        3.  Click **"Edit"** button
        4.  Edit the desired information from the form.
        5.  Click **"Update User"** button to save changes

    === "Update - Alternate Flows"

           **Scenario**: Invalid Input Format

          1. User enters Invalid data field (e.g email)
          2. System returns an input validation for that specific field **"Invalid email address"**
          3. User remain in the creation form modal to recheck

### II. User Deactivation/Activation

Supports deactivation or activation of user accounts.

???+ quote "User Deactivation/Activation"

    === "User Guide"

        1.  Navigate to **"User Management"** tab
        2.  Click **"..."** icon in the "Actions" column of the desired row
        3.  Click **"Deactivate"** or **"Activate"** button
        5.  Click **"Update User"** button to save changes

### III. User Archive

Supports soft-deletion(archive) of User accounts

???+ quote "User Archive"

    === "User Guide"

        1.  Navigate to **"User Management"** tab
        2.  Click **"..."** icon in the "Actions" column of the desired row
        3.  Click **"Archive"** button
        5.  Click **"Update User"** button to save changes

- **User Authentication**  
  Provides secure login and logout functionality using session- or token-based authentication.

- **Password Management**  
  Includes password hashing, email-based password reset, and password strength validation.

- **Role-Based Access Control (RBAC)**  
  Assigns roles (e.g., Admin, Client Admin, Staff, and Providers) to manage permissions.

- **Table Filtering**  
   Supports filtering by status and keyword search.

- **Two Factor Authentication**  
  Supports two-factor authentication via email for enhanced login security.

- **Mass User Import**  
  Enables bulk user creation through mass import.

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

| Method      | Endpoint                                | Description                  |
| ----------- | --------------------------------------- | ---------------------------- |
| GET         | `/api/users`                            | List all users (admin only). |
| POST        | `/api/user/archive/:id/`                | Archive Users                |
| GET         | `/api/users/{id}`                       | Retrieve a specific user.    |
| PUT         | `/api/users/{id}`                       | Update user info.            |
| DELETE      | `/api/users/{id}`                       | Deactivate or delete a user. |
| **Filters** |
| GET         | `api/users/search/?search={name/email}` | Search Users                 |
| GET         | `/api/users/active/`                    | List of Active Users         |

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

```json
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
