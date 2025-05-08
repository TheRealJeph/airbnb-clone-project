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





## 🚀 Feature Breakdown

The Airbnb Clone project includes several key features that replicate the core functionalities of the original Airbnb platform. Each feature is essential in providing a seamless user experience and efficient backend operation.

### 1. User Management
Users can register, log in, and manage their profiles. Hosts and guests are both managed through the same system, with role-based access to different features like listing properties or making bookings.

### 2. Property Management
Hosts can create, update, and delete property listings with details such as title, description, location, and pricing. This feature allows properties to be listed and browsed by potential guests.

### 3. Booking System
Guests can book available properties for selected dates. The system handles reservation creation, prevents double-booking, and connects bookings with both users and properties.

### 4. Review System
After completing a stay, guests can leave reviews and ratings for properties. This adds credibility to listings and helps other users make informed booking decisions.

### 5. Payment Processing
Handles secure payment transactions linked to bookings. This includes tracking amounts, statuses, and ensuring each booking is confirmed only after successful payment.

### 6. Authentication & Authorization
The system ensures that only registered users can access certain features. Hosts and guests are granted permissions based on their roles, protecting sensitive data and maintaining user trust.

### 7. API Integration
All functionality is exposed through a RESTful API. This enables frontend applications or third-party services to interact seamlessly with the backend.



## 🔐 API Security

Securing the backend APIs is essential to protect user data, maintain trust, and ensure the overall integrity of the system. This project implements several key security measures to safeguard sensitive operations and data.

### 1. Authentication
We use token-based authentication (such as JWT) to verify the identity of users before allowing access to protected endpoints. This ensures that only verified users can perform actions like booking properties or managing listings.

### 2. Authorization
Role-based access control is enforced to restrict user actions based on their permissions (e.g., only hosts can manage properties, only guests can make bookings). This prevents unauthorized access to critical features and data.

### 3. Rate Limiting
Rate limiting is applied to API requests to prevent abuse, spam, and denial-of-service (DoS) attacks. It helps maintain system performance and ensures fair usage for all users.

### 4. Data Validation and Sanitization
All user input is validated and sanitized to prevent injection attacks and data corruption. This helps protect against common vulnerabilities such as SQL injection or XSS.

### 5. Secure Payment Processing
Sensitive payment information is never stored directly in our database. Instead, we rely on secure third-party payment processors and ensure that all payment data is transmitted over HTTPS.

### 6. HTTPS Enforcement
All API traffic is encrypted using HTTPS to protect data in transit from interception or tampering by malicious actors.

---

Implementing these security measures helps protect user privacy, ensure safe transactions, and maintain the reliability and reputation of the platform.




## ⚙️ CI/CD Pipeline

### What is CI/CD?
CI/CD stands for **Continuous Integration** and **Continuous Deployment/Delivery**. It is a development practice where code changes are automatically tested and deployed to production or staging environments. This process ensures that new features, bug fixes, and updates are delivered quickly and reliably.

### Why It Matters
Implementing CI/CD pipelines improves code quality, reduces manual errors, and speeds up the development lifecycle. It enables teams to catch bugs early, maintain consistent environments, and deploy updates with confidence. This is especially crucial in collaborative projects like our Airbnb Clone, where multiple developers are working on different parts of the application.

### Tools Used
- **GitHub Actions**: Automates workflows such as testing, linting, and deploying code after each commit or pull request.
- **Docker**: Ensures consistent development and production environments through containerization.
- **Docker Compose**: Manages multi-container applications, like running the web server and database together during testing.
- **Heroku / AWS / Render** *(optional)*: Platforms used to deploy and host the backend application.




