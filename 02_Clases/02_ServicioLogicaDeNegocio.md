# 🛠️ @Service – El cerebro de tu aplicación

## 🟢 ¿Qué es?
`@Service` Es una anotación de Spring que marca la clase como un **Servicio** - es decir, **una capa de lógica de negocio**

Es un tipo de **Bean**, exactamente igual que `@Component`, pero con semántica más clara y soporte adicional para aspectoss como [`AOP`(Programación Orientada a Aspectos)](/00_INTRODUCCIÓN/02_Definiciones/04_AOP.md).

## ⚙️ ¿Cómo funciona?

Spring la trata como un `@Component`, por lo tanto:

1. Detecta la clase con `@Service` durante el escaneo.
2. La Registra como un **bean**.
3. La hace disponible para ser **inyectada** en otras partes del sistema.

Pero también puede aplicar aspectos (por ejemplo, logs automáticos, transacciones, métricas) que Spring reserva para los servicios.

### 🧪 Ejemplo práctico
```java
@Service
public class UsuarioService {
    public String registrarUsuario(String nobre){
        return "Nombre: " + nombre + "Registrado con Exito.";
    }
}
```
y otra clase que lo usa:
```java
@Component
public class RegistroController {
    private final UsuarioService usuarioService;

    @Autowired
    public RegistroController(UsuarioService usuarioService){
        this.usuarioService = usuarioService;
    }

    public void publicar(){
        String mensaje = usuarioService.registrarUsuario("Yoi");
        System.out.println(mensaje);
    }
}
```
📌 `@Service` se usa para separar la lógica de negocio del acceso a datos o de la interfaz (`controlador`)

