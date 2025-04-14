# Proxy en el Contexto AOP

El `Proxy` bajo el contexto de `AOP` es aquel que envuelve un objeto de tal manera que sirve de intermediario para **interceptar llamadas** a métodos del objeto real e inyectar comportamientos adicionales (`Advice`) sin modificar el códifo Original. 

## Tipos de Advice de los Proxies

| Tipo de Advice       | Cuándo se ejecuta                                   | Descripción                                                                                  |
|----------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| `@Before`            | Antes de la ejecución del método                    | Se ejecuta justo antes de que se invoque el método objetivo.                                 |
| `@After`             | Después de la ejecución (exitoso o con excepción)     | Se ejecuta al terminar la ejecución del método, sin importar si terminó correctamente o no.   |
| `@AfterReturning`    | Solo si el método retorna correctamente             | Se ejecuta cuando el método finaliza de forma exitosa y permite acceder al valor retornado.     |
| `@AfterThrowing`     | Solo si el método lanza una excepción               | Se ejecuta cuando el método lanza una excepción y permite capturar la causa del error.         |
| `@Around`            | Rodeando la ejecución completa del método          | Permite ejecutar código antes y después de la ejecución del método, pudiendo incluso modificar el valor retornado o gestionar excepciones. |

---


## JDK Dynamic Proxies vs. CGLIB en Spring AOP
Para generar los Proxies Spring generalmente puede usar JDK Dynamic Proxies o CGLIB en Spring AOP

| Característica               | JDK Dynamic Proxies                                  | CGLIB                                             |
|------------------------------|------------------------------------------------------|---------------------------------------------------|
| **Requisito**                | La clase debe implementar al menos una interfaz.     | No se requiere que la clase implemente interfaces.|
| **Cómo funciona**            | Crea un proxy que implementa las interfaces del target.| Crea un subclase del target para interceptar llamadas.|
| **Ventaja**                  | Más sencillo y directo cuando se trabaja con interfaces.| Mayor flexibilidad para clases sin interfaces.     |
| **Desventaja**               | Limitado solo a la interfaz, no puede interceptar métodos no públicos si no están definidos en la interfaz. | Puede ocasionar complicaciones con clases finales o métodos finales. |
| **Uso en Spring AOP**        | Por defecto, se utiliza si el bean implementa una interfaz. | Se utiliza cuando el bean no implementa ninguna interfaz o se fuerza su uso.|
