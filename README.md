# MakeMyTour

A professional full-stack travel booking platform featuring a Spring Boot backend with MongoDB and an elegant Next.js frontend.



## Overview

MakeMyTour delivers a comprehensive travel booking experience with enterprise-grade architecture and modern development practices:

- **Robust Backend**: Spring Boot microservices with MongoDB persistence
- **Responsive Frontend**: Next.js application with Tailwind CSS styling
- **Secure Authentication**: JWT-based authorization flow
- **Scalable Infrastructure**: MongoDB Atlas integration with replica sets
- **Containerized Deployment**: Docker-ready configuration

## Core Features

### User Experience
- **Streamlined Authentication** - Secure login/signup with JWT
- **Intelligent Search** - Advanced filtering for flights, hotels, and vacation packages
- **Booking Management** - Intuitive interface for creating, viewing, and canceling reservations
- **Payment Integration** - Secure transaction processing *(planned)*
- **User Profiles** - Personalized travel preferences and history

### Administration
- **Comprehensive Dashboard** - Real-time analytics and reporting
- **Inventory Management** - CRUD operations for travel offerings
- **User Management** - Administration tools for account oversight
- **Content Management** - Dynamic content updates for promotions

## Technology Stack

| Component | Technologies |
|-----------|-------------|
| **Backend** | Java 17, Spring Boot 3.4, Spring Security, Spring Data MongoDB |
| **Database** | MongoDB Atlas (replica set configuration) |
| **Frontend** | Next.js 15, React 19, Tailwind CSS, Redux Toolkit |
| **DevOps** | Docker, GitHub Actions |
| **Testing** | JUnit 5, React Testing Library |
| **Documentation** | Swagger/OpenAPI 3.0 |

## Repository Structure

```
/
├── make-my-trip-clone-springboot/   ← Spring Boot backend
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/makemytrip/
│   │   │   │   ├── controller/
│   │   │   │   ├── model/
│   │   │   │   ├── repository/
│   │   │   │   ├── service/
│   │   │   │   ├── config/
│   │   │   │   └── MakemytripApplication.java
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   ├── Dockerfile
│   └── pom.xml
└── makemytour/                      ← Next.js frontend
    ├── src/
    │   ├── pages/
    │   ├── components/
    │   ├── hooks/
    │   ├── services/
    │   └── styles/
    ├── public/
    ├── .env.example
    └── package.json
```

## Prerequisites

- **Java Development Kit** - Version 17 or higher
- **Node.js and npm** - Version 16 or higher 
- **MongoDB** - Local instance or Atlas account
- **Docker** - For containerized deployment (optional)
- **Maven** - Included via wrapper script

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/OmDadhe/Internship_Projects.git
cd Internship_Projects
```

### 2. Backend Setup

```bash
# Navigate to backend directory
cd make-my-trip-clone-springboot/

# Configure MongoDB Connection
# Edit src/main/resources/application.properties with your MongoDB URI:
# spring.data.mongodb.uri=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/makemytour

# Build the application with Maven Wrapper
./mvnw clean package

# Run the Spring Boot application
./mvnw spring-boot:run
```

**Backend API available at:** `http://localhost:8080`

### 3. Frontend Setup

```bash
# Navigate to frontend directory
cd ../makemytour/

# Install dependencies
npm install

# Create environment configuration
cp .env.example .env.local
# Edit .env.local to set NEXT_PUBLIC_API_BASE_URL=http://localhost:8080

# Start development server
npm run dev
```

**Frontend available at:** `http://localhost:3000`

## Docker Deployment

### Backend Containerization

```bash
cd make-my-trip-clone-springboot/
docker build -t makemytour-backend:latest .
docker run -p 8080:8080 -e "SPRING_DATA_MONGODB_URI=mongodb+srv://<user>:<pass>@<cluster>/makemytour" makemytour-backend:latest
```

## API Documentation

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST   | `/api/auth/signup` | Register a new user account |
| POST   | `/api/auth/login` | Authenticate user and retrieve JWT |
| GET    | `/api/flights` | Retrieve available flights |
| GET    | `/api/flights/{id}` | Get details for specific flight |
| GET    | `/api/hotels` | Retrieve available hotels |
| GET    | `/api/hotels/{id}` | Get details for specific hotel |
| POST   | `/api/bookings` | Create a new booking |
| GET    | `/api/bookings/{userId}` | Retrieve user's bookings |
| DELETE | `/api/bookings/{id}` | Cancel a booking |

*Complete API documentation available via Swagger UI at `/swagger-ui.html` when running the backend server.*

## Contributing

We welcome contributions to enhance MakeMyTour:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'feat: Add amazing feature'`
4. Push to your branch: `git push origin feature/amazing-feature`
5. Open a pull request

Please adhere to our coding standards and include appropriate tests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

© 2025 MakeMyTour. All rights reserved.
