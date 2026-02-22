# 🐾 Pet Store REST API

> Production-style REST API built with Spring Boot and MySQL
> demonstrating relational modeling, JPA persistence, and clean RESTful
> design.

------------------------------------------------------------------------

## 👤 Author

Blake Geslicky\
GitHub: https://github.com/geslic

------------------------------------------------------------------------

## 🚀 Tech Stack

-   Java 17
-   Spring Boot 3.x
-   Spring Web
-   Spring Data JPA
-   MySQL
-   Maven
-   Lombok

------------------------------------------------------------------------

## 📌 Project Overview

This backend application manages pet stores, employees, and customers
through a fully RESTful API.

It demonstrates:

-   Clean layered architecture (Controller → Service → Repository →
    Entity)
-   One-to-Many and Many-to-Many JPA relationships
-   Proper HTTP status handling
-   Database persistence with MySQL
-   Maven-based build lifecycle

------------------------------------------------------------------------

## 🏗 Architecture

The application follows a layered backend structure:

-   Controller Layer -- Handles HTTP requests and responses
-   Service Layer -- Business logic and transaction management
-   Repository Layer -- Spring Data JPA interfaces
-   Entity Layer -- JPA-mapped domain models
-   DTO Layer -- Response models to avoid exposing entities directly

This promotes separation of concerns and maintainability.

------------------------------------------------------------------------

## 🗄 Database Setup

1.  Start MySQL:

    sudo systemctl start mysql

2.  Create database and user:

    CREATE DATABASE pet_store; CREATE USER 'pet_store'@'localhost'
    IDENTIFIED BY 'pet_store'; GRANT ALL PRIVILEGES ON pet_store.\* TO
    'pet_store'@'localhost'; FLUSH PRIVILEGES;

3.  Ensure application.yaml contains:

    spring: datasource: url: jdbc:mysql://localhost:3306/pet_store
    username: pet_store password: pet_store jpa: hibernate: ddl-auto:
    update

------------------------------------------------------------------------

## ▶️ Running the Application

### Development Mode

mvn spring-boot:run

### Build and Run JAR

mvn clean package java -jar target/pet-store-0.0.1-SNAPSHOT.jar

Server runs at:

http://localhost:8080

------------------------------------------------------------------------

## 📡 Example API Request

Create Pet Store:

curl -X POST http://localhost:8080/pet_store -H "Content-Type:
application/json" -d '{ "petStoreName":"Blake Pet Store",
"petStoreAddress":"123 Main St", "petStoreCity":"Los Angeles",
"petStoreState":"CA", "petStoreZip":"90001",
"petStorePhone":"555-555-5555" }'

------------------------------------------------------------------------

## 🧩 Entity Relationships

PetStore - One-to-Many → Employee - Many-to-Many → Customer

Employee - Many-to-One → PetStore

Customer - Many-to-Many → PetStore

------------------------------------------------------------------------

## 🧪 Tested Functionality

✔ Create Pet Store\
✔ Retrieve All Pet Stores\
✔ Retrieve Single Pet Store\
✔ Update Pet Store\
✔ Delete Pet Store\
✔ Add Employee\
✔ Add Customer\
✔ Verified persistence in MySQL

------------------------------------------------------------------------

## 🎯 Why This Project Matters

This project demonstrates practical backend development skills
including:

-   RESTful API design
-   Relational database modeling
-   JPA entity mapping
-   Clean architecture principles
-   Build automation with Maven
-   Version control with Git and GitHub

This repository represents backend development work suitable for
internship-level and junior backend roles.
