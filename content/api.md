---
marp: true
size: 4:3
paginate: true
title: Project 2 – API Documentation
---

# Project 2 – API Documentation

Documenting RESTful API endpoints for Project 2  
built with Laravel, PHP & MySQL.

---

# Database Tables

This API connects to two MySQL tables:

1. `items`
2. `lists`

---

# Table Schemas - items

CREATE TABLE items (
  id BIGINT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  type VARCHAR(255) NOT NULL,
  list_id BIGINT UNSIGNED NOT NULL,
  created_at TIMESTAMP NULL,
  updated_at TIMESTAMP NULL,
  FOREIGN KEY (list_id) REFERENCES lists(id) ON DELETE CASCADE
);

---

# Table Schemas - lists

CREATE TABLE lists (
  id BIGINT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255),
  type VARCHAR(255)
);

---

# API Endpoints Overview

Project 2 includes **10 API endpoints**:

- 8 non-token endpoints
- 2 token-protected endpoints

---

# 8 Non-token Endpoints:

1. `GET /api/items` – List all items  
2. `GET /api/items/{id}` – Get item by ID  
3. `POST /api/items` – Create new item  
4. `PUT /api/items/{id}` – Update item  
5. `GET /api/lists` – List all lists  
6. `GET /api/lists/{id}` – Get list by ID  
7. `POST /api/lists` – Create new list  
8. `PUT /api/lists/{id}` – Update list  

---

# 2 Token-Protected Endpoints:

1. `DELETE /api/items/{id}` – Delete item  
2. `DELETE /api/lists/{id}` – Delete list  

---

# 1. GET /api/items

Returns all items.

**Method:** `GET`  
**URL:** `/api/items`  
**Response:** JSON array of items.

---

# 2. GET /api/items/{id}

Returns a single item by ID.

**Method:** `GET`  
**URL:** `/api/items/1`  
**Response:** Item object or error.

---

# 3. POST /api/items

Creates a new item.

**Method:** `POST`  
**URL:** `/api/items`  
**Body:** `{ "name": "Item Name" }`  
**Response:** New item ID.

---

# 4. PUT /api/items/{id}

Updates an existing item.

**Method:** `PUT`  
**URL:** `/api/items/1`  
**Body:** `{ "name": "Updated Name" }`  
**Response:** Update message.

---

# 5. GET /api/lists

Returns all lists.

**Method:** `GET`  
**URL:** `/api/lists`  
**Response:** JSON array of lists.

---

# 6. GET /api/lists/{id}

Returns a single list by ID.

**Method:** `GET`  
**URL:** `/api/lists/1`  
**Response:** List object or error.

---

# 7. POST /api/lists

Creates a new list.

**Method:** `POST`  
**URL:** `/api/lists`  
**Body:** `{ "name": "List Name" }`  
**Response:** New list ID.

---

# 8. PUT /api/lists/{id}

Updates an existing list.

**Method:** `PUT`  
**URL:** `/api/lists/1`  
**Body:** `{ "name": "Updated Name" }`  
**Response:** Update message.

---

# 9. DELETE /api/items/{id}

**Requires Bearer Token**  

**Method:** `DELETE`  
**URL:** `/api/items/1`  
**Header:** `Authorization: Bearer mysecrettoken123`  
**Response:** Deletion message.

---

# 10. DELETE /api/lists/{id}

**Requires Bearer Token**  

**Method:** `DELETE`  
**URL:** `/api/lists/1`  
**Header:** `Authorization: Bearer mysecrettoken123`  
**Response:** Deletion message.

---

# Accessing the API

Two main ways to access and test the API:

1. **Web Frontend** (GUI) – `frontend.html`  
2. **Shell Script** – `test_api.sh` (with `curl`)

---

# 1. Web Frontend

Simple HTML frontend for interacting with API endpoints.

---

# 2. Shell Script (`curl`)

Use shell scripts to test endpoints programmatically.

---

# Thank You!

Project 2 API documentation complete.
---
