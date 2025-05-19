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
