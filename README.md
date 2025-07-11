# 🏠 Airbnb Clone Project

## Overview
The **Airbnb Clone Project** is a real-world, full-stack development initiative that simulates the architecture and functionality of the popular Airbnb booking platform. This project emphasizes backend development, database architecture, API design, and application security, all within a collaborative team environment. It's designed to help learners build scalable systems using modern software development practices.

## Project Goals
- Recreate the core functionalities of a booking platform like Airbnb.
- Develop a scalable backend system with secure and well-documented APIs.
- Design a relational database to manage users, properties, bookings, reviews, and more.
- Practice team-based development using GitHub workflows and collaborative planning.
- Integrate Continuous Integration/Continuous Deployment (CI/CD) for seamless delivery.
- Apply advanced security practices to protect user data and system integrity.

## Technology Stack

### 👨‍💻 Backend
- **Django**: Primary backend web framework for building APIs and server-side logic.
- **GraphQL**: For flexible and efficient API queries and mutations.
- **Django REST Framework (DRF)**: For RESTful endpoints.

### 🗄️ Database
- **MySQL**: Relational database system for structured data storage and relationships.

### 🔒 Security
- **JWT (JSON Web Tokens)**: For secure user authentication.
- **Django Middleware & Permissions**: For API access control and data protection.

### ⚙️ DevOps
- **Docker**: Containerization for consistent development and deployment environments.
- **GitHub Actions**: CI/CD pipeline for automated testing and deployment.

### 📦 Version Control
- **Git & GitHub**: Source code management and team collaboration.

## Getting Started
To get started, clone the repository and follow the setup instructions (to be added soon).

```bash
git https://github.com/Onsongo254/airbnb-clone-project.git
cd airbnb-clone
```
## 👥 Team Roles

Effective collaboration is key to delivering scalable, secure, and high-performing software. Below is an overview of the roles involved in this Airbnb Clone Project and their responsibilities.

### 🧠 Project Manager (PM)
The Project Manager oversees the project timeline, goals, and deliverables. They facilitate communication across the team, ensure alignment with requirements, and remove roadblocks to keep the team on track. The PM also coordinates sprints and prioritizes tasks based on stakeholder feedback.

### 👨‍💻 Backend Developer
Responsible for building and maintaining the server-side application logic. This includes designing RESTful and GraphQL APIs, integrating external services, and implementing business logic. Backend developers also ensure that security standards and performance optimizations are upheld.

### 🗄️ Database Administrator (DBA)
Designs and manages the relational database schema. The DBA defines entities, attributes, and relationships while ensuring data consistency, normalization, and performance optimization. They are also responsible for backups, migrations, and securing sensitive information stored in the database.

### 🔐 DevOps Engineer
Handles CI/CD pipeline implementation, infrastructure automation, and containerization. The DevOps Engineer ensures seamless deployments, monitors application health, and automates repetitive tasks to accelerate development workflows. Tools include Docker, GitHub Actions, and monitoring platforms.

### 🔒 Security Specialist
Focuses on application and data security. This role includes implementing authentication/authorization mechanisms (e.g., JWT), enforcing API permissions, managing encryption, and conducting security audits to identify and fix vulnerabilities.

### 📄 Technical Writer / Documentation Lead
Maintains clear, comprehensive documentation for the codebase, APIs, CI/CD pipelines, and setup instructions. The writer ensures that new team members and external contributors can understand and engage with the project with minimal onboarding time.

### 🧪 QA Engineer (Optional Role)
Ensures the quality of the application through test planning, execution, and reporting. This role covers writing unit, integration, and end-to-end tests, using tools to automate regression testing, and working closely with developers to identify bugs early in the lifecycle.

## 🗄️ Database Design

The project uses a relational database (MySQL) to model real-world relationships between users, properties, bookings, reviews, and payments. Below are the key entities and their core fields:

### 🧑 Users
- `id`: Unique identifier  
- `name`: Full name of the user  
- `email`: Unique email address  
- `password`: Hashed password  
- `role`: Host or Guest  

**Relations**:  
- A user can list multiple properties (as a host)  
- A user can make multiple bookings (as a guest)  
- A user can leave multiple reviews  

### 🏠 Properties
- `id`: Unique identifier  
- `title`: Property title  
- `description`: Detailed info  
- `location`: City, state, country  
- `host_id`: References `Users.id`  

**Relations**:  
- A property belongs to one user (host)  
- A property can have many bookings and reviews  

### 📅 Bookings
- `id`: Unique identifier  
- `user_id`: References `Users.id`  
- `property_id`: References `Properties.id`  
- `check_in`: Start date  
- `check_out`: End date  

**Relations**:  
- A booking belongs to one user and one property  
- Each booking can have a corresponding payment  

### ⭐ Reviews
- `id`: Unique identifier  
- `user_id`: References `Users.id`  
- `property_id`: References `Properties.id`  
- `rating`: Numeric score  
- `comment`: User feedback  

**Relations**:  
- A review is made by a user for a specific property  

### 💳 Payments
- `id`: Unique identifier  
- `booking_id`: References `Bookings.id`  
- `amount`: Total payment  
- `status`: Paid, Pending, Failed  
- `payment_date`: Timestamp  

**Relations**:  
- A payment is tied to one booking  
