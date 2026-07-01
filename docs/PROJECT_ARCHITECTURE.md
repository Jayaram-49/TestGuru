# TestGuru - Project Architecture

## 1. System Overview

TestGuru is a web-based technical assessment platform built using a modern three-tier architecture.

The application consists of:

- Frontend (React)
- Backend (Spring Boot REST API)
- Database (PostgreSQL)

The frontend communicates with the backend through REST APIs, and the backend manages business logic, authentication, and database operations.

## 2. High-Level Architecture

Candidate / Hiring Organization / Admin
                │
                ▼
        React Frontend
                │
        REST API (HTTP/HTTPS)
                │
                ▼
      Spring Boot Backend
                │
        Spring Data JPA
                │
                ▼
         PostgreSQL Database

## 3. Technology Stack

### Frontend
- React
- JavaScript
- HTML5
- CSS3

### Backend
- Java 17
- Spring Boot
- Spring Security
- Spring Data JPA
- Maven

### Database
- PostgreSQL

### Tools
- Git
- GitHub
- Postman
- IntelliJ IDEA

## 4. Backend Architecture

The backend follows a layered architecture to separate responsibilities and improve maintainability.

backend/
└── src/
    └── main/
        ├── java/
        │   └── com/
        │       └── testguru/
        │           ├── config/
        │           ├── controller/
        │           ├── dto/
        │           ├── entity/
        │           ├── exception/
        │           ├── repository/
        │           ├── security/
        │           ├── service/
        │           ├── util/
        │           └── TestGuruApplication.java
        │
        └── resources/
            ├── application.properties
            └── static/

## 5. Frontend Architecture

frontend/
└── src/
    ├── assets/
    ├── components/
    ├── layouts/
    ├── pages/
    ├── services/
    ├── hooks/
    ├── contexts/
    ├── routes/
    ├── utils/
    ├── App.jsx
    └── main.jsx

