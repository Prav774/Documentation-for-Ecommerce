# Phase 4 – Mapper Layer

## Objective

Develop the Mapper layer for the Product Catalog Management module using **MapStruct**.

The Mapper layer automatically converts:

- Request DTO → Entity
- Entity → Response DTO

This removes manual object mapping and keeps the Service layer clean and maintainable.

---

# Folder Structure

```
product
└── mapper
    ├── CategoryMapper.java
    ├── ProductMapper.java
    └── ReviewMapper.java
```

---

# Implemented Mappers

## 1. CategoryMapper

Responsible for converting between Category DTOs and Category Entity.

### Features

- Convert CreateCategoryRequest → Category
- Convert Category → CategoryResponse
- Update existing Category entity

---

## 2. ProductMapper

Responsible for converting between Product DTOs and Product Entity.

### Features

- Convert CreateProductRequest → Product
- Convert Product → ProductResponse
- Update existing Product entity

### Notes

- Category relationship is handled inside the Service layer.
- Only `categoryId` is transferred through DTOs.
- The mapper ignores the Category object during conversion.

---

## 3. ReviewMapper

Responsible for converting Review DTOs and Review Entity.

### Features

- Convert CreateReviewRequest → Review
- Convert Review → ReviewResponse

### Notes

- Product relationship is assigned inside the Service layer.

---

# Why MapStruct?

Instead of writing manual code like:

```java
Product product = new Product();
product.setProductName(request.getProductName());
product.setBrand(request.getBrand());
...
```

MapStruct automatically generates this code during compilation.

Advantages:

- Less Boilerplate Code
- Better Performance
- Compile-Time Type Safety
- Easy Maintenance
- Cleaner Service Layer

---

# Mapping Flow

```
Client
    │
    ▼
Request DTO
    │
    ▼
Mapper
    │
    ▼
Entity
    │
Database
    │
Entity
    ▼
Mapper
    │
Response DTO
    ▼
Client
```

---

# Technologies Used

- MapStruct
- Lombok
- Spring Boot
- Spring Data JPA

---

# Phase Completion

✅ CategoryMapper

✅ ProductMapper

✅ ReviewMapper

Compilation Status

```bash
.\mvnw.cmd compile
```

Result

```
BUILD SUCCESS
```

---
