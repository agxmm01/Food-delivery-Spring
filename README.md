# 🍽️ Dish-Dash Backend API

Dish-Dash is a **Spring Boot 3.x backend service** for an online food
ordering platform.\
It manages users, restaurants, food items, and orders using **MongoDB**
for persistence.

This backend is designed to integrate seamlessly with a **React (Vite)
frontend** and provides secure authentication with **Spring Security
(session-based).**

------------------------------------------------------------------------

## 🚀 Features

-   🔐 User Authentication & Role-Based Access Control (Spring
    Security + Session)
-   🏪 Multi-Restaurant Management (Restaurant Owner role)
-   🍔 CRUD Operations for Food Items
-   🛒 Order Placement & Status Tracking
-   🗄️ MongoDB Atlas Integration
-   ☁️ AWS S3 Integration (Food & Restaurant Images)
-   🌐 RESTful APIs for Frontend Integration
-   🛡️ Global Exception Handling

------------------------------------------------------------------------

## 🛠️ Tech Stack

  Technology            Version
  --------------------- -----------------------
  Java                  17
  Spring Boot           3.x
  Spring Security       6.x
  Spring Data MongoDB   Latest
  MongoDB Atlas         Cloud Database
  AWS SDK (S3)          v2
  Maven                 Build Tool
  Lombok                Boilerplate Reduction

------------------------------------------------------------------------

## 📂 Project Structure

    src/main/java/in/agampal/dishdashapi
    │
    ├── config/          # Security configuration & application setup
    ├── controller/      # REST Controllers (API endpoints)
    ├── dto/             # Data Transfer Objects
    ├── entity/          # MongoDB Documents (User, Restaurant, FoodItem, Order)
    ├── exception/       # Custom exceptions & global exception handler
    ├── filters/         # Security filters (Session/JWT if implemented)
    ├── io/              # Request & Response models
    ├── repository/      # Spring Data MongoDB repositories
    ├── service/         # Business logic layer
    ├── util/            # Utility/helper classes
    │
    └── FoodiesapiApplication.java   # Main Spring Boot entry point

------------------------------------------------------------------------

## ⚙️ Setup & Installation

### 1️⃣ Clone the Repository

``` bash
git clone https://github.com/agxmm01/Dish-Dash_BACKEND_API.git
cd Dish-Dash_BACKEND_API
```

------------------------------------------------------------------------

### 2️⃣ Configure Environment Variables

Update `application.properties`:

``` properties
# MongoDB
spring.data.mongodb.uri=mongodb+srv://<username>:<password>@cluster-url/dbname

# AWS S3
AWS_ACCESS_KEY=your-access-key
AWS_SECRET_KEY=your-secret-key
AWS_BUCKET_NAME=your-bucket-name

# Server
server.port=8080
```

------------------------------------------------------------------------

### 3️⃣ Build & Run

``` bash
mvn clean install
mvn spring-boot:run
```

Application will start at:

👉 http://localhost:8080

------------------------------------------------------------------------

## 📡 API Endpoints

### 🔐 Authentication

  Method   Endpoint           Description
  -------- ------------------ --------------------------------------
  POST     `/auth/register`   Register new user (Customer / Owner)
  POST     `/auth/login`      Login (Session-based)
  POST     `/auth/logout`     Logout

------------------------------------------------------------------------

### 🏪 Restaurants

  Method   Endpoint              Description
  -------- --------------------- --------------------------------
  POST     `/restaurants`        Create restaurant (Owner only)
  GET      `/restaurants`        Get all restaurants
  GET      `/restaurants/{id}`   Get restaurant by ID

------------------------------------------------------------------------

### 🍔 Food Items

  Method   Endpoint                   Description
  -------- -------------------------- ------------------------------
  POST     `/restaurants/{id}/food`   Add food item (Owner only)
  GET      `/restaurants/{id}/food`   Get food items by restaurant
  PUT      `/food/{id}`               Update food item
  DELETE   `/food/{id}`               Delete food item

------------------------------------------------------------------------

### 🛒 Orders

  Method   Endpoint                Description
  -------- ----------------------- -----------------------------------
  POST     `/orders`               Place new order
  GET      `/orders/{id}`          Get order details
  PUT      `/orders/{id}/status`   Update order status (Owner/Admin)

------------------------------------------------------------------------
