# Hospital Management System

A Spring Boot-based REST API system for managing hospital operations including patients, doctors, appointments, departments, and staff.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [API Documentation](#api-documentation)
- [Security](#security)
- [Testing](#testing)

## Features

- Patient Management
- Doctor Management
- Appointment Scheduling with conflict prevention
- Department Organization
- Staff Management
- Role-based access control (Admin/User)
- Automated appointment validation
- Comprehensive error handling

## Tech Stack

- **Framework**: Spring Boot 3.2.3
- **Language**: Java 17
- **Database**: H2 (In-memory)
- **Security**: Spring Security
- **Build Tool**: Maven
- **Documentation**: Spring REST Docs

## Getting Started

### Prerequisites

- Java JDK 17 or higher
- Maven 3.6 or higher
- Any IDE (IntelliJ IDEA/Eclipse/VS Code)

### Installation Steps

1. Clone the repository

```bash
git clone https://github.com/GriffinBlackbirdd/hospital-management-system.git
```

2. Navigate to project directory

```bash
cd hospital-management
```

3. Build the project

```bash
mvn clean install
```

4. Run the application

```bash
mvn spring-boot:run
```

The application will start at `http://localhost:8080`

### Database Configuration

H2 Console available at `http://localhost:8080/h2-console`

```
URL: jdbc:h2:mem:hospitaldb
Username: sa
Password: [empty]
```

## API Documentation

### Authentication

```
Admin Credentials:
Username: admin
Password: admin123

User Credentials:
Username: user
Password: user123
```

### API Endpoints

#### Patient Management

```http
GET    /api/patients        - Get all patients
POST   /api/patients        - Create new patient
GET    /api/patients/{id}   - Get patient by ID
PUT    /api/patients/{id}   - Update patient
DELETE /api/patients/{id}   - Delete patient
```

#### Doctor Management

```http
GET    /api/doctors         - Get all doctors
POST   /api/doctors        - Create new doctor
GET    /api/doctors/{id}   - Get doctor by ID
PUT    /api/doctors/{id}   - Update doctor
DELETE /api/doctors/{id}   - Delete doctor
```

#### Appointment Management

```http
POST   /api/appointments                    - Schedule appointment
GET    /api/appointments/doctor/{id}       - Get doctor's appointments
GET    /api/appointments/patient/{id}      - Get patient's appointments
PUT    /api/appointments/{id}              - Update appointment
DELETE /api/appointments/{id}              - Cancel appointment
```

#### Department Management

```http
GET    /api/departments        - Get all departments
POST   /api/departments        - Create department
GET    /api/departments/{id}   - Get department by ID
PUT    /api/departments/{id}   - Update department
DELETE /api/departments/{id}   - Delete department
```

#### Staff Management

```http
GET    /api/staff                    - Get all staff
POST   /api/staff                    - Add staff member
GET    /api/staff/department/{id}    - Get staff by department
PUT    /api/staff/{id}              - Update staff details
DELETE /api/staff/{id}              - Delete staff member
```

## Security

### Role-Based Access

- **Admin Role**: Full access to all endpoints
- **User Role**: Limited to:
  - Viewing doctors/departments
  - Managing appointments
  - Viewing patient information

### Authentication

Basic Authentication is implemented for all endpoints except:

- `/h2-console/**`
- `/api/auth/**`

## Testing

### Running Tests

```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=AppointmentServiceImplTest
```

### Postman Collection

Import the provided Postman collection for testing all endpoints:
[Download Postman Collection](#)

## Features Highlight

### Appointment Conflict Management

- Automatic 30-minute slot allocation
- Conflict detection and prevention
- Working hours validation (9 AM - 5 PM)
- Weekend booking prevention

### Error Handling

- Comprehensive error messages
- Proper HTTP status codes
- Validation error details

## Response Format

```json
// Success Response
{
    "success": true,
    "message": "Operation successful",
    "data": {
        // Response data
    }
}

// Error Response
{
    "success": false,
    "message": "Error message",
    "status": 400
}
```

## Contributors

- [Your Name]
- [Team Members]

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

Would you like me to:

1. Add more sections to the README?
2. Include additional setup instructions?
3. Add troubleshooting guides?
4. Include contribution guidelines?

Let me know what specific aspects you'd like me to expand!
