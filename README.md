# Task 1 – Spring Boot MVC Application

## Project Description

This project is a simple **Spring Boot MVC application** created as part of **Task 1**.
The goal of the application is to demonstrate:

* creation of a Spring Boot project from scratch,
* usage of a Spring Controller,
* handling HTTP GET requests,
* returning plain text using `@ResponseBody`,
* returning an HTML view using the MVC pattern with **Thymeleaf**.

The application runs on an embedded Tomcat server and is accessible via a web browser.

---

## Technologies Used

* Java
* Spring Boot
* Spring Web
* Thymeleaf
* Maven

---

## Project Structure

```
src
 └── main
     ├── java
     │   └── com.example.demo
     │       └── controller
     │           └── GreetingController.java
     └── resources
         ├── templates
         │   └── greeting.html
         └── static
             └── vistula.png
```

---

## Application Endpoints

### 1. Root Endpoint – Plain Text Response

**URL**

```
GET http://localhost:8080/
```

**Description**

This endpoint returns a simple text response directly to the browser.

**Implementation details**

* Uses `@GetMapping("/")`
* Uses `@ResponseBody`
* Returns a `String` instead of a view

**Expected Output**

```
Hello Spring Boot
```

---

### 2. Greeting Endpoint – HTML View (MVC)

**URL**

```
GET http://localhost:8080/greeting
```

**Description**

This endpoint demonstrates the **MVC pattern**.
The controller passes data to an HTML view rendered using **Thymeleaf**.

**Implementation details**

* Uses `@Controller`
* Uses `Model` to pass data
* Returns the name of the HTML template (`greeting.html`)
* Thymeleaf displays dynamic content using `${}` syntax

**Expected Output**

* A webpage displaying a greeting message
* An image loaded from the static resources folder

---

## Explanation of Key Annotations

* `@Controller`
  Marks the class as a Spring MVC controller.

* `@GetMapping`
  Maps HTTP GET requests to a controller method.

* `@ResponseBody`
  Indicates that the return value should be written directly to the HTTP response body instead of rendering a view.

* `Model`
  Used to pass data from the controller to the view layer.

---

## How to Run the Application

1. Open the project in IntelliJ IDEA
2. Make sure Maven dependencies are downloaded (`Reload Project`)
3. Run the main Spring Boot application class
4. Open a browser and visit:

   * `http://localhost:8080/`
   * `http://localhost:8080/greeting`

---

## Notes for Assessment

During the presentation, the application can be demonstrated by:

1. Showing the controller code
2. Explaining the difference between returning text and returning a view
3. Running the application locally
4. Accessing endpoints via a browser
5. Explaining how Thymeleaf integrates with Spring MVC

---

## Author

Adam Mikael Bin Aris Abdillah
