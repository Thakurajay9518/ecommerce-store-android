# Ecommerce-store-android
End-to-end e-commerce mobile application featuring dynamic cart state management, RecyclerView caching, and REST backend synchronization.  
Topics / Tags: android, java, recyclerview, sharedpreferences, rest-api, ecommerce
# 🛒 Grocery Store – Full-Stack E-Commerce Mobile Application

Grocery Store is a native Android e-commerce application integrated with a Spring Boot RESTful backend and MySQL database. The architecture follows a decoupled client-server model, utilizing Retrofit for asynchronous network communication and SharedPreferences for local session persistence.

---

## 📌 Architecture Overview
[ Android App (Java) ]
│  HTTP / REST (Retrofit 2 & OkHttp)
▼
[ Spring Boot REST API (Port 8080) ]
│  Spring Data JPA / Hibernate ORM
▼
[ MySQL Relational Database (Port 3306) ]

## 🚀 Key Features

* **User Authentication & Session Management**: Secure user registration (`/users/signUp`) and authentication (`/users/signIn`). Active session state is maintained locally using `SharedPreferences`.
* **Dynamic Product Catalog**: Real-time product retrieval (`GET /products`) parsed asynchronously via Gson and presented through an optimized `RecyclerView` with custom `CardView` cards.
* **Cart Management System**: Real-time cart synchronization enabling users to add products (`POST /cart/add`), view current items (`GET /cart/user/{id}`), remove items (`DELETE /cart/remove/{id}`), and compute dynamically calculated bill totals.
* **Network & Error Handling**: Non-blocking asynchronous network execution on background threads using Retrofit `enqueue()` callbacks with built-in network failure recovery.

---

## 🛠️ Technology Stack

### Client Side (Android)
* **Language**: Java
* **UI Components**: XML, ConstraintLayout, RecyclerView, CardView, Material Design
* **Networking**: Retrofit 2, OkHttp 3, Gson Converter
* **Storage**: Android SharedPreferences

### Server Side (Backend)
* **Framework**: Spring Boot (Maven)[cite: 1]
* **Language**: Java 17+[cite: 1]
* **ORM & Database**: Spring Data JPA, Hibernate, MySQL[cite: 1]
* **Architecture**: MVC Pattern (Controller, Service, Repository, Entity, DTO)[cite: 1]



## 🔌 API Endpoints Reference

| Module | Method | Endpoint | Description |
| :--- | :--- | :--- | :--- |
| **Auth** | `POST` | `/users/signUp` | Register a new user[cite: 1] |
| **Auth** | `POST` | `/users/signIn` | Authenticate user credentials[cite: 1] |
| **Products** | `GET` | `/products` | Fetch entire product catalog[cite: 1] |
| **Cart** | `POST` | `/cart/add` | Add an item to user's cart[cite: 1] |
| **Cart** | `GET` | `/cart/user/{userId}` | Retrieve cart items for specified user[cite: 1] |
| **Cart** | `DELETE`| `/cart/remove/{cartItemId}` | Remove a specific item from cart[cite: 1] |
