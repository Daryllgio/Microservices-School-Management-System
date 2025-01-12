Microservices-Based School Management System

This project is a Microservices-Based School Management System designed to manage schools and their associated students. 
It is built using a modern microservices architecture and employs tools like Spring Boot, Docker, Eureka, and Feign for scalability, reliability, and ease of maintenance.

I) Features

 - School Management:
    - Create, retrieve, and manage school details (e.g., name, email).
    - Fetch details of schools along with their associated students.

 - Student Management:
    - Create, retrieve, and manage student details (e.g., name, email, associated school).
    - Filter students by their associated school.

 - Inter-Service Communication:
   - Uses OpenFeign to enable seamless communication between services.

 - Centralized Configuration:
   - Spring Cloud Config Server manages configuration for all services.

 - Service Discovery:
   - Eureka ensures dynamic service registration and discovery.

 - Distributed Tracing:
   - Zipkin is integrated for tracing requests across multiple services.

 - Dockerized Deployment:
   - All services are containerized and orchestrated using docker-compose.

II) Architecture

The project consists of the following services:

1. School Service
   - Manages school-related data.
   - Exposes REST APIs for CRUD operations on schools.
   - Communicates with the Student Service to fetch students associated with a specific school.

2. Student Service
   - Manages student-related data.
   - Exposes REST APIs for CRUD operations on students.
   - Supports filtering students by their school ID.

3. Gateway Service
 - Serves as a single entry point for all client requests.
 - Routes requests to the appropriate services.

4. Discovery Service
   - Eureka Server for service registration and discovery.
   - Ensures dynamic and fault-tolerant service interaction.

5. Config Server
   - Provides centralized configuration management for all services.
   - Simplifies updates and ensures consistency across the system.

6. Zipkin
   - Integrated for distributed tracing and debugging.
   - Tracks the flow of requests across services.

III) Technology Stack

  - Languages: Java

  - Frameworks: Spring Boot, Spring Cloud (Eureka, OpenFeign, Config Server)

  - Databases: PostgreSQL

  - Containerization: Docker

  - Tracing: Zipkin

IV) Access the services:

 - School Service: http://localhost:8080

 - Student Service: http://localhost:8081

 - Eureka Server: http://localhost:8761

 - Zipkin: http://localhost:9411

 - Config Server: http://localhost:8888

v) API Endpoints

1) School Service

 - Create a School:

    POST /api/v1/schools

 - Request Body:

    {
      "name": "Greenwood High",
      "email": "contact@greenwood.com"
    }

 - Retrieve All Schools:

    GET /api/v1/schools

 - Retrieve a School with Students:

  GET /api/v1/schools/with-students/{school-id}

2) Student Service

 - Create a Student:

    POST /api/v1/students

 - Request Body:

    {
      "firstname": "Alice",
      "lastname": "Smith",
      "email": "alice.smith@example.com",
      "schoolId": 1
    }

- Retrieve All Students:

    GET /api/v1/students

- Retrieve Students by School:

  GET /api/v1/students/school/{school-id}




