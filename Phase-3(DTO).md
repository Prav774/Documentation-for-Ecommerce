# Phase 3 – DTO (Data Transfer Object) Layer

## Objective

Develop the DTO layer for the Product Catalog Management module.

The DTO layer acts as the communication layer between the client and the backend. It transfers only the required data and prevents exposing database entities directly.

---

# Folder Structure

```
product
└── dto
    ├── requests
    │     ├── CreateCategoryRequest.java
    │     ├── UpdateCategoryRequest.java
    │     ├── CreateProductRequest.java
    │     ├── UpdateProductRequest.java
    │     └── CreateReviewRequest.java
    │
    └── responses
          ├── CategoryResponse.java
          ├── ProductResponse.java
          └── ReviewResponse.java
```

---

# Request DTOs

## CreateCategoryRequest

Used to create a new product category.

### Fields

- categoryName
- description

---

## UpdateCategoryRequest

Used to update an existing category.

### Fields

- categoryName
- description
- active

---

## CreateProductRequest

Used to create a new product.

### Fields

- productName
- brand
- description
- imageUrl
- price
- stockQuantity
- vendorId
- categoryId
- featured

---

## UpdateProductRequest

Used to update an existing product.

### Fields

- productName
- brand
- description
- imageUrl
- price
- stockQuantity
- vendorId
- categoryId
- featured
- active

---

## CreateReviewRequest

Used to add a customer review.

### Fields

- customerName
- rating
- review

---

# Response DTOs

## CategoryResponse

Returns category information to the client.

### Fields

- id
- categoryName
- description
- active

---

## ProductResponse

Returns complete product information.

### Fields

- id
- productName
- brand
- description
- imageUrl
- price
- stockQuantity
- vendorId
- categoryId
- categoryName
- featured
- active

---

## ReviewResponse

Returns review information.

### Fields

- id
- customerName
- rating
- review

---

# Validation Used

The DTO layer uses Jakarta Bean Validation.

Validation annotations include:

- @NotBlank
- @NotNull
- @Size
- @Min
- @Max
- @DecimalMin

These validations ensure invalid input is rejected before reaching the service layer.

---

# DTO Workflow

```
Client
   │
   ▼
Request DTO
   │
Controller
   │
Service
   │
Entity
   │
Database
   │
Entity
   │
Service
   │
Response DTO
   │
Client
```

---

# Advantages

- Prevents exposing database entities
- Performs input validation
- Improves API security
- Reduces unnecessary data transfer
- Simplifies controller logic
- Supports clean architecture

---

# Phase Completion

✅ CreateCategoryRequest

✅ UpdateCategoryRequest

✅ CreateProductRequest

✅ UpdateProductRequest

✅ CreateReviewRequest

✅ CategoryResponse

✅ ProductResponse

✅ ReviewResponse

Compilation Status:

```bash
.\mvnw.cmd compile
```

Result:

```
BUILD SUCCESS
```

---
