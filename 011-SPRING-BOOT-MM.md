# 🚀 The Ultimate Spring Boot Handbook

## ⭐ The Core Philosophy
- **"The Factory-Assembled Car"**: Opinionated,Convention over Configuration.
- **Goals**: Auto-configuration, Standalone apps (embedded server), "Just Run".
- **Start Here**: `start.spring.io`

## 1. The Entry Point: `@SpringBootApplication`
- **What**: The main annotation that kicks everything off.
- **File**: `YourApplication.java` with a `main` method.
- **Action**: `SpringApplication.run(YourApplication.class, args);`

## 2. The Engine: Dependency Injection (DI) & Config
- **DI/IoC**: Spring manages object creation (`beans`).
  - `@Component`, `@Service`, `@Repository`: Tells Spring "manage this class."
  - `@Autowired`: Tells Spring "give me an instance of a managed class."
- **Configuration**:
  - **File**: `src/main/resources/application.properties`
  - **Syntax**: `key=value` (e.g., `server.port=9000`).
  - **Usage**: `@Value("${key}")` to inject properties into your code.

## 3. The Web Layer: Building REST APIs
- **`@RestController`**: Marks a class as a request handler (returns JSON).
- **`@RequestMapping("/base-path")`**: Sets the base URL for the controller.
- **Mapping Annotations**:
  - `@GetMapping`: Handles GET requests.
  - `@PostMapping`: Handles POST requests.
  - `@PutMapping`: Handles PUT requests (update).
  - `@DeleteMapping`: Handles DELETE requests.
- **Parameter Annotations**:
  - `@PathVariable`: Grabs a value from the URL path (e.g., `/products/{id}`).
  - `@RequestBody`: Maps the JSON request body to a Java object.

## 4. The Data Layer: Spring Data JPA
- **Goal**: Talk to a database without writing boilerplate SQL.
- **The Layers**:
  - **1. `@Entity`**: A class that maps to a database table. Use `@Id`, `@GeneratedValue`.
  - **2. `JpaRepository<Entity, IdType>`**: An interface that provides free CRUD methods (`findAll()`, `findById()`, `save()`, `delete()`).
  - **3. `@Service`**: The business logic layer that uses the Repository.

## 5. The Full Flow (Putting it all together)
- **Request -> `@RestController` -> `@Service` -> `JpaRepository` -> Database**

## 6. Real-World Essentials
- **Testing**:
  - **`@SpringBootTest`**: Loads the full application context for integration tests.
  - **`MockMvc`**: A tool to simulate HTTP requests and test your controllers.
- **Lombok**: A library to eliminate boilerplate code.
  - **`@Data`**: Generates getters, setters, `toString()`, `equals()`, and `hashCode()`.
  - **`@NoArgsConstructor`, `@AllArgsConstructor`**: Generates constructors.