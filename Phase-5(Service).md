# Phase 5 – Service Layer

## Objective

Develop the Service Layer for the Product Catalog Management module.

The Service layer contains the application's business logic and acts as an intermediary between the Controller layer and Repository layer. It validates requests, processes business rules, and interacts with the database through repositories.

---

# Folder Structure

```
product
└── service
    ├── CategoryService.java
    ├── CategoryServiceImpl.java
    ├── ProductService.java
    ├── ProductServiceImpl.java
    ├── ReviewService.java
    └── ReviewServiceImpl.java
```

---

# Service Architecture

```
Controller
      │
      ▼
Service Layer
      │
      ▼
Repository Layer
      │
      ▼
Database
```

The Service layer is responsible for:

- Business Logic
- Data Validation
- Exception Handling
- Entity Mapping
- Database Transactions

---

# Category Service

## Features

- Create Category
- Update Category
- Delete Category
- Get Category by ID
- Get All Categories

### Business Rules

- Prevent duplicate category names.
- Throw `ResourceNotFoundException` if the category does not exist.
- Convert entities to DTOs using MapStruct.

---

# Product Service

## Features

- Create Product
- Update Product
- Delete Product
- Get Product by ID
- Get All Products

## Product Search

- Search by Product Name

## Product Filtering

- Filter by Category
- Filter by Brand
- Filter by Vendor
- Filter by Price Range

## Product Management

- Retrieve Featured Products
- Retrieve Active Products

### Business Rules

- Validate category existence before creating or updating a product.
- Prevent invalid price ranges.
- Throw `ResourceNotFoundException` when a product or category is not found.
- Throw `BadRequestException` for invalid input.

---

# Review Service

## Features

- Add Product Review
- Retrieve Reviews by Product
- Delete Review

### Business Rules

- Validate product existence before adding a review.
- Throw `ResourceNotFoundException` if the review or product is not found.

---

# Spring Features Used

- @Service
- @Transactional
- @Transactional(readOnly = true)
- Dependency Injection
- Constructor Injection (Lombok)
- Spring Data JPA

---

# Exception Handling

The Service layer integrates with the project's common exception framework.

Exceptions used:

- BadRequestException
- ResourceNotFoundException

These exceptions are handled globally by `GlobalExceptionHandler`.

---

# Data Flow

```
Client
   │
   ▼
Controller
   │
   ▼
Service
   │
   ▼
Repository
   │
   ▼
PostgreSQL
```

---

# Advantages

- Separates business logic from controllers.
- Reuses repository methods.
- Improves maintainability.
- Supports transaction management.
- Provides centralized validation.
- Simplifies future enhancements.

---

# Files Completed

## Category

- CategoryService
- CategoryServiceImpl

---

## Product

- ProductService
- ProductServiceImpl

---

## Review

- ReviewService
- ReviewServiceImpl

---

# Phase Completion

✅ Category Service Completed

✅ Product Service Completed

✅ Review Service Completed

Compilation Check

```bash
.\mvnw.cmd clean compile
```

Expected Result

```
BUILD SUCCESS
```

---

# Next Phase
