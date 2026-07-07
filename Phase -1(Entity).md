# Phase 1 – Product Module Entity Layer

## Objective

Develop the core database entities for the Product Catalog Management module of the Enterprise Multi-Vendor E-Commerce Platform.

This phase establishes the database structure that will be used throughout the Product module.

---

## Implemented Entities

### 1. Category Entity

Represents the product categories available in the platform.

#### Fields

| Field | Type | Description |
|--------|------|-------------|
| id | UUID | Primary Key (Inherited from BaseEntity) |
| categoryName | String | Unique category name |
| description | String | Category description |
| active | Boolean | Indicates whether the category is active |

#### Features

- Unique category names
- Soft activation/deactivation
- Audit fields inherited from BaseEntity

---

### 2. Product Entity

Represents products listed by vendors.

#### Fields

| Field | Type | Description |
|--------|------|-------------|
| id | UUID | Primary Key |
| productName | String | Product name |
| brand | String | Brand name |
| description | String | Product description |
| imageUrl | String | Product image path |
| price | BigDecimal | Product price |
| stockQuantity | Integer | Available stock |
| vendorId | Long | Vendor reference (temporary) |
| category | Category | Product category |
| featured | Boolean | Featured product flag |
| active | Boolean | Product availability |

#### Features

- Category relationship
- Vendor reference (temporary until Vendor module integration)
- Inventory support
- Product pricing
- Product status management

---

### 3. Review Entity

Stores customer reviews and ratings for products.

#### Fields

| Field | Type | Description |
|--------|------|-------------|
| id | UUID | Primary Key |
| product | Product | Reviewed product |
| customerName | String | Customer name |
| rating | Integer | Rating (1–5) |
| review | String | Review comment |

#### Features

- Product review support
- Customer feedback
- Product ratings

---

# Entity Relationships

Category (1)
│
└──────────────► Product (Many)
                     │
                     │
                     ▼
               Review (Many)

---

# Database Tables

## categories

- id
- category_name
- description
- is_active
- created_at
- updated_at
- deleted

---

## products

- id
- product_name
- brand
- description
- image_url
- price
- stock_quantity
- vendor_id
- category_id
- is_featured
- is_active
- created_at
- updated_at
- deleted

---

## reviews

- id
- product_id
- customer_name
- rating
- review
- created_at
- updated_at
- deleted

---

# Technologies Used

- Java 21
- Spring Boot 3.5
- Spring Data JPA
- Hibernate
- Lombok
- PostgreSQL (Target Database)

---

# Notes

- All entities extend `BaseEntity` to inherit:
  - UUID Primary Key
  - Created Timestamp
  - Updated Timestamp
  - Version
  - Soft Delete Flag

- `vendorId` is currently stored as a simple `Long` field because the Vendor module is being developed independently. It will be replaced with a proper JPA relationship after the Vendor module is integrated.

---

# Phase Status

✅ Category Entity Completed

✅ Product Entity Completed

✅ Review Entity Completed

**Next Phase:** Repository Layer
