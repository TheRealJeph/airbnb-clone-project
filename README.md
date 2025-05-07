# AirBnB Clone Project

## 🧠 Overview
This project is a clone of the AirBnB platform. It simulates core features like user registration, property listings, bookings, and reviews.

## 🎯 Project Goals
- Gain hands-on experience in full-stack web development.
- Learn collaboration using Git and GitHub.
- Build and document a real-world application.
- Understand CI/CD and automated testing practices.

## 🛠 Tech Stack
- Python
- Flask
- PostgreSQL
- HTML/CSS
- JavaScript
- Git & GitHub


## 🧑‍💻 Team Roles

In this project, each team member plays a vital role to ensure the successful development of our Airbnb Clone. Below is a breakdown of the key roles and their responsibilities:

### 1. Backend Developer
- **Responsibilities**: Designs and implements the server-side logic of the application. Works with APIs, frameworks, and databases to ensure data is handled correctly and efficiently. Ensures RESTful routes and security practices are followed.

### 2. Database Administrator (DBA)
- **Responsibilities**: Manages the structure and organization of the database. Responsible for schema design, indexing, performance tuning, backups, and ensuring data integrity throughout the application lifecycle.

### 3. DevOps Engineer
- **Responsibilities**: Manages infrastructure, deployment, and CI/CD pipelines. Ensures the application is scalable, reliable, and efficiently deployed across environments using tools like Docker, GitHub Actions, and cloud services.

### 4. Project Manager
- **Responsibilities**: Oversees planning, coordination, and communication within the team. Tracks progress against project timelines and ensures deliverables are completed on time. Facilitates team meetings and resolves blockers.

### 5. Quality Assurance (QA) Engineer
- **Responsibilities**: Ensures the application meets quality standards. Writes and executes test cases, reports bugs, and works closely with developers to fix issues before deployment.

### 6. API Designer
- **Responsibilities**: Plans and structures the RESTful API endpoints. Defines how the frontend and backend systems communicate, including data formats, request/response structure, and error handling strategies.



## 🛠️ Technology Stack

Below is the list of technologies used in this project and their purpose within the Airbnb Clone:

### 1. Django
- **Purpose**: A high-level Python web framework used to build robust and scalable RESTful APIs quickly and securely.

### 2. Django REST Framework (DRF)
- **Purpose**: An extension of Django that simplifies the process of building and managing REST APIs, including serialization and authentication.

### 3. PostgreSQL
- **Purpose**: A powerful, open-source relational database used to store structured data such as users, listings, bookings, and reviews.

### 4. Docker
- **Purpose**: A containerization tool that packages the application and its dependencies into isolated environments, making it easier to develop, deploy, and run consistently across machines.

### 5. GitHub Actions
- **Purpose**: Used to automate workflows like testing, linting, and deployment, ensuring continuous integration and delivery (CI/CD).

### 6. GraphQL *(if applicable in your project)*
- **Purpose**: An API query language that allows clients to request exactly the data they need, reducing over-fetching and under-fetching of data.

### 7. Gunicorn
- **Purpose**: A Python WSGI HTTP server used to serve the Django application in production environments.

### 8. Nginx
- **Purpose**: A high-performance web server used as a reverse proxy to handle incoming HTTP requests and serve static files.

### 9. Swagger / Postman
- **Purpose**: Tools for documenting and testing APIs, allowing developers to understand and interact with endpoints more easily.





## 🗃️ Database Design

This section outlines the key entities in our Airbnb Clone project and their relationships. The database is designed to store and manage users, listings, bookings, payments, and reviews efficiently.

### 1. Users
- **Fields**:
  - `id`: Unique identifier
  - `username`: User’s login name
  - `email`: User’s email address
  - `password`: Hashed password
  - `is_host`: Boolean indicating if the user can post properties
- **Relationships**:
  - A user can have multiple properties (if they are a host)
  - A user can make multiple bookings
  - A user can write multiple reviews

### 2. Properties
- **Fields**:
  - `id`: Unique identifier
  - `title`: Property name/title
  - `description`: Detailed info about the property
  - `location`: Address or city
  - `price_per_night`: Cost of staying per night
- **Relationships**:
  - Each property belongs to a user (host)
  - A property can have many bookings
  - A property can have many reviews

### 3. Bookings
- **Fields**:
  - `id`: Unique identifier
  - `user_id`: User who made the booking
  - `property_id`: Booked property
  - `start_date`: Booking start date
  - `end_date`: Booking end date
- **Relationships**:
  - A booking belongs to one user
  - A booking belongs to one property

### 4. Reviews
- **Fields**:
  - `id`: Unique identifier
  - `user_id`: Author of the review
  - `property_id`: Property being reviewed
  - `rating`: Numeric rating (e.g., 1 to 5)
  - `comment`: Text of the review
- **Relationships**:
  - A review is written by one user
  - A review belongs to one property

### 5. Payments
- **Fields**:
  - `id`: Unique identifier
  - `booking_id`: Related booking
  - `amount`: Total payment amount
  - `payment_method`: Method used (e.g., card, PayPal)
  - `status`: Payment status (e.g., pending, completed)
- **Relationships**:
  - A payment is linked to one booking



