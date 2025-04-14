# 🧠 ¿Qué es AOP (Aspect Oriented Programming)?

`AOP` es un paradigma de programación que permite separa código transversal o repetitivo de la lógica principal de la aplicación.

```txt
En lugar de repetir el mismo código en muchos métodos (por ejemplo, logs, seguridad, transacciones), AOP te permite escribirlo una vez y que se ejecute automáticamente donde lo necesites.
```

## 🎯 ¿Para qué sirve?

| **Funcionalidad Transversal** | **Ejemplo en AOP** |
|-------------|---------------------------|
| **🔐 Seguridad** | Comprobar Roles/Permisos antes de ejecutar un método. |
| **🧾 Logging** | Registrar entradas/salidas de métodos. |
| **🔁 Transacciones** | Abrir y cerrar transacciones sin escribirlo manualmente. |
| **📊 Métricas/Monitoreo** | Medir tiempos de Ejecución. |
| **❌ Manejo de errores** | Capturar y tratar excepciones de forma centralizada. |

---

## 🧱 ¿Cómo funciona en Spring?
Spring usa [Proxies](/00_INTRODUCCIÓN/02_Definiciones/05_Proxies.md) y Anotaciones para aplicar `AOP`. Es decir:

1. Detecta ciertos objetos o clases (por ejemplo, los anotados con `@Transactional`, `@Scheduled`, etc.).
2. Crea un **envoltorio** al rededor del método (Un Proxy).
3. Antes, Despues o incluso _en lugar_ de ejecutar el método, **aplica** lógica definida por el desarrollador.

---

## 🧪 Ejemplo básico

```bash
com.yoi.aopdemo
├── AopConfig.java           # Activador de AOP
├── UsuarioService.java      # Servicio de prueba
├── UsuarioAspect.java       # Aspecto con todas las anotaciones
└── AopDemoApplication.java  # Main Spring Boot
```

## 🚀 Paso 1: Activar AOP

```java
@Configuration
@EnableAspectJAutoProxy // Habilita los proxies y el AspectJ
public class AopConfig {
}
```

## 🧠 Paso 2: Clase Servicio (UsuarioService)

```java
@Service
public class UsuarioService{
    public String crearNombre(String nombre){
        if(nombre.equals("error")){
            throw new RuntimeException("Nombre Invalido");
        }
        return "Usuario:" + nombre + "Creado con Éxito!!!";
    }

}
```

## 🧩 Paso 3: Aspecto con todas las anotaciones (UsuarioAspect)

```java
@Aspect
@Component
public class UsuarioAspect{

    // Ejecutar ANTES del método.
    @Before("execution(* com.yoi.aopdemo.UsuarioService.*(..))")
    public void antesDelMetodo(JoinPoint joinPoint){
        System.out.println("👉 [Before] Entrando a: " + joinPoint.getSignature().getName());
    }

    // Ejecutar DESPUES del método (éxito o fallo).
    @After("execution(* com.yoi.aopdemo.UsuarioService.*(..))")
    public void despuesDelMetodo(JoinPoint joinPoint){
        System.out.println("✅ [After] Salió de: " + joinPoint.getSignature().getName());
    }

    // Ejecutar SOLO SI el método retorna sin errores.
    @AfterReturning(pointcut = "execution(* com.yoi.aopdemo.UsuarioService.*(..))", returning = "resultado")
    public void despuesDeRetornar(JoinPoint joinPoint, Object resultado){
        System.out.println("🎉 [AfterReturning] Resultado: " + resultado);
    }

    // Ejecutar SOLO SI el método lanza error.
    @AfterThrowing(pointcut = "execution(* com.yoi.aopdemo.UsuarioService.*(..))", throwing = "ex")
    public void despuesDeExcepción(JoinPoint joinPoint Throwable ex){
        System.out.println("❌ [AfterThrowing] Excepción en "+ joinPoint.getSignature().getName() + ": " + ex.getMessage())
    }

    // RODEAR completamente el método para MEDIR TIEMPO
    @Around("execution(* com.yoi.aopdemo.UsuarioService.*(..))")
    public Object medirTiempoEjecución(ProceedingJoinPoint pjp) throws Throwable{
        Long inicio = System.currentTimeMillis();
        Object resultado = pjp.proceed();
        Long fin = System.currentTimeMillis();
        System.out.println("⏱️ [Around] Tiempo de ejecución: " + (fin - inicio) + "ms");
        return resultado;
    }
}
```

### 🧪 Resultado al ejecutarlo (caso exitoso)
```bash
👉 [Before] Entrando a: crearUsuario
✅ [After] Salió de: crearUsuario
🎉 [AfterReturning] Resultado: Usuario Yoi creado con éxito!
⏱️ [Around] Tiempo de ejecución: 3ms
```

### 💥 Resultado si se lanza error (crearUsuario("error"))
```bash
👉 [Before] Entrando a: crearUsuario
✅ [After] Salió de: crearUsuario
❌ [AfterThrowing] Excepción en crearUsuario: Nombre inválido
⏱️ [Around] Tiempo de ejecución: 1ms
```