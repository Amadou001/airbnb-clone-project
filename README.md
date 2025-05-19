# About the Project
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

## Tech Stacks

- *Django*
- *Django REST Framework*
- *PostgreSQL*
- *GraphQL*
- *Celery*
- *Redis*
- *Docker*
- *CI/CD Pipelines*

# Team Roles

* **Backend Developer**: Responsible for implementing API endpoints, database schemas, and business logic.
* **Database Administrator**: Manages database design, indexing, and optimizations.
* **DevOps Engineer**: Handles deployment, monitoring, and scaling of the backend services.
* **QA Engineer**: Ensures the backend functionalities are thoroughly tested and meet quality standards.

# Technology Stack

* **Django**: A high-level Python web framework used for building the RESTful API.
* **Django REST Framework**: Provides tools for creating and managing RESTful APIs.
* **PostgreSQL**: A powerful relational database used for data storage.
* **GraphQL**: Allows for flexible and efficient querying of data.
* **Celery**: For handling asynchronous tasks such as sending notifications or processing payments.
* **Redis**: Used for caching and session management.
* **Docker**: Containerization tool for consistent development and deployment environments.
* **CI/CD Pipelines**: Automated pipelines for testing and deploying code changes.

# Database Design

## Entities

### 🧑 Users
**Fields:**
- `id` (Primary Key)
- `name`
- `email`
- `password_hash`
- `created_at`

**Relationships:**
- A user can list multiple properties.
- A user can make multiple bookings.
- A user can write reviews.
- A user can make payments.

---

### 🏠 Properties
**Fields:**
- `id` (Primary Key)
- `title`
- `description`
- `location`
- `owner_id` (Foreign Key referencing Users)

**Relationships:**
- A property belongs to a user (owner).
- A property can have multiple bookings.
- A property can receive multiple reviews.

---

### 📅 Bookings
**Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key referencing Users)
- `property_id` (Foreign Key referencing Properties)
- `start_date`
- `end_date`

**Relationships:**
- A booking is made by a user for a property.
- A booking can have one associated payment.

---

### 💳 Payments
**Fields:**
- `id` (Primary Key)
- `booking_id` (Foreign Key referencing Bookings)
- `amount`
- `payment_date`
- `status`

**Relationships:**
- A payment is linked to a single booking.

---

### ✍️ Reviews
**Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key referencing Users)
- `property_id` (Foreign Key referencing Properties)
- `rating`
- `comment`

**Relationships:**
- A review is written by a user for a property.


# Feature Breakdown

### 📘 1. API Documentation
The backend APIs follow the **OpenAPI standard**, ensuring consistent and developer-friendly documentation.  
With **Django REST Framework**, all essential CRUD operations for users and properties are exposed through RESTful endpoints.  
Additionally, **GraphQL** is implemented to allow flexible and efficient querying of nested and specific data requirements.

---

### 🔐 2. User Authentication
Authentication is handled through endpoints like `/users/` and `/users/{user_id}/`, enabling user registration, login, and profile management.  
This ensures that only authorized users can perform sensitive actions like creating bookings or managing properties.

---

### 🏠 3. Property Management
Property-related operations are managed via endpoints such as `/properties/` and `/properties/{property_id}/`.  
Users can create, update, retrieve, and delete listings, enabling hosts to maintain accurate and up-to-date property details.

---

### 📅 4. Booking System
Bookings are processed through `/bookings/` and `/bookings/{booking_id}/`, allowing users to reserve properties and manage trip details.  
This system supports check-in/check-out information and ensures accurate availability tracking.

---

### 💳 5. Payment Processing
Handled through the `/payments/` endpoint, this feature manages payment transactions tied to bookings.  
It supports secure and reliable processing to ensure a seamless experience for users and hosts.

---

### ⭐ 6. Review System
The review system allows users to leave feedback on properties through `/reviews/` and `/reviews/{review_id}/`.  
Reviews contribute to trust and transparency by allowing users to share their experiences with future guests.

---

### ⚙️ 7. Database Optimizations
To enhance performance, indexing is used to speed up frequent queries, and caching mechanisms reduce database load.  
These optimizations ensure the application scales effectively under high user demand.
