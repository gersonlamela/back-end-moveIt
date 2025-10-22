# MoveIt — Authentication API

## 📋 Overview

**MoveIt Auth API** is a backend authentication system built with **Spring Boot 3**, **Java 21**, and **JWT** for secure token-based authentication.  
It provides endpoints for user registration, login, and user management, integrating seamlessly with the **MoveIt Frontend**.

This API follows RESTful design principles and ensures secure communication between the client and the server using Spring Security and JWT.

---

## 🧠 Features

- 🔐 **JWT Authentication** — Secure login and token validation  
- 👤 **User Management** — Register and authenticate users  
- 🧾 **DTO Layer** — Clean data transfer between layers  
- 🧱 **Layered Architecture** — Controllers, Services, Domain, DTO, and Repositories  
- ⚙️ **Spring Security Configuration** — Custom filters and token validation  
- 🔄 **CORS Configuration** — Enables secure communication with the frontend  
- 🧰 **H2 Database** — In-memory database for local development  

---

## 🛠️ Technologies

| Category | Stack |
|-----------|--------|
| Framework | Spring Boot 3.5.6 |
| Language | Java 21 |
| Build Tool | Maven |
| Security | Spring Security + JWT |
| Database | H2 (in-memory) |
| ORM | Spring Data JPA |
| Lombok | For boilerplate code reduction |

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/gersonlamela/Back-end-moveIt.git
cd Back-end-moveIt
```

### 2️⃣ Build the project

```bash
mvn clean install
```

### 3️⃣ Run the API

```bash
mvn spring-boot:run
```

The API will be available at:  
👉 [http://localhost:8080](http://localhost:8080)

---

## 📂 Folder Structure

```
src/
 └── main/
     └── java/
         └── com/gersonlamela_auth/auth_api/
             ├── controllers/
             │   ├── AuthController
             │   └── UserController
             ├── domain/user/
             │   └── User
             ├── dto/
             │   ├── LoginRequestDTO
             │   ├── RegisterRequestDTO
             │   └── ResponseDTO
             ├── infra/security/
             │   ├── cors/
             │   │   └── CorsConfig
             │   ├── CustomUserDetailsService
             │   ├── SecurityConfig
             │   ├── SecurityFilter
             │   └── TokenService
             ├── repositories/
             │   └── UserRepository
             └── AuthApiApplication.java
```

---

## 🔑 API Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| `POST` | `/auth/register` | Register a new user |
| `POST` | `/auth/login` | Authenticate user and return JWT |
| `GET` | `/users` | Get the authenticated user's data (secured route) |

---

## 🧩 JWT Authentication Flow

1. User sends credentials to `/auth/login`
2. Server validates user and generates a **JWT token**
3. Token is sent to the frontend and stored in `sessionStorage`
4. Subsequent requests must include the header:  
   `Authorization: Bearer <token>`
5. The token is validated by `SecurityFilter` on each request

---

## 🧑‍💻 Author

**Gerson Lamela**  
Full-Stack Developer | [LinkedIn](https://linkedin.com/in/gersonlamela)  
Frontend: [MoveIt Frontend](https://github.com/gersonlamela/front-end-moveIt)  
Backend: [MoveIt Backend](https://github.com/gersonlamela/Back-end-moveIt)

---

## 🪪 License

This project is licensed under the **MIT License** — feel free to use and adapt it.
