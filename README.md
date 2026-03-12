# 🚀 Spring Boot REST API

A production-ready RESTful API built with **Spring Boot** and **Java 17**, backed by a **PostgreSQL** database running in Docker. This project demonstrates clean backend architecture, database integration via Spring Data JPA, and a fully containerized development environment.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Technologies](#technologies)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
- [API Endpoints](#api-endpoints)
- [What I Learned](#what-i-learned)

---

## Overview

This project is a full-featured backend service that exposes a REST API using Spring MVC. It connects to a PostgreSQL database managed through Docker Compose, and uses Spring Data JPA for clean, repository-based data access. The goal was to build a scalable, testable, and maintainable backend foundation following industry best practices.

---

## Technologies

| Technology | Version | Purpose |
|---|---|---|
| Java | 17 | Core language |
| Spring Boot | Latest | Application framework |
| Spring MVC | — | REST API layer |
| Spring Data JPA | — | Database abstraction |
| PostgreSQL | Latest | Relational database |
| Docker | — | Containerization |
| Docker Compose | — | Multi-container orchestration |
| Maven | — | Build & dependency management |
| IntelliJ IDEA | — | Development environment |

---

## Architecture

> 📌 _Architecture diagram coming soon_

```
┌─────────────────────────────────────────────┐
│                  Client                     │
└────────────────────┬────────────────────────┘
                     │ HTTP Requests
┌────────────────────▼────────────────────────┐
│            Spring Boot Application          │
│  ┌──────────────────────────────────────┐   │
│  │         REST Controllers             │   │
│  │         (Spring MVC)                 │   │
│  └──────────────┬───────────────────────┘   │
│  ┌──────────────▼───────────────────────┐   │
│  │         Service Layer                │   │
│  └──────────────┬───────────────────────┘   │
│  ┌──────────────▼───────────────────────┐   │
│  │     Repository (Spring Data JPA)     │   │
│  └──────────────┬───────────────────────┘   │
└─────────────────┼───────────────────────────┘
                  │
┌─────────────────▼───────────────────────────┐
│         PostgreSQL (Docker Container)        │
└─────────────────────────────────────────────┘
```

---

## Getting Started

### Prerequisites

- [Java 17](https://adoptium.net/)
- [Docker & Docker Compose](https://www.docker.com/)
- [Maven](https://maven.apache.org/)
- [IntelliJ IDEA](https://www.jetbrains.com/idea/) _(recommended)_

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/spring-boot-rest-api.git
cd spring-boot-rest-api
```

### 2. Start the PostgreSQL Database

```bash
docker-compose up -d
```

This spins up a PostgreSQL instance as defined in `docker-compose.yml`.

### 3. Configure Application Properties

Update `src/main/resources/application.properties` if needed:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/your_db
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
```

### 4. Run the Application

```bash
./mvnw spring-boot:run
```

The API will be available at `http://localhost:8080`.

---

## API Endpoints

> 📌 _Screenshots / Postman collection coming soon_

### Base URL: `http://localhost:8080/api`

| Method | Endpoint | Description | Request Body | Response |
|--------|----------|-------------|--------------|----------|
| `GET` | `/resource` | Get all records | — | `200 OK` + JSON array |
| `GET` | `/resource/{id}` | Get record by ID | — | `200 OK` + JSON object |
| `POST` | `/resource` | Create a new record | JSON body | `201 Created` + JSON object |
| `PUT` | `/resource/{id}` | Update a record | JSON body | `200 OK` + JSON object |
| `DELETE` | `/resource/{id}` | Delete a record | — | `204 No Content` |

> Replace `/resource` with your actual resource name (e.g., `/students`, `/products`).

### Example Request

```bash
curl -X POST http://localhost:8080/api/resource \
  -H "Content-Type: application/json" \
  -d '{"name": "Example", "description": "Sample payload"}'
```

### Example Response

```json
{
  "id": 1,
  "name": "Example",
  "description": "Sample payload",
  "createdAt": "2025-01-01T12:00:00"
}
```

---

## What I Learned

- ✅ How to design and implement **REST APIs** using **Spring Boot** and **Spring MVC**
- ✅ How to connect a Spring Boot application to a real **PostgreSQL** database via **Docker**
- ✅ How to use **Spring Data JPA** for clean, repository-based database interactions
- ✅ How to set up a professional **development environment** with IntelliJ IDEA and Maven
- ✅ How to write **clean, testable, and scalable** backend services
- ✅ How to use **Docker** and **Docker Compose** to manage containerized databases

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

> Built with ☕ Java and 🌱 Spring Boot
