# Phase 6 – Controller Layer

## Objective

Develop the REST Controller layer for the Product Catalog Management module.

The Controller layer acts as the entry point for client requests. It receives HTTP requests, validates incoming data, invokes the Service layer, and returns appropriate responses.

---

# Folder Structure

```
product
└── controller
    ├── CategoryController.java
    ├── ProductController.java
    └── ReviewController.java
```

---

# Controller Architecture

```
Client (Frontend / Postman)
            │
            ▼
      REST Controller
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

The Controller layer does not contain business logic. It only handles request routing and delegates processing to the Service layer.

---

# CategoryController

## Base URL

```
/api/categories
```

## Implemented APIs

| HTTP Method | Endpoint | Description |
|-------------|----------|-------------|
| POST | /api/categories | Create a new category |
| PUT | /api/categories/{id} | Update category |
| DELETE | /api/categories/{id} | Delete category |
| GET | /api/categories/{id} | Get category by ID |
| GET | /api/categories | Get all categories |

---

# ProductController

## Base URL

```
/api/products
```

## Implemented APIs

| HTTP Method | Endpoint | Description |
|-------------|----------|-------------|
| POST | /api/products | Create product |
| PUT | /api/products/{id} | Update product |
| DELETE | /api/products/{id} | Delete product |
| GET | /api/products/{id} | Get product by ID |
| GET | /api/products | Get all products |
| GET | /api/products/search?keyword= | Search products |
| GET | /api/products/category/{categoryId} | Products by category |
| GET | /api/products/brand/{brand} | Products by brand |
| GET | /api/products/vendor/{vendorId} | Products by vendor |
| GET | /api/products/featured | Featured products |
| GET | /api/products/active | Active products |
| GET | /api/products/price?min=&max= | Products by price range |

---

# ReviewController

## Base URL

```
/api/reviews
```

## Implemented APIs

| HTTP Method | Endpoint | Description |
|-------------|----------|-------------|
| POST | /api/reviews/{productId} | Add review |
| GET | /api/reviews/{productId} | Get reviews of a product |
| DELETE | /api/reviews/{reviewId} | Delete review |

---

# HTTP Methods Used

| Method | Purpose |
|---------|----------|
| GET | Retrieve data |
| POST | Create new resource |
| PUT | Update existing resource |
| DELETE | Remove resource |

---

# Spring Boot Features Used

- @RestController
- @RequestMapping
- @GetMapping
- @PostMapping
- @PutMapping
- @DeleteMapping
- @RequestBody
- @PathVariable
- @RequestParam
- @Valid
- Constructor Dependency Injection (Lombok)

---

# Request Processing Flow

```
Client Request
      │
      ▼
Controller
      │
      ▼
Request Validation
      │
      ▼
Service Layer
      │
      ▼
Repository
      │
      ▼
Database
      │
      ▼
Repository
      │
      ▼
Service Layer
      │
      ▼
Response DTO
      │
      ▼
Client
```

---

# Validation

Incoming requests are validated using Jakarta Bean Validation annotations.

Examples:

- @Valid
- @NotBlank
- @NotNull
- @Size
- @Min
- @Max
- @DecimalMin

Invalid requests are automatically handled by the project's GlobalExceptionHandler.

---

# Advantages

- Clean REST API design
- Separation of concerns
- DTO-based communication
- Automatic request validation
- Easy integration with frontend applications
- Supports future scalability

---

# Completed Controllers

## Category

- Create Category
- Update Category
- Delete Category
- Get Category
- Get All Categories

---

## Product

- Create Product
- Update Product
- Delete Product
- Get Product
- Search Products
- Filter Products
- Featured Products
- Active Products

---

## Review

- Add Review
- Get Product Reviews
- Delete Review

---

# Phase Completion

✅ CategoryController Completed

✅ ProductController Completed

✅ ReviewController Completed

Compilation Check

```bash
.\mvnw.cmd clean compile
```

Result

```
BUILD SUCCESS
```

---
