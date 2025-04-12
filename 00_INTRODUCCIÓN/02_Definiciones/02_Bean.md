# ☕ ¿Qué es un Bean en Spring?

Un **Bean** es cualquier objeto que sea **administrado** por el `Contenedor de Spring`. Cuando marcas una clase con las anotaciones (`@Component`,`Service`,`Repository`,etc.) o las registras manualmente, estás diciendo lo siguiente: _“Ey Spring, tú te encargas de crear y administrar esta clase como parte de la aplicación.”_

## 🛠️ ¿Qué hace un bean?

Cuando una clase es un `Bean` en Spring:

- ✅ La **crea** automáticamente.

- ✅ La **inyecta** donde se necesite (si otra clase la requiere).

- ✅ La **configura** si tiene propiedades especiales.

- ✅ La **destruye** si ya no se necesita (cuando termina la app, por ejemplo).

- ✅ La **hace parte** del `ApplicationContext`, es decir, el contenedor central de Spring.

---

## 📌 ¿Para qué sirve?

Los `Beans` permiten construir una aplicación donde **cada parte del sistema puede colaborar sin saber cómo están creadas las demás** dando como resultado:

| **Ventajas** | **Descripción** |
|----------------|----------------------------|
| `🔁 Reutilización` | Puedes usar el mismo **bean** en diferentes lugares. |    
| `🧪 Testeabilidad` | Fácil de sustituir por `mocks` y `fakes`. |    
| `🧩 Módulos desacoplados` | Las clases se conectar **sin depender entre si**. |    
| `🔧 Configuración flexible` | Puedes cambiar la implementación sin saber el resto del código. |    