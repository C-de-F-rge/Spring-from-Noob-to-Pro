# 🤖 ¿Qué es la Inyección de Dependencias (DI)?

Es un principio de diseño donde un `objeto` no se encarga de crear sus propias `dependencias`, sino que se las entregan desde afuera (por un contenedor, un framework o una clase superior).

## Ventajas:
- Bajo acoplamiento (los objetos no dependen directamente de otros)
- Más fácil de testear
- Más flexible y mantenible

---

## 🧪 DI en Java puro
En `Java` sin frameworks, tú mismo creas las `dependencias`.
```java
public class Motor{
    public void encender(){
        System.out.println("Motor Encendido");
    }
}

public class Carro{
    private Motor motor;

    public Motor(){
        this.motor = new Motor(); // 😬 fuerte acoplamiento
    }

    public void arrancar(){
        return motor.encender();
    }
}
```
Aquí el `Carro` crea su propia instancia de `Motor`. Está muy **acoplado** a `Motor`, lo que hace dificil remplazarlo o testearlo con mocks.

---

## 🌱 DI con Spring
En spring tú creas las clases y dejas que spring `cree` y `conecte` los objetos por ti.
```java
@Component
public class Motor{
    public void encender(){
        System.out,println("Motor Encendido");
    }
}

@Component
public class Carro{
    private final Motor motor;

    @Autowired
    public Carro(){
        this.motor = motor;
    }

    public void arrancar(){
        return motor.encender();
    }
}
```

### Paso 2: Spring se encarga de inyectarlo

**Con las siguientes anotaciones:**

- `@Component`: Le dice a spring que debe gestionar esta clase como un [Bean](/00_INTRODUCCIÓN/02_Definiciones/02_Bean.md)(Objetivo dentro del Contenedor).

- `@Autowired`: Spring ve que `Carro` necesita un `Motor`, busca uno ya registrado y se lo inyecta automáticamente.

💡 Spring tiene un [contenedor](/00_INTRODUCCIÓN/02_Definiciones/03_AplicationContext.md) que "escanea" todas las clases anotadas y gestiona su ciclo de vida.

---

## 🔧 Tipos de inyección en Spring

| **Tipo** | **Ejemplo** | **Comentario** |
|----------|---------------------------|-----------------|
| **Constructor** | `@Autowired public Carro(Motor motor)` | 👍 Recomendado. |
| **Setter** | `@Autowired public void setMotor(Motor m)` | Cuando no siempre es obligatirio. |
| **Campo** | `@Autowired private Motor motor` | Rápido pero menos testeable |

