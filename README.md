# Authentication Project in Java with Spring Boot

This project implements a basic authentication system using Java and Spring Boot. The system allows user registration, login, and access to user information through a RESTful API.

## Technologies Used

- Java 21
- Spring Boot
- IntelliJ IDEA
- Maven
- JPA (Hibernate)
- H2 Database (for development)

## Project Structure

```
/src
   /main
      /java
         /com
            /example
               /authentication
                  - AuthController.java
                  - UserController.java
                  - UserService.java
                  - AuthService.java
                  - User.java
                  - UserRepository.java
                  - JwtUtil.java
      /resources
         - application.properties
```

## API Routes

### 1. User Registration

- **Method:** `POST`
- **Route:** `/auth/register`
- **Description:** Registers a new user in the system.
- **Request Body:**
    ```json
    {
        "username": "string",
        "password": "string"
    }
    ```
- **Success Response (201):**
    ```json
    {
        "message": "User registered successfully."
    }
    ```

### 2. User Login

- **Method:** `POST`
- **Route:** `/auth/login`
- **Description:** Logs in a user and generates a JWT token.
- **Request Body:**
    ```json
    {
        "username": "string",
        "password": "string"
    }
    ```
- **Success Response (200):**
    ```json
    {
        "token": "string"
    }
    ```

### 3. Access User Information

- **Method:** `GET`
- **Route:** `/user`
- **Description:** Returns the information of the authenticated user.
- **Authentication:** This endpoint requires a JWT token in the request header.
- **Request Header:**
    ```
    Authorization: Bearer <token>
    ```
- **Success Response (200):**
    ```json
    {
        "username": "string"
    }
    ```

## Running the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repository.git
   ```

2. Navigate to the project directory:
   ```bash
   cd your-repository
   ```

3. Run the project using IntelliJ IDEA.

## Database Configuration

By default, the project uses the H2 database for development. The configurations can be found in the `application.properties` file.

## Contribution

Contributions are welcome! Feel free to open an `issue` or `pull request`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for more details.
