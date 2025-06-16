# Employee Management System

A full-stack Employee Management System (EMS) that allows users to manage employee data with a modern web UI and a Java Spring Boot backend. The application supports CRUD (Create, Read, Update, Delete) operations for employee records.

## Features

- **Add new employee:** Enter and save employee name and email.
- **View all employees:** See a list of all employees with their details.
- **Edit employee:** Update employee information directly from the dashboard.
- **Delete employee:** Remove employee records with confirmation.
- **Responsive UI:** Modern, responsive, and clean web interface.
- **RESTful API:** Secure and efficient backend API using Spring Boot and JPA.

## Architecture

- **Backend:** Java, Spring Boot, Spring Data JPA, REST, H2/MySQL (configurable)
- **Frontend:** HTML, CSS, JavaScript (Vanilla)
- **Communication:** REST API (JSON)
- **Persistence:** Employee data stored in a relational database

```
[Frontend] <---- REST API (JSON) ----> [Spring Boot Backend] <----> [Database]
```

## Directory Structure

```
Employee-Management-System/
├── backend/
│   └── ems-backend/
│       ├── src/
│       │   ├── main/
│       │   │   └── java/com/example/ems_backend/
│       │   │       ├── controller/      # REST API controllers
│       │   │       ├── dto/             # Data Transfer Objects
│       │   │       ├── entity/          # JPA entities
│       │   │       ├── exception/       # Custom exceptions
│       │   │       ├── mapper/          # Mapping utility
│       │   │       ├── repository/      # Spring Data JPA repositories
│       │   │       └── service/         # Service layer
│       │   └── test/                    # Backend tests
├── frontend/
│   └── index.html                       # Main UI (HTML/JS/CSS)
└── README.md
```

## Backend Details

- **Main Application:** `EmsBackendApplication.java`
- **Entity:** `Employee.java` (fields: id, firstName, lastName, email)
- **Repository:** `EmployeeRepository.java` (extends JpaRepository)
- **Service:** `EmployeeService.java` and `EmployeeServiceImpl.java` (business logic)
- **Controller:** `EmployeeController.java` (API endpoints)
- **Exception Handling:** `ResourceNotFoundException.java`
- **DTO:** `EmployeeDto.java`

### REST Endpoints

- `POST /api/employees` - Add new employee
- `GET /api/employees` - List all employees
- `GET /api/employees/{id}` - Get employee by ID
- `PUT /api/employees/{id}` - Update employee
- `DELETE /api/employees/{id}` - Delete employee

## Frontend Details

- Single-page application in `frontend/index.html`
- Uses vanilla JavaScript for API calls and DOM manipulation
- Features a dashboard, employee list, forms for create/update, and modal dialogs for delete actions

## Running the Project

### Backend

1. Navigate to `backend/ems-backend/`
2. Build and run with Maven/Gradle or your IDE
3. Access API at `http://localhost:8080/api/employees`

### Frontend

1. Open `frontend/index.html` in your browser
2. The UI connects to the backend at `http://localhost:8080/api/employees`

## Customization

- **Database:** By default uses H2; configure `application.properties` for MySQL or other databases as needed.
- **CORS:** Configured for `http://127.0.0.1:5500` in the backend controller, adjust as necessary.

## Code Highlights

- **Clean separation** of concerns (controller, service, repository, entity, DTO)
- **Error handling:** Custom exceptions and HTTP status codes
- **Modern UI:** Responsive design and smooth user experience

