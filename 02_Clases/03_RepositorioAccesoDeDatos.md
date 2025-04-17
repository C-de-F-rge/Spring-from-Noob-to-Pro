# 🧱 ¿Qué es @Repository?

En **Spring**, la anotación `@Repository` se utiliza para identificar que una clase es un componente de acceso a datos, tambien conocído como [DAO (Data Access Object)](/00_INTRODUCCIÓN/02_Definiciones/06_DAO.md).

Manejo de excepciones: Spring proporciona una traducción automática de excepciones específicas de la base de datos a excepciones no verificadas (unchecked) específicas de Spring, como DataAccessException. Esto facilita el manejo uniforme de errores en la capa de persistencia.


## 🛠️ ¿Cómo se utiliza @Repository?

Existen dos métodos para implementarla correctamente

---
 
### 🧱 Enfoque DAO (@Repository en clases DAO)

Un DAO es una clase que proporciona una interfaz abstracta para interactuar con una fuente de datos, encapsulando todos los detalles de acceso a la base de datos. Este patrón es útil cuando se necesita un control más detallado sobre las operaciones de persistencia.

```java
@Repository
public class UsuarioDAO {

    @PersistenceContext
    private EntityManger entityManger;

    public Usuario buscarPorId(Long id) {
        return entityManager.find(Usuario.class, id);
    }

    public void guardar(Usuario usuario){
        entityManager.persist(usuario);
    }

    public void eliminar(Usuario usuario){
        entityManager.remove(usuari);
    }

    // Otros métodos personalizados...
}
```

---

### 🧰 Enfoque Repository (@Repository en interfaces)

En Spring Data JPA, un Repository es una interfaz que extiende una de las interfaces proporcionadas por el framework, como [JpaRepository](/04_Librerías/05_Persistencia/JPA.md) o [CrudRepository](/04_Librerías/05_Persistencia/CRUDREP.md). Spring se encarga de proporcionar la implementación en tiempo de ejecución.

```java
@Repository
public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
    List<Usuario> findByNombre(String nombre);
}
```