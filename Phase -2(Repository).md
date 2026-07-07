# Phase 2 – Repository Layer

## Objective

Develop the Repository layer for the Product Catalog Management module using Spring Data JPA.

The Repository layer acts as the communication bridge between the Service layer and the database. It provides CRUD operations and custom database queries without writing SQL manually.

---

# Implemented Repositories

## 1. CategoryRepository

Responsible for performing database operations related to product categories.

### Features

- Save Category
- Update Category
- Delete Category
- Find Category by Name
- Check Existing Category

### Custom Methods

| Method | Purpose |
|---------|----------|
| findByCategoryName() | Retrieve category using its name |
| existsByCategoryName() | Check whether a category already exists |

---

## 2. ProductRepository

Responsible for handling all database operations related to products.

### Features

- Add Product
- Update Product
- Delete Product
- Retrieve Products
- Product Search
- Product Filtering

### Custom Methods

| Method | Purpose |
|---------|----------|
| findByCategory_Id() | Get products of a category |
| findByBrand() | Filter products by brand |
| findByVendorId() | Get vendor products |
| findByPriceBetween() | Price range filtering |
| findByProductNameContainingIgnoreCase() | Search product by name |
| findByActiveTrue() | Retrieve active products |
| findByFeaturedTrue() | Retrieve featured products |

---

## 3. ReviewRepository

Responsible for storing and retrieving product reviews.

### Features

- Add Review
- Delete Review
- Retrieve Product Reviews

### Custom Methods

| Method | Purpose |
|---------|----------|
| findByProduct_Id() | Retrieve all reviews of a product |

---

# Repository Architecture

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
PostgreSQL Database
```

The Repository layer does not contain business logic. It only interacts with the database through Spring Data JPA.

---

# Spring Data JPA Features Used

- JpaRepository
- Derived Query Methods
- CRUD Operations
- UUID Primary Key Support
- Custom Finder Methods

---

# Repository Summary

## CategoryRepository

- Category CRUD
- Category Lookup
- Duplicate Category Validation

---

## ProductRepository

- Product CRUD
- Product Search
- Product Filtering
- Vendor-wise Products
- Featured Products
- Active Products
- Price Filtering

---

## ReviewRepository

- Review CRUD
- Product Reviews

---

# Advantages

- No SQL Queries Required
- Automatic Query Generation
- Clean Architecture
- Easy Maintenance
- Supports PostgreSQL
- Faster Development using Spring Data JPA

---

# Phase Completion

✅ CategoryRepository Completed

✅ ProductRepository Completed

✅ ReviewRepository Completed

Compilation Status:

```bash
.\mvnw.cmd compile
```

Result:

```
BUILD SUCCESS
```

---

