# 💡 ApplicationContext - El Contenedor de Spring

El `ApplicationContext` de Apring es el **Contenedor** central en el cual Spring gestiona los objetos (llamados `beans`) y sus dependencias.

## 📦 ¿Qué es un "Contenedor" en Spring?
Un `Contenedor` en **Spring** es una estructura que _crea_, _configura_, _gestiona_ y _destruye_ los objetos de nuestra aplicación (`Beans`), aplicando los principios de Control (IoC) y la Dependency Injection (DI).

---

## 🧩 ¿Qué hace exactamente?
Cuando arrancas una aplicación Spring Boot:
```java
@SpringBootApplication
public class MiApp {
    public static void main(String[] args) {
        SpringApplication.run(MiApp.class, args);
    }
}
```
Internamente, `SpringApplication.run(...)` hace lo siguiente:

1. **Escanea** los paquetes en busca de clases anotadas (`@Component`,`@Service`, etc.).

2. **Crea Instancias** de las clases (Tambien llmamadas `Beans`).

3. **Resuelve Dependencias** entre ellas (`Inyección de Dependencias`).

5. Te las **inyecta donde las necesites**.

---

## 🧪 ¿Cómo puedes acceder al ApplicationContext si lo necesitas?

Puedes inyectarlo en cualquier parte:
```java
@Autowired
private ApplicationContext context;
```

O para ver todos los `beans` registrados:
```java
Arrays.stream(context.getBeanDefinitionNames())
        .foreach(System.out::println);
```
