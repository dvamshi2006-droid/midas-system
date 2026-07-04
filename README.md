# midas-system

MIDAS System

A modular Spring Boot backend project demonstrating real-world integration of Apache Kafka, the H2 Database, and REST APIs — built as part of a Software Engineering Job Simulation (Forage) virtual internship.

Author: D. Vamshi Krishna (24EG105E07)
Project Guide: Mr. BV Srikanth, Dept. of CSE
Department: Computer Science and Engineering


📖 Introduction

The MIDAS System was built to bridge the gap between academic learning and real-world backend software development. It simulates practical, industry-style engineering tasks including:
Project setup and structuring
Apache Kafka integration (asynchronous messaging)
H2 in-memory database integration
REST API integration with an external Incentive API
REST API Controller development
Each task mirrors a real workplace scenario, reinforcing how different components of a software application interact — strengthening skills in software architecture, database management, event-driven communication, API development, and debugging.


🎯 Problem Statement

Modern applications require integrating multiple technologies (databases, APIs, event-driven systems), which is hard to learn without hands-on experience. Many students have limited exposure to real-world engineering practices before entering the workforce. MIDAS closes this gap by providing a realistic backend development environment covering setup, Kafka, H2, REST API integration, and controllers.



📂 Project Structure

midas-system/
├── src/
│   ├── main/
│   │   ├── java/com/example/midas/
│   │   │   ├── controller/      # REST API Controllers (GET, POST, PUT, DELETE)
│   │   │   ├── service/         # Business logic + Incentive API integration
│   │   │   ├── repository/      # Spring Data JPA repositories (H2)
│   │   │   ├── entity/          # JPA entity classes
│   │   │   ├── kafka/           # @KafkaListener consumer classes
│   │   │   └── MidasApplication.java
│   │   └── resources/
│   │       ├── application.properties   # H2 + Kafka config
│   │       └── static/
│   └── test/                    # Unit & integration tests
├── pom.xml                      # Maven dependencies
└── README.md



🔑 Key Points
Task 1 — Project Setup: Spring Boot project structured with Maven; organized into Controllers, Services, Repositories, and Entities; version-controlled with Git/GitHub.
Task 2 — Kafka Listener: @KafkaListener-annotated consumer asynchronously processes messages from a configured Kafka topic.
Task 3 — H2 Database: JPA entities + JpaRepository interfaces enable CRUD operations, verified via the H2 web console.
Task 4 — Incentive API Integration: Dedicated service class communicates with an external Incentive API, handling JSON parsing and exceptions.
Task 5 — REST Controllers: @RestController classes expose GET/POST/PUT/DELETE endpoints, tested end-to-end with Postman.

System flow: Client (web/mobile/Postman) → REST Controller → Service Layer (business logic) → Spring Data JPA → H2 Database, with Kafka producers/consumers handling async messaging independently.


🛠️ Tech Stack

Language: Java 17+
Framework: Spring Boot, Spring Data JPA
Messaging: Apache Kafka
Database: H2 (in-memory)
Build Tool: Apache Maven
Testing: Postman
IDE: IntelliJ IDEA / Eclipse / VS Code



⚖️ Advantages & Limitations
Advantages: Modular architecture, asynchronous Kafka messaging, fast H2-based testing, and standardized REST APIs improve maintainability and scalability.

Limitations: H2 is in-memory and non-persistent; security (auth/authorization) is minimal; only basic Kafka producer/consumer functionality is implemented; not yet tested at production scale.


🔮 Future Enhancements
Replace H2 with a production database (MySQL/PostgreSQL)
Add Spring Security with JWT authentication
Deploy to the cloud (AWS/Azure/GCP) using Docker and Kubernetes
Build a frontend with Angular/React
Add CI/CD pipeline and monitoring



✅ Results
All five tasks — project setup, Kafka listener, H2 database, Incentive API integration, and REST controllers — were implemented and verified successfully using Postman.



🚀 Deployment
Follow these steps in order to set up and run the project locally, then push it to your GitHub repo:
1. Clone the repository:
git clone https://github.com/<your-github-username>/midas-system.git
cd midas-system

2. Prerequisites
JDK 17 or higher installed
Apache Maven installed
Apache Kafka running locally (or via Docker)

3. Configure application properties
Edit src/main/resources/application.properties:
# H2 Database
spring.datasource.url=jdbc:h2:mem:midasdb
spring.h2.console.enabled=true
spring.jpa.hibernate.ddl-auto=update

# Kafka
spring.kafka.bootstrap-servers=localhost:9092
spring.kafka.consumer.group-id=midas-group


Build the project:
mvn clean install

Run the application:
mvn spring-boot:run


The app starts on http://localhost:8080 by default.


git init
git add .
git commit -m "Initial commit: MIDAS System"
git branch -M main
git remote add origin https://github.com/<your-github-username>/midas-system.git
git push -u origin main


📌 Conclusion
The MIDAS System successfully demonstrates modern backend development using Spring Boot, Apache Kafka, H2 Database, and REST APIs — strengthening practical skills in Java development, API integration, and software engineering best practices.
