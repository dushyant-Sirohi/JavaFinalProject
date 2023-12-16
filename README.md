# Final Project

This is a Java project developed using the Spring Boot framework for managing students. The project includes functionality for displaying a list of students, adding new students, viewing student details, and deleting students.

## Project Structure

- **FinalprojectApplication.java**
  - Main class for running the Spring Boot application.
  - Contains the `main` method to start the application.
  - Includes a `CounterService` bean.

- **ServletInitializer.java**
  - Extends `SpringBootServletInitializer` to support deployment as a WAR file.
  - Configures the application's entry point.

- **PageHitsController.java**
  - REST controller for handling requests related to page hits.
  - Uses the `CounterService` to retrieve page hit counts.

- **StudentController.java**
  - Controller for managing student-related operations.
  - Handles requests for listing students, viewing details, adding new students, and deleting students.
  - Utilizes `StudentService` and `CounterService` for data manipulation and tracking page hits.

- **Student.java**
  - Model class representing a student.
  - Annotated with Spring Data MongoDB annotations for persistence.

- **StudentRepository.java**
  - Interface extending `MongoRepository` for CRUD operations on `Student` entities.
  - Contains custom query methods for case-insensitive searches.

- **CounterService.java**
  - Service class managing page hit counts.
  - Utilizes `AtomicInteger` for thread-safe incrementing.

- **StudentService.java**
  - Service class providing business logic for student-related operations.
  - Interacts with the `StudentRepository` for database operations.

## Usage

1. **Build with Maven:**
   ```bash
   mvn clean install
2. **Run the Application:**
   ```bash
   java -jar target/finalproject-0.0.1-SNAPSHOT.war

Access the application at http://localhost:8080.

## Endpoints

- **/page-hits:** Retrieves the current page hit count.
- **/students-list:** Lists all students or performs a search based on the query parameter.
- **/new:** Displays a form to add a new student.
- **/{id}:** Retrieves details of the student with the specified ID.
- **/delete/{id}:** Deletes the student with the specified ID.

## Notes

- Page hits are tracked and displayed using the `CounterService`.
- Student data is stored in MongoDB using the `StudentRepository`.
- The `StudentController` handles user interactions and invokes corresponding services.

## Dependencies

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring Data MongoDB](https://spring.io/projects/spring-data-mongodb)
- [Lombok](https://projectlombok.org/)



