# 🌟 ¿Qué son las anotaciones en Spring?

Las **Anotaciones** en spring son **Metadatos** que le indican al framework como debe comportarse o configurar algo. No son clases en sí mismas, sino instrucciones especiales que se procesan en tiempo de ejecución (o a veces en tiempo de compilación) para cambiar el comportamiento de tu código o para integrarlo con el framework.

## 🌱 Otras anotaciones muy importantes en Spring

| **Anotación** | **¿De qué es?** | **¿Para qué Sirve?** |
|----------|----------------|------------------------|
| [`@Lazy`](/03_Anotaciones/01_Lazy.md) | Gestión de Beans | Crea el Bean **solo cuando se necesita**(Lazy Loading). |
| [`@Primary`](/03_Anotaciones/02_Primary.md) | Gestión de Beans | Marca el Bean que Spring debe **usar por defecto** si hay más beans del mismo tipo. |
| [`@Qualifier`](/03_Anotaciones/03_Qualifier.md) | Inyección de dependencias | Le dice a Spring cual Bean usar **exactamente** cuando hay varios del mismo tipo. |
| [`@Value`](/03_Anotaciones/04_Value.md) | Configuración | Inyecta valores desde `Application.properties` o variables de entorno. |
| [`@PropertySource`](/03_Anotaciones/05_PropertySource.md) | Configuración | Importa archivos `.properties` externos. |
| [`@ConfigurationProperties`](/03_Anotaciones/06_ConfigurationProperties.md) | Configuración | Enlaza propiedades completas de config a una clase POJO. |
| [`@Profile`](/03_Anotaciones/07_Profile.md) | Entornos | **Activa clases/configs** solo en un perfil activo (dev, prod, etc.). |
| [`@Transactional`](/03_Anotaciones/08_Transactional.md) | Transacciones | Abre una transacción automática en métodos de `DB`. |
| [`@EnableTransactionManagement`](/03_Anotaciones/09_EnableTransactionManagement.md) | Transacciones | **Habilita** el manejo de transacciones. |
| [`@Scheduled`](/03_Anotaciones/10_Scheduled.md) | Tareas Programadas | **Ejecuta** un método de forma automática con `Cron` |
| [`@EnableScheduling`](/03_Anotaciones/11_EnableScheduling.md) | Tareas Programadas | **Habilita** las tareas programadas. |
| [`@Async`](/03_Anotaciones/12_Async.md) | Asincronía | **Ejecuta** un método en otro `Hilo`(_sin bloquear_). |
| [`@EnableAsync`](/03_Anotaciones/13_EnableAsync.md) | Asincronía | **Hablita** el procesamiento `Asincróno`. |
| [`@EventListener`](/03_Anotaciones/14_EventListener.md) | Eventos | Método que **responde** a `eventos Publicados`. |
| [`@EnableWebSecurity`](/03_Anotaciones/15_EnableWebSecurity.md) | Seguridad| **Activa** la configuración de `Seguridad Personalizada`(Spring Security). |
| [`@EnableJpaRepositories`](/03_Anotaciones/16_EnableJpaRepositories.md) | JPA | **Activa** el escaneo de interfaces `@Repository`. |
| [`@EntityScan`](/03_Anotaciones/17_EntityScan.md) | JPA | **Especifica** donde están tus clases `@Entity`. |
| [`@RestClientTest`,](/03_Anotaciones/18_Testing.md) <br> [`@WebMvcTest`,](/02_Anotaciones/18_Testing.md) <br> [`@SpringBootTest`](/03_Anotaciones/18_Testing.md) | Testing | Anotaciones de `Test` específicas para **Probar** partes del sistema|