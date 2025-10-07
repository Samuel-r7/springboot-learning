# springboot-learning - 1

**1. Project overview:**
A very small Spring Boot REST API with one endpoint:
    * GET /hello → returns Hello, World!
    * Tech: Java 17+, Maven, Spring Boot, embedded Tomcat

Recommended IDE: IntelliJ IDEA Community (has excellent Maven + Spring support).


**2. Create the project in IntelliJ:**
File → New → Project
Select Spring Initializr (or if not visible: use Maven).

Fill the form:
    * Group: org.example (your package root)
    * Artifact: helloapi (project name)
    * Type: Maven
    * Java: 17 (or your installed LTS)

Click Next, choose dependency: Spring Web, then Finish.
Choose the repo folder (your cloned feature/hello-api) as the module location so project files are inside your Git repo.
IntelliJ will create pom.xml, src/, and the main class.


**3. Project Structure:**

helloapi/
├─ pom.xml
└─ src/
├─ main/
│  ├─ java/
│  │  └─ org/example/helloapi/
│  │       ├─ HelloApiApplication.java
│  │       └─ HelloController.java
│  └─ resources/
│       └─ application.properties
└─ test/...


**4. pom.xml — what it is:**
pom.xml tells Maven what the project is, which dependencies it needs and how to build it.

Why these parts matter:
    * <parent>: inherits Spring Boot defaults (dependency versions, plugin config).
    * spring-boot-starter-web: provides Spring MVC and Tomcat.
    * spring-boot-maven-plugin: lets you run with mvn spring-boot:run and build an executable jar.


**5. Create packages and Java files:**
   
Create package:
Right-click src/main/java → New → Package → org.example.helloapi
(IntelliJ will create org/example/helloapi folders.)

Create HelloApiApplication.java (main)
src/main/java/org/example/helloapi/HelloApiApplication.java

**What it does:**
* @SpringBootApplication enables auto-configuration + component scanning.
* SpringApplication.run() starts the embedded Tomcat and Spring context.

Create HelloController.java
src/main/java/org/example/helloapi/HelloController.java

**What it does**
* @RestController marks this class as a REST handler.
* @GetMapping("/hello") maps GET requests for /hello to this method.


**6. Run the app:**

from IntelliJ: Open HelloApiApplication.java and click the green ▶ icon next to main().


**Test Endpoint:**
Open Browser: http://localhost:8080/hello

