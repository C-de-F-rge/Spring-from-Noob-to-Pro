# Temario para Aprender Spring

## Conocimientos Previos Necesarios
1. **Java Básico/Intermedio:**
   - Sintaxis: variables, operadores, estructuras de control.
   - POO: clases, herencia, interfaces, polimorfismo.
   - Manejo de excepciones (`try-catch`).
   - Colecciones (`List`, `Map`, `Set`).
   - Lambda expressions y streams (Java 8+).

2. **Herramientas Básicas:**
   - Maven o Gradle (gestión de dependencias).
   - Git (control de versiones).
   - IDE: IntelliJ IDEA, Eclipse o VS Code.

---

## Módulo 1: Fundamentos de Spring
1. **¿Qué es Spring?**
   - Arquitectura modular.
   - Spring vs Spring Boot.
   - Inversión de Control (IoC) y Spring Container.
   - Inyección de Dependencias (DI).

2. **Spring Core:**
   - Configuración con `@Configuration` y `@Bean`.
   - Anotaciones clave: `@Component`, `@Service`, `@Repository`, `@Autowired`.

3. **Spring Boot:**
   - Creación de proyectos con Spring Initializr.
   - Autoconfiguración y `application.properties`.
   - Uso de `SpringApplication`.

---

## Módulo 2: Desarrollo Web con Spring
1. **Spring MVC:**
   - Controladores con `@RestController` y `@Controller`.
   - Mapeo de rutas (`@GetMapping`, `@PostMapping`).
   - Thymeleaf o HTML para vistas (opcional).

2. **APIs REST:**
   - Manejo de JSON (`@RequestBody`, `@ResponseBody`).
   - Validación de datos (`@Valid`).
   - Documentación con Swagger/OpenAPI.

3. **Seguridad:**
   - Spring Security básico (autenticación y autorización).
   - JWT para APIs.

---

## Módulo 3: Persistencia de Datos
1. **Spring Data JPA:**
   - Configuración de bases de datos (H2, MySQL, PostgreSQL).
   - Repositorios (`CrudRepository`, `JpaRepository`).
   - Consultas con `@Query` y métodos derivados.

2. **Transacciones:**
   - `@Transactional` y manejo ACID.

---

## Módulo 4: Temas Avanzados
1. **Microservicios:**
   - Spring Cloud (Eureka, Zuul, Config Server).
   - Comunicación entre servicios (Feign, RestTemplate).
   - Circuit Breaker con Resilience4j o Hystrix.

2. **Reactive:**
   - Spring WebFlux (programación reactiva).
   - Diferencias entre bloqueante y no bloqueante.

3. **Cloud:**
   - Despliegue en AWS/Azure/Google Cloud.
   - Spring Cloud AWS y Kubernetes (conceptos básicos).

4. **Serverless:**
   - Funciones Lambda con AWS y Spring Cloud Function.

5. **Event Driven:**
   - Spring Kafka o RabbitMQ (mensajería asíncrona).
   - Event Sourcing y CQRS (intro).

6. **Batch:**
   - Spring Batch (procesamiento por lotes).
   - Jobs, Steps y `ItemReader`/`ItemWriter`.

---

## Módulo 5: Proyectos Integradores
1. **Aplicación Web Full-Stack:**
   - Backend (Spring Boot) + Frontend (React/Angular).
   - Autenticación JWT + base de datos.

2. **Sistema de Microservicios:**
   - 2-3 servicios comunicándose (ej: pedidos, inventario, usuarios).
   - Uso de Spring Cloud Gateway y Eureka.

3. **Procesamiento de Datos:**
   - Spring Batch para importar/exportar archivos CSV.

---

## Módulo 6: IA Generativa (Opcional)
1. **Integración con Spring:**
   - Uso de APIs de IA (OpenAI, TensorFlow Serving).
   - Ejemplo: Chatbot con Spring Boot y GPT-3/4.
   - Requisitos: Conocimiento de APIs REST y JSON.

---

## Herramientas Adicionales
- **Testing:** JUnit 5, Mockito, Testcontainers.
- **DevOps:** Docker, Jenkins (CI/CD básico).
- **Monitoreo:** Spring Actuator, Prometheus/Grafana.

---
