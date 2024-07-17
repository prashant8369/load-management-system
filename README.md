# Load Management System

This is a Spring Boot application that provides RESTful APIs for managing load entries. It uses PostgreSQL as the database.

## Prerequisites

- Java 17 or later
- Maven 3.6.3 or later
- PostgreSQL 12 or later

## Setup

1. Clone the repository:https://github.com/prashant8369/load-management-system.git
2. Navigate to the project directory:cd load-management-system
3. Configure the database:
- Open `src/main/resources/application.properties`
- Modify the following properties with your PostgreSQL credentials:
  ```
  spring.datasource.url=jdbc:postgresql://localhost:5432/your_database_name
  spring.datasource.username=your_username
  spring.datasource.password=your_password
  ```

4. Build the project:mvn clean install
5. Run the application:mvn spring-boot:run
The application will start running at `http://localhost:8080`.

## API Endpoints

1. Create a new load
- POST `/load`
- Request body:
  ```json
  {
    "loadingPoint": "Delhi",
    "unloadingPoint": "Jaipur",
    "productType": "Chemicals",
    "truckType": "Canter",
    "noOfTrucks": 1,
    "weight": 100,
    "comment": "Handle with care",
    "shipperId": "shipper:<UUID>",
    "date": "dd-mm-yyyy"
  }
  ```

2. Get all loads for a shipper
- GET `/load?shipperId=<UUID>`

3. Get a specific load
- GET `/load/{loadId}`

4. Update a load
- PUT `/load/{loadId}`
- Request body: (same as create load)

5. Delete a load
- DELETE `/load/{loadId}`

## Error Handling

The application includes basic error handling. Detailed error messages are returned for invalid requests or server errors.

## Testing

You can use tools like Postman or curl to test the APIs. Ensure to replace `<UUID>` and `{loadId}` with actual UUIDs in your requests.
