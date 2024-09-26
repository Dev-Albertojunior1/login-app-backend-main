# Spring Boot Login & Registration API

Welcome to the **Spring Boot Login & Registration API**! This project provides a secure and robust API for handling user authentication and registration using **Spring Boot**, **Spring Security**, and **JWT**.

---

## Features

- **JWT Authentication** for secure user login and session management.
- **Password Encryption** using `BCrypt`.
- **REST API** endpoints for **Login**, **Registration**, and **Profile**.
- **MySQL / H2 Database** integration with **Spring Data JPA**.
- **Spring Security** configuration for endpoint protection.
- **User roles and access control**.
- **Custom UserDetailsService** for managing user credentials.

---

## Technology Stack

- **Backend**: Spring Boot, Spring Security, Spring Data JPA
- **Authentication**: JWT (JSON Web Tokens)
- **Database**: MySQL / H2
- **Build Tool**: Maven
- **Language**: Java

---

## Getting Started

### Prerequisites
Ensure you have the following installed:

- **Java 17+**
- **Maven**
- **MySQL** (optional if using H2 for local development)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/spring-boot-login-registration-api.git
   cd spring-boot-login-registration-api

2. **Configure your Database**

   - For **MySQL**: update the `application.properties` or `application.yml` with your MySQL connection details.
   - For **H2 Database**: you can skip the MySQL setup for local testing, as H2 is an in-memory database.

3. **Run the Application**
   ```bash
   mvn spring-boot:run
   ```

4. Access the application via `http://localhost:8080`.

---

## API Endpoints

| HTTP Method | Endpoint              | Description                   | Requires Auth? |
|-------------|-----------------------|-------------------------------|----------------|
| `POST`      | `/auth/register`       | Register a new user            | No             |
| `POST`      | `/auth/login`          | Login and get JWT token        | No             |
| `GET`       | `/users/me`            | Get logged-in user's profile   | Yes            |

- **Authorization**: Protected routes require the JWT token in the `Authorization` header as:  
  ```bash
  Authorization: Bearer <JWT_TOKEN>
  ```

---

## Project Structure

```
src
├── main
│   ├── java
│   │   └── com.example.project
│   │       ├── config         # Security and JWT Configurations
│   │       ├── controller     # Controllers for authentication and user management
│   │       ├── dto            # Data Transfer Objects for Login and Registration
│   │       ├── entity         # User Entity
│   │       ├── repository     # JPA Repository for User
│   │       ├── service        # Services for User Management & JWT
│   └── resources
│       ├── application.yml    # Database Configuration
└── pom.xml                    # Project Dependencies and Plugins
```

---

## JWT Token Example

After successful login, you'll receive a JWT token that looks like this:

```
eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJqb2huZG9lQGVtYWlsLmNvbSIsImlhdCI6MTYyNjU5MjA1MywiZXhwIjoxNjI2NTk1NjUzfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

Use this token to authenticate protected routes by adding it to the request headers.

---

## Configuration

You can customize the application settings by modifying the `application.properties` or `application.yml` file.

### Example for MySQL:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/mydb
    username: your-username
    password: your-password
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
  security:
    jwt:
      secret: YourJWTSecretKey
      expirationMs: 86400000
```

---

## Testing the API

Use tools like **Postman** or **Insomnia** to test the API endpoints. Here’s an example request to register a new user:

```json
POST /auth/register
{
  "name": "John Doe",
  "email": "johndoe@example.com",
  "password": "password123"
}
```

---

## Built With

- [Spring Boot](https://spring.io/projects/spring-boot) - Backend Framework
- [JWT](https://jwt.io/) - Token-based Authentication
- [Maven](https://maven.apache.org/) - Build Tool

---

## Contributing

Contributions are always welcome! Feel free to submit a pull request or open an issue to help improve this project. Check out the [contribution guidelines](CONTRIBUTING.md) for more information.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Contact

Feel free to reach out via [Email](mailto:your-email@example.com) or create an issue for any questions, bugs, or feature requests!
```

This version removes all emojis while retaining the professional look and clear structure for your project. Let me know if you need any further modifications!
