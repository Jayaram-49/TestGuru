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

## 6. Authentication Flow

TestGuru uses JWT (JSON Web Token) for secure authentication.

### Login Flow

1. User enters email and password.
2. Frontend sends login request to the backend.
3. Backend validates the credentials.
4. Backend generates a JWT token.
5. Frontend stores the JWT token.
6. Frontend includes the JWT token in every protected API request.
7. Backend validates the token before processing the request.

### User Roles

- Administrator
- Hiring Organization
- Candidate

Each role has access only to the features and APIs assigned to it.

## 7. REST API Design

### Authentication

POST /api/auth/register

POST /api/auth/login

POST /api/auth/logout

---

### Organizations

GET /api/organizations

GET /api/organizations/{id}

PUT /api/organizations/{id}

---

### Assessments

POST /api/assessments

GET /api/assessments

GET /api/assessments/{id}

PUT /api/assessments/{id}

DELETE /api/assessments/{id}

---

### Questions

POST /api/questions

GET /api/questions/{assessmentId}

PUT /api/questions/{id}

DELETE /api/questions/{id}

---

### Attempts

POST /api/attempts/start

POST /api/attempts/submit

GET /api/attempts/{id}

---

### Results

GET /api/results/{attemptId}

GET /api/results/candidate

GET /api/results/assessment/{assessmentId}

## 8. Development Roadmap

### Phase 1
- Project Setup
- Software Requirements
- Database Design
- System Architecture

### Phase 2
- Spring Boot Backend Development
- JWT Authentication
- Database Integration

### Phase 3
- React Frontend Development
- API Integration
- UI Improvements

### Phase 4
- Testing
- Deployment
- Documentation