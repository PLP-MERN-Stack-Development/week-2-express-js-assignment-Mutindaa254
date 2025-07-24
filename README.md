# 🚂 Week 2: Express.js – Server-Side Framework

## 🚀 Objective
Build a RESTful API using **Express.js** that implements:
- Standard CRUD operations
- Proper routing structure
- Middleware implementation (logging, authentication, validation)
- Robust error handling
- Advanced features like filtering, pagination, and search

---

## 📂 Tasks Overview

### ✅ Task 1: Express.js Setup
- Initialize Node.js project
- Install dependencies
- Create a basic Express server (`server.js`) on port `3000`
- Add a test route: `GET /` → returns `"Hello World"`

### ✅ Task 2: RESTful API Routes – `/api/products`
Product fields:
- `id` (UUID)
- `name` (string)
- `description` (string)
- `price` (number)
- `category` (string)
- `inStock` (boolean)

**Endpoints:**
| Method | Endpoint              | Description              |
|--------|-----------------------|--------------------------|
| GET    | `/api/products`       | List all products        |
| GET    | `/api/products/:id`   | Get product by ID        |
| POST   | `/api/products`       | Create new product       |
| PUT    | `/api/products/:id`   | Update existing product  |
| DELETE | `/api/products/:id`   | Delete a product         |

### ✅ Task 3: Middleware
- **Logger** – logs method, URL, and timestamp
- **JSON parser** – parses incoming `application/json`
- **Authentication** – validates API key in headers
- **Validation** – ensures product data is valid for POST/PUT

### ✅ Task 4: Error Handling
- Global error handler middleware
- Custom error classes: `NotFoundError`, `ValidationError`, etc.
- Error responses with appropriate status codes
- Async error handling using wrapper or try/catch

### ✅ Task 5: Advanced Features
- Filter products by `category` (e.g., `GET /api/products?category=electronics`)
- Pagination (e.g., `GET /api/products?page=2&limit=10`)
- Search products by name (`GET /api/products/search?name=solar`)
- Product statistics route (`GET /api/products/stats`) → return count by category

---

## 🧪 Example API Usage

### 📥 Create a Product
```http
POST /api/products
Content-Type: application/json
x-api-key: your-api-key

{
  "name": "Solar Panel",
  "description": "High efficiency",
  "price": 199.99,
  "category": "Electronics",
  "inStock": true
}
