# Bookstore Management System 📚

An academic project built to manage book inventory and personalized user collections. This application demonstrates a full-stack Java implementation focusing on relational data management and dynamic server-side rendering.

---

## 🛠 Tech Stack
- **Backend:** Java & Spring Boot
- **Frontend:** Thymeleaf, HTML5, CSS3, Bootstrap
- **Database:** MySQL
- **Build Tool:** Maven

## ✨ Key Features
- **Book Inventory:** View a complete list of **Available Books** in the store.
- **New Book Registration:** A dedicated form to add new books to the system.
- **Personal Collection (My Books):** Allows users to select and manage their own list of books from the store.
- **CRUD Functionality:** Full capability to register, view, and delete book entries.

## 📸 Screenshots
Home Page
<img width="1366" height="646" alt="Book Store Home page" src="https://github.com/user-attachments/assets/3dbe8e6a-940c-4ae6-80e9-345dfb04b6e0" />

Available Books
<img width="1366" height="645" alt="Book Store availabe books" src="https://github.com/user-attachments/assets/076f13b4-870b-42c5-8a4f-4b84c1399554" />

My Books
<img width="1366" height="644" alt="Book Store my books" src="https://github.com/user-attachments/assets/f2c93883-c3b6-4034-a1e8-c8671431c4da" />

New Book Registration
<img width="1366" height="643" alt="Book Store new book register" src="https://github.com/user-attachments/assets/155eb9f9-cd3c-4922-968e-ae9a03a4bc0d" />



## ⚙️ How to Run

### Method A: 🐳 The Dockerized Setup (Recommended & Quickest)
This project is fully containerized and orchestrated using **Docker** and **Docker Compose**. It completely isolates the application execution environment and packages a dedicated, self-contained MySQL database service to guarantee deployment with zero manual configurations.

####  Architecture Breakdown
* **Application Container (`bookstore-backend`):** Implements a multi-stage Docker build pipeline. Stage 1 utilizes a Maven container wrapper to compile optimized binary `.jar` targets directly from source code. Stage 2 executes this payload inside a secure, lightweight **Eclipse Temurin OpenJDK 17** virtual container layer on port `1001`.
* **Database Container (`bookstore-db`):** Launches an explicit MySQL 8.0 server instance operating internally on a virtual bridge network while exposing network connectivity externally via mapped port `3307` to eliminate any possible native machine database environment conflicts.

#### 🚀 Execution Steps
1. Navigate to the root directory containing your `docker-compose.yml` file and trigger the build process:
   ```bash
   docker compose up --build
   ```
   *Note: For subsequent runs, you can drop the `--build` flag to launch the entire system instantly in under 3 seconds:*
   ```bash
   docker compose up
   ```
2. **Access the Application:** Open your web browser and go to:
   ```text
   http://localhost:1001
   ```

---

### Method B: Manual Local Setup (Traditional Approach)

1. **Database:** Create a local MySQL database named `book`.
2. **Configuration:** Update `src/main/resources/application.properties` with your MySQL `username` and `password`.
3. **Execution:** Ensure you have Maven and JDK 17 installed locally, then compile and run the application:
   ```bash
   mvn clean package
   mvn spring-boot:run
   ```
4. **Access the Application:** Open your browser and go to:
   ```text
   http://localhost:1001
   ```

