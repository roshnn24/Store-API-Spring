# 🛒 Store API Spring

A **production-ready backend API** built with **Spring Boot** and **MySQL** for a modern grocery store application.  
This API handles everything from user authentication to product management, cart operations, and checkout using **Stripe** integration.

---

## 🚀 Features

- 🔐 **JWT Authentication** with Spring Security  
- 👤 **User & Admin Roles** for access control  
- 🧾 **User Registration & Login** endpoints  
- 🛍️ **Product Management** (create, update, delete, list)  
- 🛒 **Shopping Cart** creation and item management  
- 💳 **Stripe Checkout Integration** for secure payments  
- 🔄 **Stripe Webhooks** for order updates and status syncing  
- 📘 **Swagger API Documentation** included  
- 🧠 **EntityGraph & MapStruct** for optimized data access and DTO mapping  

---

## 🧰 Tech Stack

| Layer | Technology |
|-------|-------------|
| **Backend Framework** | Spring Boot |
| **Security** | Spring Security, JWT |
| **ORM / Persistence** | Hibernate, JPA, JPA Buddy |
| **Mapping** | MapStruct |
| **Database** | MySQL |
| **Build Tool** | Maven |
| **API Documentation** | Swagger (OpenAPI) |
| **Utilities** | Lombok, Entity Graph |
| **Payments** | Stripe API Integration |

---

## 🏗️ Project Structure

```

src/
├── main/
│   ├── java/com/example/storeapi/
│   │   ├── controller/      # REST Controllers
│   │   ├── service/         # Business Logic
│   │   ├── repository/      # JPA Repositories
│   │   ├── dto/             # Data Transfer Objects
│   │   ├── config/          # Security & App Configurations
│   │   └── entity/          # JPA Entities
│   └── resources/
│       ├── application.yaml # Database & Stripe Configurations
│       └── static/
└── test/                    # Unit and Integration Tests

````

---

## ⚙️ Setup & Installation

### 1️⃣ Clone the repository
```bash
git clone https://github.com/<your-username>/store-api-spring.git
cd store-api-spring
````

### 2️⃣ Configure Database Connection

Update your **`application.yaml`** file with your local or Railway MySQL credentials:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/store_api
    username: root
    password: yourpassword
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
```

### 3️⃣ Stripe Configuration

Add your Stripe keys:

```yaml
stripe:
  secret-key: YOUR_STRIPE_SECRET_KEY
  webhook-secret: YOUR_STRIPE_WEBHOOK_SECRET
```

---

## ▶️ Run the Application

Run directly from your IDE (by executing the `StoreApiSpringApplication` class)
or via terminal:

```bash
mvn spring-boot:run
```

Application runs by default on:
👉 **[http://localhost:8080](http://localhost:8080)**

---

## 📘 API Endpoints Overview

| Module       | Method | Endpoint              | Description                        |
| ------------ | ------ | --------------------- | ---------------------------------- |
| **Auth**     | `POST` | `/api/auth/register`  | Register new user                  |
| **Auth**     | `POST` | `/api/auth/login`     | Login and receive JWT              |
| **Products** | `GET`  | `/api/products`       | Get all products                   |
| **Products** | `POST` | `/api/products`       | Create a new product (Admin only)  |
| **Cart**     | `POST` | `/api/cart`           | Create a cart for a user           |
| **Cart**     | `POST` | `/api/cart/add`       | Add item to cart                   |
| **Cart**     | `GET`  | `/api/cart`           | View cart items                    |
| **Checkout** | `POST` | `/api/checkout`       | Create Stripe checkout session     |
| **Webhook**  | `POST` | `/api/stripe/webhook` | Handle payment updates from Stripe |

---

## 📄 Swagger API Documentation

Once the app is running, explore the API endpoints using Swagger UI:
👉 **[http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)**

---

## ☁️ Deployment (Planned)

The project is being prepared for deployment on **[Railway.app](https://railway.app/)**.
Once deployed, the live API endpoint and documentation URL will be added here.

---

## 🧑‍💻 Author

**Roshaun Infant R**
🔗 [GitHub Profile](https://github.com/roshaunr) *(update link if different)*

---

## 🪪 License

This project is currently **not licensed**.
All rights reserved by the author.

---

## 💡 Future Enhancements

* 🧾 Add order history and invoices
* 📦 Introduce inventory management
* 📧 Email notifications for successful checkouts
* ☁️ Dockerize and deploy with CI/CD pipeline
