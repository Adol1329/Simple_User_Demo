# User API with Spring Boot

A simple RESTful API built with Spring Boot for managing user data with in-memory storage.

## 📋 Overview

This repository contains a lightweight User Management API that demonstrates basic CRUD operations using Spring Boot. The API uses HashMap-based in-memory storage instead of a persistent database, making it perfect for development, testing, and learning purposes.

**📦 Project Files:** The main Spring Boot project is packaged in `demo.zip`

## 👨‍💻 Author

**Adolphe Uwayo**  
📧 adolpheuwayo12@gmail.com

## 🛠️ Technology Stack

- **Language:** Java 11
- **Framework:** Spring Boot 2.7.5
- **Build Tool:** Maven
- **Storage:** In-memory HashMap

## 📋 Prerequisites

Before running this application, ensure you have:

- Java Development Kit (JDK) 11 or higher
- Maven 3.6+ (for building the project)
- Terminal or command-line interface

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone <repository-url>
```

### 2. Navigate to Project Directory
```bash
cd <repository-directory>
```

### 3. Build the Project
```bash
mvn clean install
```

### 4. Run the Application
```bash
mvn spring-boot:run
```

The API will be available at: `http://localhost:8081`

## 📚 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/users` | Create a new user |
| GET | `/users/{id}` | Retrieve a user by ID |

## 🔧 Usage Examples

### Create a User
```bash
curl -X POST http://localhost:8081/users \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe", 
    "email": "john@example.com"
  }'
```

**Expected Response (201 Created):**
```json
{
  "id": "0f4dc56e-5e11-4984-aea6-bb8412997741",
  "name": "John Doe",
  "email": "john@example.com"
}
```

### Retrieve a User
```bash
curl -X GET http://localhost:8081/users/0f4dc56e-5e11-4984-aea6-bb8412997741
```

**Expected Response (200 OK):**
```json
{
  "id": "0f4dc56e-5e11-4984-aea6-bb8412997741",
  "name": "John Doe",
  "email": "john@example.com"
}
```

**User Not Found (404 Not Found):**
```json
{
  "error": "User not found"
}
```

## ⚠️ Important Notes

- **In-Memory Storage:** Data is stored in a HashMap within the UserService and will be lost when the application restarts
- **No Persistence:** No database or repository layer is implemented by design
- **Port Configuration:** Ensure your `application.properties` contains `server.port=8081`
- **Input Validation:** Invalid requests (missing required fields) will return `400 Bad Request` with error details

## 🧪 Tested Scenarios

### ✅ Successful Operations

**POST /users**
- Status: `201 Created`
- Response includes generated UUID and user data

**GET /users/{valid-id}**
- Status: `200 OK`
- Returns complete user information

**GET /users/{invalid-id}**
- Status: `404 Not Found`
- Returns appropriate error message

## 🤝 Contributing

Feel free to fork this repository and submit pull requests for any improvements.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Note:** This API is designed for educational and development purposes. For production use, consider implementing proper data persistence, security measures, and comprehensive error handling.
