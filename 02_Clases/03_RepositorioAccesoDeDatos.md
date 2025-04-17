# 🧱 ¿Qué es @Repository?

En **Spring**, la anotación `@Repository` se utiliza para identificar que una clase es un componente de acceso a datos, tambien conocído como [DAO (Data Access Object)](/00_INTRODUCCIÓN/02_Definiciones/06_DAO.md).

Manejo de excepciones: Spring proporciona una traducción automática de excepciones específicas de la base de datos a excepciones no verificadas (unchecked) específicas de Spring, como DataAccessException. Esto facilita el manejo uniforme de errores en la capa de persistencia.


## 🛠️ ¿Cómo se utiliza @Repository?

Existen dos métodos para implementarla correctamente

---
 
### 🔹 Enfoque DAO: interfaz + implementación

Con el patrón DAO sueles definir una interfaz con las operaciones de acceso a datos y luego una clase de implementación anotada con @Repository que usa EntityManager. Esto te da control total sobre cada consulta y te permite, por ejemplo, combinar múltiples fuentes de datos o usar SQL/JPA avanzado.

**Interfaz:**
```java
public interface UsuarioDAO {
    Usuario buscarPorId(Long id);
    void guardar(Usuario usuario);
    void eliminar(Usuario usuario);
    // otras operaciones...
}
```

**Implementación:**
```java
@Repository
public class UsuarioDAOImpl implements UsuarioDAO {
    @PersistenceContext
    private EntityManager em;

    @Override
    public Usuario buscarPorId(Long id) {
        return em.find(Usuario.class, id);
    }

    @Override
    public void guardar(Usuario usuario) {
        em.persist(usuario);
    }

    @Override
    public void eliminar(Usuario usuario) {
        em.remove(usuario);
    }
    // ...
}
```

---

### 🧰 Enfoque Repository (@Repository en interfaces)

Con el patrón Repository de Spring Data [JPA](/04_Librerías/05_Persistencia/JPA.md), simplemente defines una interfaz que extiende JpaRepository<T,ID> (o [CrudRepository](/04_Librerías/05_Persistencia/CRUDREP.md), etc.), y Spring genera la implementación automáticamente. Obtienes CRUD, consultas derivadas por nombre y paginación sin escribir código de persistencia.

```java
@Repository  // opcional: Spring lo detecta por el repositorio de Data JPA
public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
    List<Usuario> findByNombre(String nombre);
}
```
Si empleas JPA (ya sea en tu DAO o con Spring Data), SIEMPRE tus clases de dominio deben estar anotadas con @Entity.

```java
@Entity
@Table(name = "usuarios")
public class Usuario {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(length = 100, nullable = false)
    private String nombre;

    // …
}
```