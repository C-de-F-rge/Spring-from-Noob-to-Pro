# 🌐 ¿Qué es un Controlador MVC en Spring?

Un **Un Controlador MVC** es una la clase anotada Java con `@Controller` que gestiona las solicitudes de la capa web y coordina la producción de la visita final. 

El `DispatcherServlet` de **Spring MVC** actúa como Front Controller; intercepta todas las peticiones **HTTP** y las envia al método de controlador adecuado en la **URL** y el método **HTTP**.

## 🛠️ Creación de un Controller MVC
```java
@Controller
@RequestMapping("/usuarios")
public class GreetingController{

    @GetMapping("/{id}")
    public String verUsuario(@PathVariable Long id, Model model){
        //Lógica para obtener el Usuario
        return "usuarioDetalle" // nombre de la vista (greeting.html, greeting.jsp, etc.)
    }

    @PostMapping
    public String crearUsuario(@ModelAttribute Usuario usuario){
        // Lógica para crear un nuevo usuario
        return "redirect:/usuarios";
    }

    @PutMapping("/{id}")
    public String actualizarUsuario(@PathVariable Long id, @ModelAttribute Usuario usuario){
        //Lógica para actualizar el usuario
        return "redirect:/usuarios";
    }

    @DeleteMapping("/{id}")
    public String eliminarUsuario(@PathVariable Long id){
        //Lógica para eliminar el Usuario
        return "redirect:/usuarios";
    }
     
}
```

---
## ⚠️ Consideraciones al usar PUT y DELETE desde formularios HTML

Los formularios HTML estándar solo admiten los métodos GET y POST. Para enviar solicitudes PUT o DELETE desde un formulario, Spring proporciona el filtro HiddenHttpMethodFilter, que permite emular estos métodos mediante un campo oculto _method.​
