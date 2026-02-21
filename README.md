# 🐾 Pet Store REST API

## 👤 Author

**Blake Geslicki**\
GitHub: https://github.com/geslic

------------------------------------------------------------------------

## 📌 Overview

This project is a RESTful API built using Spring Boot 3, Spring Data
JPA, and MySQL.\
It manages pet stores, employees, and customers with full CRUD
functionality.

The application demonstrates:

-   REST API design
-   Entity relationships (One-to-Many and Many-to-Many)
-   JPA/Hibernate persistence
-   MySQL database integration
-   Maven project management

------------------------------------------------------------------------

## 🛠 Tech Stack

-   Java 17\
-   Spring Boot 3.x\
-   Spring Web\
-   Spring Data JPA\
-   MySQL\
-   Maven\
-   Lombok

------------------------------------------------------------------------

## 🗄 Database Setup

1.  Start MySQL

    sudo systemctl start mysql

2.  Create Database and User

    CREATE DATABASE pet_store; CREATE USER 'pet_store'@'localhost'
    IDENTIFIED BY 'pet_store'; GRANT ALL PRIVILEGES ON pet_store.\* TO
    'pet_store'@'localhost'; FLUSH PRIVILEGES;

3.  Configure application.yaml

    spring: datasource: url: jdbc:mysql://localhost:3306/pet_store
    username: pet_store password: pet_store jpa: hibernate: ddl-auto:
    update

------------------------------------------------------------------------

## ▶️ Running the Application

Option A --- Development Mode

mvn spring-boot:run

Option B --- Build & Run JAR

mvn clean package java -jar target/pet-store-0.0.1-SNAPSHOT.jar

Server runs at:

http://localhost:8080

------------------------------------------------------------------------

## 📡 API Endpoints

Create Pet Store\
POST /pet_store

Get All Pet Stores\
GET /pet_store/petstores

Get Pet Store by ID\
GET /pet_store/{petStoreId}

Update Pet Store\
PUT /pet_store/{petStoreId}

Delete Pet Store\
DELETE /pet_store/{petStoreId}

Add Employee\
POST /pet_store/{petStoreId}/employee

Add Customer\
POST /pet_store/{petStoreId}/customer

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

## 🚀 Status

Application builds successfully with:

mvn clean package

All endpoints tested using curl.
