University Library API

This project defines a RESTful API for an online university library system using the OpenAPI 3.0.3 specification.

📚 Overview

The API supports management of:

Books

Students

Loans

It includes all basic CRUD operations, pagination, validation formats, and partial updates (PATCH).

📁 Project Structure

/
├── openapi.yaml     # Main OpenAPI specification file
├── DELIVERY.md      # Assignment delivery file
└── README.md        # Project documentation (this file)

🔧 Features

Full OpenAPI 3.0.3 compliant

Includes schemas for all entities

Query & path parameters (pagination, IDs)

Detailed response codes: 200, 201, 400, 404, 500

Example values, descriptions, and tags

🚀 How to Test

Open Swagger Editor

Paste the contents of openapi.yaml

Explore endpoints and schemas interactively

📌 API Endpoints

Books

GET /books — List books with pagination

GET /books/{id} — Get book by ID

POST /books — Create new book

PUT /books/{id} — Update book

DELETE /books/{id} — Delete book

Students

GET /students — List students

GET /students/{id} — Get student by ID

POST /students — Create new student

PUT /students/{id} — Update student

DELETE /students/{id} — Delete student

Loans

GET /loans — List all loans

GET /loans/{id} — Get loan by ID

POST /loans — Create loan

PATCH /loans/{id}/return — Return a book

🛡️ Optional Security (Not Implemented)

API Key or Bearer Token example can be added in components/securitySchemes

© 2025 nailkocabay — For educational purposes

