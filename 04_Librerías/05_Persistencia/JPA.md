# JPA Persistencia de Datos en Spring


## 🧠 ¿Cómo funciona la convención de nombres?

1. **Prefijo:** Indica la operación que se va a realizar, como `findBy`, `readBy`, `getBy`, `countBy`, `existBy`, `deleteBy`.

2. **Criterios:** Especifica las condiciones útilizando, los nombres de las propiedades de la entidad y operadores como `And`, `Or`, `Between`, `LessThan`, `GreaterThan`, `Like`, `Containing`, `IgnoreCase`, etc.

### Sintaxis:
```java
List<Usuario> prefijo-parametro-criterios(Tipo parametro);
```

### Ejemplo:
```java
List<Producto> findByNombreContaining(String nombre);
```
---

## 🧭 Prefijos de Métodos

| **Prefijo** | **Descripción** |
|-----------|-------------------|
| [`findBy`](/901_SPRING_JPA/02_Prefijos/FindBy.md) | Recupera una lista de entidades que coinciden con los criterios. |
| [`getBy`](/901_SPRING_JPA/02_Prefijos/GetBy.md) | Similar a `findBy`, pero semánticamente indica una obtención. |
| [`readBy`](/901_SPRING_JPA/02_Prefijos/ReadBy.md) | Otra variante para recuperar datos. |
| [`queryBy`](/901_SPRING_JPA/02_Prefijos/QueryBy.md) | Utilizado para consultas personalizadas. |
| [`countBy`](/901_SPRING_JPA/02_Prefijos/CountBy.md) | Cuenta el número de entidades que coinciden con un criterio. |
| [`existBy`](/901_SPRING_JPA/02_Prefijos/ExistBy.md) | Verifica la existencia de almenos una entidad que coincida con los criterios. |
| [`deleteBy`](/901_SPRING_JPA/02_Prefijos/DeleteBy.md) | Elimina entidades que coincidan con los criterios. |
| [`removeBy`](/901_SPRING_JPA/02_Prefijos/RemoveBy.md) | Similar a `deleteBy`, elimina entidades según los criterios. |

### Ejemplo:​
```java
List<Producto> findByNombre(String nombre);
```
Este método recupera todos los productos cuyo nombre coincide exactamente con el valor proporcionado.

---

## 🧩 Criterios de Consulta
Los criterios definen las condiciones específicas de la consulta y se basan en los nombres de las propiedades de la entidad. Puedes combinarlos utilizando operadores lógicos como And y Or.


## 🔹 Operadores de Comparación

| **Operador** | **Descripción** |
|------------|-------------------|
| `Is`,`Equals` | Igualdad exacta |
| `Not`, `IsNot` | Desigualdad |
| `LessThan` | Menor que |
| `LessThanEqual` | Menor o igual que |
| `GreaterThan` | Mayor que |
| `GreaterThanEqual` | Mayor o igual que que |
| `Between` | Dentro de un rango |
| `In` | Dentro de una colección de valores | 
| `NotIn` | Fuera de una colección de valores |

### Ejemplo:
```java
List<Producto> findByPrecioBetween(Double min, Double max);
```


## 🔹 Operadores de Texto

| **Operador** | **Descripción** |
|------------|-------------------|
| `StartingWith` | Comienza con una cadena específica |
| `EndingWith` | Termina con una cadena específica |
| `Containing`, `Contains` | Contiene una cadena específica |
| `Like` | Coincide con un patron utilizando comodines |
| `NotLike` | No coincide con un patron |
| `IgnoreCase` | Ignora mayusculas y minusculas en la comparación |

### Ejemplo:
```java
List<Producto> findByNombreContainingIgnoreCase(String nombre);
List<Producto> findByPrecioBetween(Double min, Double max);
List<Producto> findByFechaCreacionAfter(LocalDate fecha);
List<Producto> findByStockGreaterThanEqual(Integer stock);

```
Este método recupera productos cuyo nombre contiene la cadena proporcionada, sin importar mayúsculas o minúsculas.


## 🔹 Operadores de Fecha y Tiempo

| **Operador** | **Descripción** |
|------------|-------------------|
| `Before` | Fecha anterior a la proporcionada |
| `After` | Fecha posterior a la proporcionada |

### Ejemplo:
```java
List<Producto> findByFechaCreacionAfter(LocalDate fecha);
```
Este método recupera productos creados después de la fecha especificada.


## 🔹 Operadores de Nulidad y Booleanos

| **Operador** | **Descripción** |
|------------|-------------------|
| `IsNull` | La propiedad es nula |
| `IsNotNull` | La propiedad no es nula  |
| `True` | La propiedad es verdadera |
| `False` | La propiedad es falsa |

### Ejemplo:
```java
List<Producto> findByDisponibleTrue();
```
Este método recupera productos que están disponibles.


## 🔹 Operadores de Ordenación y Límite

| **Operador** | **Descripción** |
|------------|-------------------|
| `OrderBy` | ordena los resultados según una propiedad |
| `Asc` | Orden ascendente  |
| `Desc` | Orden decendente |
| `Top`, `First` | Limita el número de resultados devueltos |

### Ejemplo:
```java
List<Producto> findTop5ByOrderByPrecioDesc();
List<Producto> findByCategoriaOrderByNombreAsc(String categoria);
```


## 🔗 Combinación de Criterios
Puedes combinar múltiples criterios utilizando And y Or:

```java
List<Producto> findByNombreAndPrecio(String nombre, Double precio);
List<Producto> findByNombreContainingAndPrecioBetweenOrderByFechaCreacionDesc(String nombre, Double min, Double max);
```

## Ejemplo de orden agregado
```java
List<Figura> findByColorOrderByIdAsc(String color);
```