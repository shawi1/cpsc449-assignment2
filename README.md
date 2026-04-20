# Assignment 2 — JWT Role-Based Authorization

Extends the Bookstore API with ADMIN-only `DELETE /api/books/{id}` using Spring Security JWT role-based authorization.

## Changes Made

- **BookService.java** — added `deleteBook(id)` with 404 if book not found
- **BookController.java** — added `DELETE /api/books/{id}` returning 200 or 404
- **SecurityConfig.java** — restricted DELETE to `ADMIN` role; added `AccessDeniedHandler` returning `{"error": "Access Denied"}` on 403

## Postman / Bruno Screenshots

### 1. Register ADMIN user — 200 OK
![Register ADMIN](image.png)

### 2. Login as ADMIN — token visible in response
![Login ADMIN](image-2.png)

### 3. DELETE as ADMIN — 200 OK
![DELETE as ADMIN](image-5.png)

### 4. DELETE as USER — 403 Forbidden
![DELETE as USER](image-7.png)
