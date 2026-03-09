# Ticket Management System (TMS)

A microservices-based ticket management system built with Spring Boot 4 and Java 25.

## Architecture

The system is composed of five Spring Boot services:

| Service | Description | Key technologies |
|---------|-------------|------------------|
| **api-gateway** | Single entry point, routing and OAuth2 validation | Spring Cloud Gateway (WebFlux), OAuth2 Resource Server |
| **auth-service** | Authentication, user management, JWT issuance | Spring Security, JPA, Flyway, PostgreSQL, Spring AI (Redis vector store), Mail |
| **ticket-service** | Ticket lifecycle and business logic | Spring Data JPA, Flyway, PostgreSQL, Kafka, OAuth2 |
| **notification-service** | Notifications and real-time updates | Spring Data JPA, Kafka, WebSocket, PostgreSQL |
| **file-service** | File upload and storage | Spring Data JPA, Flyway, PostgreSQL, OAuth2 |

## Tech stack

- **Java** 25  
- **Spring Boot** 4.0.3  
- **Spring Cloud** 2025.1.0 (Gateway)  
- **Spring AI** 2.0.0-M2 (auth-service, Redis vector store)  
- **PostgreSQL** (persistence)  
- **Apache Kafka** (event-driven communication between ticket and notification services)  
- **Redis** (vector store for auth-service)  
- **OAuth2** (JWT-based security across gateway and services)

## Prerequisites

- JDK 25  
- Maven 3.x  
- PostgreSQL  
- Apache Kafka  
- Redis (for auth-service)

## Running the services

Each service is a standalone Maven project. From the project root:

```bash
# API Gateway
cd api-gateway && ./mvnw spring-boot:run

# Auth Service
cd auth-service && ./mvnw spring-boot:run

# Ticket Service
cd ticket-service && ./mvnw spring-boot:run

# Notification Service
cd notification-service && ./mvnw spring-boot:run

# File Service
cd file-service && ./mvnw spring-boot:run
```

Configure each service via `src/main/resources/application.properties` (or environment variables) for database, Kafka, Redis, and OAuth2 settings as needed.

## Project structure

```
ticket-management-system/
├── api-gateway/           # Spring Cloud Gateway
├── auth-service/          # Authentication & user management
├── ticket-service/        # Ticket domain
├── notification-service/  # Notifications & WebSocket
├── file-service/          # File storage
├── docker-compose.yml
├── LICENSE
└── README.md
```

## License

Copyright (c) 2026 Di2iT, Unipessoal Lda.  
This project is licensed under the [Business Source License 1.1](LICENSE).  
Change Date: 2029-01-01 → Change License: Apache 2.0.
