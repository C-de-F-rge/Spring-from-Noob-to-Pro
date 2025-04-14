# 🧱 @Component – El todo terreno de Spring

## 🟢 ¿Qué es?
`@Component` Es una anotación que le dice a **Spring**:
```txt
"¡Ey! Esta clase es un bean y quiero que la manejes dentro del contenedor."
```
Es el tipo más genérico de los `Spring-Managed-Components` a partir de él, se derivan las anotaciones más específicas como `@Service`, `@Repository` y `@Controller`.

---

## 📦 ¿Para qué sirve?
Sirve para **Registrar una clase en el contexto de Spring** de tal manera que se pueda:

- Se puede **Inyectar** en otras clases.
- Spring **pueda manejar** su ciclo de vida.
- Se aprovecha funcionalidades como [`AOP`(Programación Orientada a Aspectos)](/00_INTRODUCCIÓN/02_Definiciones/04_AOP.md)., configuración automática, etc.

---

## ⚙️ ¿Cómo funciona?
1. Spring escanea las clases del proyecto (con `@ComponentScan` o por defecto).
2. Encuentra una clase con `@Component`.
3. La instancia automáticamente como un **Bean Singleton** (por defecto).
4. La hace disponible para inyección con `@Autowired` y otras formas.

---

## 🧪 Ejemplo práctico

```java
@Component
public class MotorService{
    public void encender(){
        System.out.println("Motor Encendido!");
    }
}
```
```java
@Component
public class Auto{

    private final MotorService motorService;

    @Autowired
    public Auto(MotorService motorService){
        this.motorService = motorService;
    }

    public void arrancar(){
        motorService.encender();
        System.out.println("Auto Arrancado");
    }
}
```
`Spring` detecta ambas clases, las inyecta una dentro de la otra, y no necesitas instanciar nada manualmente.

---

## 🧠 ¿Cuándo usar @Component?
- Cuando necesitas que **Spring controle una clase**.
- para clases que **no encajan claramente** como: servicios(`@Service`), controladores(`@Controller`) o repositorios(`@Repository`).
- Cuando quieres crear una **Lógica compartida** o **Lógica auxiliar** que otros beans usarán.

---

## ❓ ¿Y si no pongo @Component?
Spring no detectará la clase automáticamente.

Tendrías que registrarla manualmente como un @Bean en una clase @Configuration.


