# BookHub - Deployment Guide

## 🚀 Uploading to GitHub

### Step 1: Create a new repository on GitHub
1. Go to [GitHub](https://github.com) and sign in to your account
2. Click the "+" icon in the top right corner and select "New repository"
3. Name the repository: `BookHub`
4. Make it public or private (your choice)
5. **DO NOT** initialize with README, .gitignore, or license (we already have these)
6. Click "Create repository"

### Step 2: Initialize Git and push to GitHub
Open your terminal in the project directory and run these commands:

```bash
# Initialize Git repository
git init

# Add all files to Git
git add .

# Create initial commit
git commit -m "Initial commit: BookHub - Online Bookstore API"

# Add your GitHub repository as remote origin
git remote add origin https://github.com/novitskiiy/BookHub.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Environment Configuration
Create a `.env` file in the root directory with the following content:

```env
# Database Configuration
MYSQLDB_USER=root
MYSQLDB_PASSWORD=MySQLpassword1
MYSQLDB_DATABASE=bookhub
MYSQLDB_LOCAL_PORT=3306
MYSQLDB_DOCKER_PORT=3306

# Spring Application Configuration
SPRING_LOCAL_PORT=8088
SPRING_DOCKER_PORT=8088

# Debug Configuration
DEBUG_PORT=5005
```

**Important**: Make sure to create the `.env` file before running the application with Docker Compose.

### Step 4: Running the Application

#### Using Docker (Recommended):
```bash
# Build the project
mvn clean install

# Run with Docker Compose
docker-compose up
```

#### Using Maven directly:
```bash
# Run the application
mvn spring-boot:run
```

### Step 5: Access the Application
- **API Documentation**: http://localhost:8088/swagger-ui/index.html
- **Health Check**: http://localhost:8088/actuator/health

## 🔐 Default Admin Credentials
- **Email**: admin@example.com
- **Password**: password

## 📝 Notes
- The project has been renamed from "book-store" to "BookHub"
- All author references have been updated to Bogdan Veremienko
- Database name changed from "book_store" to "bookhub"
- JWT secret has been updated for security

## 🛠️ Technologies Used
- Java 17
- Spring Boot 3.3.2
- Spring Security
- Spring Data JPA
- MySQL 8.0
- Docker & Docker Compose
- Liquibase
- MapStruct
- JWT Authentication
- Swagger/OpenAPI

---

**Author**: [Bogdan Veremienko](https://github.com/novitskiiy)
