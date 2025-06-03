
## Employee Management System (Spring Boot + JWT + Swagger)

This is a beginner-friendly backend project built with Spring Boot. It features CRUD operations for employee records, secured with JWT-based authentication, and includes API documentation via Swagger UI.

---

## 1. Features

- JWT Authentication (Login API with token generation)
- CRUD APIs for Employee entity
- Swagger UI for easy API testing
- Secured endpoints (authentication required for all employee APIs)
- H2 In-memory database for development
- Simple Java code — great for learning Spring Boot

---

## 2. Tech Stack

- Java 17+
- Spring Boot
- Spring Security
- JWT 
- SwaggerUI
- MySQL
- Maven

---

## 3. Prerequisites
-Java 17 installed
-Maven installed
-IDE (e.g., IntelliJ IDEA, Eclipse)
-Postman or browser for testing APIs

---

## 4. How to Run

1. Clone the project:
   git clone https://github.com/yashika777m/employee-management.git
   cd employee-management-backend

2. Make sure Java 17+ and Maven are installed:
   java -version
   mvn -v

3. Run the app:
   mvn spring-boot:run

4. Access:

   - Swagger UI:  
     http://localhost:8080/swagger-ui/index.html

   - H2 Console (optional):  
     http://localhost:8080/h2-console

---

## 5. Default Login Credentials

- Username: admin
- Password: admin123

(You can change these in the SecurityConfig.java or use DB-based users as an enhancement.)

---

## 6. Project Structure

src/main/java/com/example/employeemanagement
├── config
│   └── SwaggerConfig.java
├── controller
│   ├── AuthController.java
│   └── EmployeeController.java
├── exception
│   └── GlobalExceptionHandler.java
├── model
│   ├── Employee.java
│   ├── JwtRequest.java
│   └── JwtResponse.java
├── repository
│   └── EmployeeRepository.java
├── security
│   ├── JwtFilter.java
│   ├── JwtUtil.java
│   └── SecurityConfig.java
└── EmployeeManagementApplication.java

---

## 7. Clean Folder Structure

For better organization and readability, the codebase has been structured into clearly defined packages:

- config – Swagger/OpenAPI configurations
- controller – All REST controllers (e.g., AuthController, EmployeeController)
- exception – Global exception handler using @ControllerAdvice
- model – Entity classes and data transfer objects (DTOs)
- repository – Spring Data JPA interfaces
- security – All security-related components (JWT filter, utilities, config)
- main class – EmployeeManagementApplication.java at the root of the Java package

---

## 8. API Endpoints & Usage

Authentication

- POST /login  
  → Logs in with username and password  
  → Returns a JWT token on success

Example request body:
{
  "username": "admin",
  "password": "admin123"
}

Use the returned token:

- In Swagger UI: Click "Authorize" and paste as:  
  Bearer <your_token>

- In Postman: Add Header:  
  Authorization: Bearer <your_token>

Employee APIs (JWT required)

- GET /employees  
- GET /employees/{id}  
- POST /employees  
- PUT /employees/{id}  
- DELETE /employees/{id}

Example request body for POST and PUT:
{
  "name": "John Doe",
  "email": "john@example.com",
  "department": "Engineering"
}

---

## 9. Optional Enhancements & Customizations

Optional Features:

- Use BCryptPasswordEncoder instead of NoOpPasswordEncoder
- Replace in-memory user with database-based users
- Use MySQL/PostgreSQL instead of H2
- Add role-based authorization
- Add pagination, sorting, and filtering
- Deploy to Render, Railway, or Heroku
- Write unit & integration tests

Contribution Guidelines:

- Fork this repo
- Create a feature branch
- Submit a PR with a meaningful description

---
