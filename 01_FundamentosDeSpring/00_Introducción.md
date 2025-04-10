# 🌱 ¿Qué es Spring?

`Spring` Es un framework de desarrollo en `Java` que te facilita construir aplicaciones de forma modular organizada y con menos código repetido.

---

# ⚙️ ¿Cómo funciona Spring?

Spring se basa en dos `pilares` clave:

##  1. Inversión de Control (IoC)
En vez de tener que crear las dependencias manualmente (`new Object()`) Spring se encarga de **inyectar** los objetos necesarios donde se requieren.

### 💡 Ejemplo de aplicación
En vez de esto:
```java
Servicio servicio = new Servicio();
```
Usas `Anotaciones` como:
```java
@Autowired
Servicio servicio;
```
💡 Spring detecta que necesitar un objeto `Servicio` y lo crea por ti. Esto se llama [Inyección de Dependencias(DI)](/00_INTRODUCCIÓN/02_Definiciones/01_InyecciónDeDependencias.md)



## 2. Contenedor de Spring (Spring Context)
Spring maneja [Contenedor de Beans](/00_INTRODUCCIÓN/02_Definiciones/02_ContenedorDeBeans.md): Objetos que tú defines y `Spring controla`.

- Cuando la app arranca, Spring escanea tú código y guarda los componentes anotados como `@Component`, `@Service`, `@Repository`, Etc. en un **contenedor**.

- Luego cuando necesitas un objeto Spring te lo da automáticamente ya configurado.

---

# 🛠️ ¿Qué herramientas incluye Spring?

Spring es muy modular. Algunas de sus herramientas más importantes son:

| **Herramienta/Módulo** | **¿Para qué sirve?** |
|----------------|-----------------------------|
| `Spring Core` | Base del framework con `IOC` y `DI`. |
| `Spring Boot` | `Crea` aplicaciones rápido sin `configuración` tediosa. |
| `Spring Data JPA` | `Conecta` con base de datos usando `JPA` (_Hibernate_). |
| `Spring MVC` | `Crea` aplicaciones web o `APIs REST`. |
| `Spring Security` | `Seguridad` y `Autorización` (_Usuarios, Roles, JWT_). |
| `Spring Cloud` | Para `microservicios` distribuidos (_con Config Central, Eureka, Getaway, etc._). |
| `Spring WebFlux` | Para las apps `Reactivas` (_Más Rápidas y Eficientes_). |
| `Spring Batch` | `Procesamiento` por Lotes. |
| `Spring Actuator` | `Monitoreo` y métricas de tu app. |

---

# 🤝 ¿Con qué es compatible Spring?

- **Bases de datos:** PostgreSQL, MySQL, Oracle, MongoDB, H2...
- **Frontend:** React, Angular, Vue, etc. (con APIs REST o GraphQL)
- **Nube:** AWS, GCP, Azure, Heroku, Railway
- Docker y Kubernetes
- **Mensajería:** Kafka, RabbitMQ
- **Autenticación:** JWT, OAuth2, LDAP