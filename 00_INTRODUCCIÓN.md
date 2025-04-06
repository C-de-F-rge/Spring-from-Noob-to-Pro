# 🧠 Plan de Estudio Completo para Dominar Spring Framework

Este temario está diseñado para que aprendas Spring desde cero hasta un nivel profesional, incluyendo arquitectura limpia, pruebas, microservicios y herramientas avanzadas como Spring Cloud, Event-Driven y programación reactiva.

---

## 🌱 Módulo 1: Fundamentos de Spring

- ¿Qué es Spring y para qué se usa?
- Inversión de Control (IoC) y Principio de Inyección de Dependencias (DI)
- Beans, Containers y Ciclo de vida
- Configuración básica de un proyecto Spring (con Maven o Gradle)
- Tipos de configuración: XML vs Anotaciones vs JavaConfig
- 🔧 **Práctica:** Crear un proyecto simple con servicios y beans inyectados

---

## 🚀 Módulo 2: Spring Boot - Productividad al Máximo

- ¿Qué es Spring Boot y por qué usarlo?
- Estructura de un proyecto Spring Boot
- Configuración con `application.properties` o `application.yml`
- AutoConfiguración y convenciones
- Spring Boot DevTools y Hot Reload
- Pruebas básicas con JUnit y Mockito

---

## 🌐 Módulo 3: Web y APIs REST con Spring MVC

- Arquitectura MVC en Spring
- Controladores REST (`@RestController`)
- Manejo de peticiones HTTP (`@GetMapping`, `@PostMapping`, etc.)
- Envío y recepción de JSON (`@RequestBody`, `@PathVariable`, DTOs)
- Validaciones con `@Valid`, `@NotNull`, etc.
- Manejo de errores globales (`@ControllerAdvice`)
- 🔧 **Práctica:** Crear una API REST completa (CRUD)

---

## 🗃️ Módulo 4: Acceso a Datos con Spring Data JPA

- ¿Qué es JPA? ¿Qué rol cumple en Spring?
- Configuración de base de datos (PostgreSQL, MySQL)
- Entidades y mapeo con `@Entity`, `@Id`, `@ManyToOne`, etc.
- Repositorios con `JpaRepository` y consultas personalizadas
- Relaciones entre entidades (OneToMany, ManyToMany)
- Uso de `CommandLineRunner` para precargar datos

---

## 🔐 Módulo 5: Seguridad con Spring Security

- ¿Qué es Spring Security?
- Autenticación básica (login/contraseña)
- Autorización con roles y permisos
- Configuración con `SecurityFilterChain`
- Seguridad con JWT (JSON Web Tokens)
- CORS y seguridad en APIs REST

---

## 🧼 Módulo 6: Arquitectura Limpia y Buenas Prácticas

- Capas de aplicación: Controller, Service, Repository, DTOs
- Separación de responsabilidades
- Manejo global de excepciones (`@ExceptionHandler`)
- Uso de MapStruct o ModelMapper para transformar entidades
- Documentación de APIs con Swagger/OpenAPI

---

## 🧪 Módulo 7: Testing en Spring

- Pruebas unitarias con JUnit y Mockito
- Pruebas de integración con `@SpringBootTest`
- Pruebas de endpoints con MockMvc
- Pruebas con TestContainers (bases de datos reales para testing)

---

## 🧰 Módulo 8: Herramientas Complementarias

- Spring Boot Actuator (monitoreo y métricas)
- Spring DevTools y LiveReload
- Logs con Logback y niveles de log
- Perfiles de configuración (`application-dev.yml`, `application-prod.yml`)

---

## ☁️ Módulo 9: Microservicios con Spring Cloud

- Introducción a Microservicios
- Comunicación entre servicios (REST, Feign)
- Spring Cloud Config (configuración centralizada)
- Service Discovery con Eureka
- API Gateway con Spring Cloud Gateway
- Circuit Breaker con Resilience4j

---

## ⚡ Módulo 10: Arquitectura Event-Driven (orientada a eventos)

- Introducción a Event-Driven Architecture
- Publicación y consumo de eventos con `ApplicationEventPublisher`
- Uso de colas como Kafka o RabbitMQ
- Spring Cloud Stream

---

## ⚛️ Módulo 11: Programación Reactiva con Spring WebFlux

- ¿Qué es programación reactiva?
- Diferencia entre Spring MVC y Spring WebFlux
- Uso de `Mono` y `Flux`
- Controladores reactivos (`@RestController` con WebFlux)
- Acceso a datos reactivo con R2DBC
- Integración con MongoDB reactivo

---

## 🏁 Módulo 12: Proyecto Final

- ✅ Crear una aplicación profesional con:
  - Registro y login con JWT
  - CRUD completo con Spring Data JPA
  - Seguridad por roles y permisos
  - Arquitectura limpia en capas
  - Documentación con Swagger
  - Base de datos PostgreSQL
  - (Opcional) despliegue con Docker o en la nube (Heroku, Railway)

---

¡Listo! Este plan te llevará desde cero hasta ser un pro con Spring y sus herramientas modernas. 💪

> ¿Quieres que te lo estructure también en semanas o en un tablero de avance (tipo Notion o Trello)? Solo dime y lo armamos 😉
