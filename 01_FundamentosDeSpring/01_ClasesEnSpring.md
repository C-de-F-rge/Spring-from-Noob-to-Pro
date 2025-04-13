# Las Clases en Spring 

Saber qué tipos de clases se manejan en Spring es como entender los roles de cada personaje en una obra de teatro 🎭. Cada uno tiene su función y juntos hacen que tu app funcione como un sistema bien orquestado.

## 🎬 Tipos de clases en Spring

| **Tipo de Clases** | **Anotación Principal** | **Rol de la Aplicación** |
|--------------------|-------------------------|--------------------------|
| [Componente Genérico](/02_Clases/01_ComponenteGenerico.md) | `@Component` | Cualquier clase que **Spring** deba gestionar como un bean. |
| [Servicio Lógica de Negocio](/02_Clases/02_ServicioLogicaDeNegocio.md) | `@Service` | Contiene la **Lógica** principal de la aplicación. |
| [Repositorio (acceso de datos)](/02_Clases/03_RepositorioAccesoDeDatos.md) | `@Repository` | **Accede** a bases de datos, **Maneja** entidades, **Usa** JPA. |
| [Controlador MVC](/02_Clases/04_ControladorMVC.md) | `@Controller` | **Atiende** solicitudes web (HTML, formularios, vistas). |
| [Controlador REST](/02_Clases/05_ControladorREST.md) | `@RestController` | **Expone** endpoints REST (respuestas JSON). |
| [Clase de Configuración](/02_Clases/06_ClaseDeConfiguracion.md) | `@Configuration` | **Define** beans manuales o configuraciones especiales. |
| [Clase de Arranque](/02_Clases/07_ClaseDeArranque.md) | `@SpringBootApplication` | **Clase Principal** para iniciar la app Spring Boot. |
| [Bean Manual](/02_Clases/08_BeanManual.md) | `@Bean`, dentro de `@Configuration` | **Declara objetos** que Spring debe gestionar como beans. |
| [DTOs / Entidades](/02_Clases/09_DTOsEntidades.md) | `@Entity`, sin anotación especial. | **Representa Datos:** Objetos planos, modelos de `DB`. |
| [Aspects (AOP)](/02_Clases/10_AspectsAOP.md) | `@Aspect` | Clases que **interceptan** otras para generar `Lógica común`. |
| [Componentes Reactivos](/02_Clases/11_ComponentesReactivos.md) | `@Controller`, `@Service`, etc. | Pero usando **WebFlux**(`Mono`, `Flux`, etc.). |
| [Eventos/Listeners](/02_Clases/12_EventosListeners.md) | `@EventListener`, `ApplicationEventPublisher` | Para arquitectura **Event-Driven**. |