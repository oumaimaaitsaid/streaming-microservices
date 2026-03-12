# Video Streaming Platform Microservices

Backend application for a video streaming platform using Spring Boot and Spring Cloud.

## Architecture
- **Config Service**: Centralized configuration management using a local Git repository.
- **Discovery Service**: Eureka server for service registration and discovery.
- **Gateway Service**: Spring Cloud Gateway for routing requests.
- **Video Service**: Manages video content (CRUD).
- **User Service**: Manages users, watchlists, history, and statistics.

## Tech Stack
- Java 17, Spring Boot 3.4.3
- Spring Cloud (Eureka, Config, Gateway, OpenFeign)
- Spring Data JPA, MySQL
- Docker & Docker Compose

## Prerequisites
- Maven 3.x
- Docker & Docker Compose

## How to Run
1. Build all services:
   ```bash
   mvn clean package -DskipTests
   ```
2. Start the infrastructure and services:
   ```bash
   docker-compose up --build
   ```

## API Endpoints
### Video Service (via Gateway: 8222)
- `GET /api/videos`: List all videos
- `POST /api/videos`: Create a video
- `GET /api/videos/{id}`: Get video details

### User Service (via Gateway: 8222)
- `POST /api/users`: Create a user
- `POST /api/users/{userId}/watchlist/{videoId}`: Add to watchlist
- `GET /api/users/{userId}/watchlist`: Get watchlist
- `POST /api/users/{userId}/history`: Record watch history
- `GET /api/users/{userId}/statistics`: Get watch stats

## Jira & Documentation
- [Jira Board](https://jira.example.com/projects/VSM)
- Class Diagram: See `diagram.md` in artifacts.
