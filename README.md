**User Registration and Details Fetch API**
=============================================

This is a Spring Boot-based RESTful API that provides two endpoints for user registration and user details fetch.

**API Endpoints**
---------------

### 1. Register a new user

* **Endpoint:** `/api/user/register`
* **Method:** `POST`
* **Request Body:** JSON object containing user details (username, email, password)
* **Response:**
	+ Success: `201 Created` with a message indicating successful registration
	+ Failure: `400 Bad Request` with an error message indicating the reason for failure

### 2. Fetch user details

* **Endpoint:** `/api/user/fetch`
* **Method:** `GET`
* **Query Parameter:** `username`
* **Response:**
	+ Success: `200 OK` with a JSON object containing user details
	+ Failure: `404 Not Found` with an error message indicating that the user was not found

**Implementation Details**
-------------------------

* The API uses in-memory storage to store user information for simplicity.
* User passwords are stored securely using a hashing algorithm.
* Exception handling is implemented to handle potential errors and exceptions.
* Unit tests are written to ensure the correct behavior of the registration endpoint.

**TODO**
-----

* Implement database storage instead of in-memory storage
* Enhance security measures to protect sensitive user data
* Document the API using Swagger or an alternate documentation tool

**Running the Application**
-------------------------

* Clone the repository and navigate to the project directory
* Run the application using `mvn spring-boot:run` (if using Maven) or `gradle bootRun` (if using Gradle)
* Use a tool like Postman or cURL to test the API endpoints

**Testing the API**
-----------------

### Register a new user

```bash
curl -X POST -H "Content-Type: application/json" -d '{"username": "testuser", "email": "testuser@example.com", "password": "testpassword"}' http://localhost:8080/api/user/register
```

### Fetch user details

```bash
curl -X GET "http://localhost:8080/api/user/fetch?username=testuser"
```

**License**
-------

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

**Contributing**
------------

Contributions are welcome! If you'd like to contribute to this project, please fork the repository and submit a pull request.
