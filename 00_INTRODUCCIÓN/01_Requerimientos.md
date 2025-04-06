# Requerimientos: Temas y Herramientas

## 1. Temas que se trabajan directamente en Spring Boot
- **Fundamentos de Spring**  
  - IoC (Inversión de Control).  
  - DI (Inyección de Dependencias).  
  - Anotaciones básicas (`@Component`, `@Autowired`, etc.).  

- **Desarrollo Web**  
  - Spring MVC.  
  - APIs REST.  
  - Spring Security (autenticación/autorización).  

- **Persistencia de Datos**  
  - Spring Data JPA.  
  - Transacciones (`@Transactional`).  

- **Batch**  
  - Spring Batch (procesamiento por lotes).  

- **Reactive**  
  - Spring WebFlux (programación reactiva).  

- **Proyectos Integradores**  
  - Backend + Frontend (ej: Spring Boot + React/Angular).  

### Herramientas:  
- **Spring Initializr**: Para generar la plantilla base del proyecto.  
- Configuración en:  
  - `pom.xml` o `build.gradle` (dependencias).  
  - `application.properties` (parámetros de la app).  

---

## 2. Temas que requieren integración externa
- **Microservicios (Spring Cloud)**  
  - Servicios adicionales:  
    - Eureka (registro de servicios).  
    - Zuul (API Gateway).  
    - Config Server (gestión centralizada de configuraciones).  
  - Implementación: Proyectos Spring Boot separados.  

- **Cloud (AWS/Azure/Google Cloud)**  
  - Despliegue en plataformas externas.  
  - Integración con Spring Cloud AWS.  

- **Serverless (AWS Lambda)**  
  - Spring Cloud Function.  
  - Entorno gestionado por AWS/Azure.  

- **Event Driven (Kafka/RabbitMQ)**  
  - Configuración de brokers externos (Kafka/RabbitMQ).  
  - Librerías de Spring Boot para conexión.  

- **IA Generativa (OpenAI)**  
  - Consumo de APIs externas (ej: OpenAI).  
  - Integración desde Spring Boot.  