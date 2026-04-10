# Project Name

Brief description of what this system does and what problem it solves.  
Example: *REST API for freight cost calculation and cargo tracking in import/export operations.*

---

## Tech Stack

- **Language:** Java 17
- **Framework:** Spring Boot 3.x
- **Database:** MySQL / MongoDB
- **Security:** Spring Security + JWT
- **Docs:** Springdoc OpenAPI (Swagger)
- **Build:** Maven
- **Containerization:** Docker

---

## Prerequisites

- Java 17+
- Docker and Docker Compose
- Maven 3.8+

---

## Running locally

**With Docker (recommended):**

```bash
docker-compose up
```

**Without Docker:**

```bash
# 1. Configure the database in application.properties
# 2. Run
mvn spring-boot:run
```

Application starts at `http://localhost:8080`  
Swagger UI: `http://localhost:8080/swagger-ui.html`

---

## Main Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/resource` | Create resource |
| GET | `/api/resource/{id}` | Get resource by ID |
| PUT | `/api/resource/{id}` | Update resource |
| DELETE | `/api/resource/{id}` | Delete resource |

> Full documentation available via Swagger UI when running locally.

---

## Architecture

This project follows **Clean Architecture** principles with clear separation between layers:

```
src/
├── domain/          # Entities, value objects, domain rules
├── application/     # Use cases, input/output ports
├── infrastructure/  # Database, external services, repositories
└── adapters/        # Controllers, DTOs, mappers
```

Key design decisions:
- Domain layer has zero framework dependencies
- Use cases are orchestrated through input ports (interfaces)
- Database and framework details are isolated in the infrastructure layer

---

## Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `DB_URL` | Database connection URL | `jdbc:mysql://localhost:3306/dbname` |
| `DB_USER` | Database username | `root` |
| `DB_PASS` | Database password | `secret` |
| `JWT_SECRET` | JWT signing key | `your-secret-key` |

---

## Author

**Everson Rubira**  
[LinkedIn](https://www.linkedin.com/in/eversonrubira) · [GitHub](https://github.com/EversonRubira)
