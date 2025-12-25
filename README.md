# Task 1: First Spring Boot Application

## Project Overview

This project is an introductory Spring Boot application designed to demonstrate the basic setup of a web project, the creation of REST controllers, and the rendering of HTML views using the MVC (Model-View-Controller) pattern.

## Technologies Used

* **Java 17+** 
* **Spring Boot** (latest stable version) 
* **Maven** (Project Builder) 
* **Spring Web**: For handling HTTP requests.
* **Lombok**: To reduce boilerplate code.
* **Thymeleaf**: Server-side Java template engine for rendering HTML views.

## Project Structure and Setup

The project was initialized using [Spring Initializr](https://start.spring.io/) with the following metadata:

* **Group**: `pl.edu.vistula`
* **Artifact**: `first-project-java-spring`
* **Name**: `First-Project-Java-Spring`

## Implementation Details

### 1. The Hello Controller

The first controller, `HelloController`, was created in the `pl.edu.vistula.firstprojectjavaspring.controller` package. It initially used the `@RestController` annotation to return simple text directly to the HTTP response.

#### Code: HelloController.java

```java
package pl.edu.vistula.firstprojectjavaspring.controller;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
public class HelloController {

    @GetMapping(value = "/")
    public String hello() {
        return "Hello Vistula, in my first Spring controller.";
    }

    @GetMapping("/greeting")
    public String greeting(@RequestParam(name="name", required=false, defaultValue="World") String name, Model model) {
        model.addAttribute("name", name);
        return "greeting";
    }
}

```



### 2. Rendering an HTML View

To implement the MVC pattern, the controller was updated to use `@Controller`. A `greeting.html` file was created in the resources folder, which displays a personalized message and the Vistula logo (`vistula.png`).

## Screenshots

### Application Startup (Console Output)

Below is the console output showing the Spring Boot application starting successfully on the default port.

![ConsoleOutput](https://github.com/user-attachments/assets/17f63613-76ea-4d84-b4c2-a32855630182)

### First Controller Implementation

A screenshot of the `HelloController.java` class within the IntelliJ IDEA editor.

![RestController](https://github.com/user-attachments/assets/71e11b6e-8d4f-4a48-894a-f40cd9badf82)

### First GET Request

The result of sending a GET request to the root URL (`http://localhost:8080/`).

![Output 1](https://github.com/user-attachments/assets/395079cb-43aa-4a5f-b010-cd38990d158d)

### Rendering the HTML View

The rendered `greeting.html` page, accessed via `http://localhost:8080/greeting?name=Vistula`, showing the dynamic name attribute and the project image.

![Controller](https://github.com/user-attachments/assets/55bc51ed-9b6a-4be6-b84d-cd8090cad387)
![greeting](https://github.com/user-attachments/assets/3ecb2765-b321-4d69-971b-75d62fd1ae03)
![Output 2](https://github.com/user-attachments/assets/f6b98461-4e31-4f84-befe-3003c5056968)

### Full Project Code Structure

A look at the project hierarchy, including the `src/main/java` and `src/main/resources` directories.

---

### How to Run

1. Ensure you have Java 17 or higher installed.


2. Import the project as a Maven project into your IDE.


3. Run the `FirstProjectJavaSpringApplication.java` class.


4. Open your browser and navigate to `http://localhost:8080`.
