Para explicar de forma clara **JUnit** voy a estar usando la siguiente clase **Persona** para mostrar la sintaxis de **JUnit**
```Java
public class Persona {  
 
    private Long id;  
    private String nombre;  
    private String apellido;  
    private String email;  
    private LocalDate fechaNacimiento;  
    private int edad;  
    private List<Persona> amigos;  
    private Queue<Tarea> tareas;

	// ...
}
```

# Qué es?
Es un framework que permite realizar pruebas de clases Java de manera controlada. De esta forma evalúa si el comportamiento de los métodos de la clase es el esperado.
> Útil en prueba de Regresión. **([[Regression Test VS Retest]])**

## Dependencias (maven)
```xml title:pom.xml
<!-- JUnit Jupiter API for creating tests -->  
<dependency>  
    <groupId>org.junit.jupiter</groupId>  
    <artifactId>junit-jupiter-api</artifactId>  
    <version>5.10.0</version>  
    <scope>test</scope>  
</dependency>  
  
<!-- JUnit Jupiter Engine to run tests -->  
<dependency>  
    <groupId>org.junit.jupiter</groupId>  
    <artifactId>junit-jupiter-engine</artifactId>  
    <version>5.10.0</version>  
    <scope>test</scope>  
</dependency>

<!-- Opcionales para agregar Suites o tests parametrizados -->
<!-- JUnit Platform Suite API -->  
<dependency>  
    <groupId>org.junit.platform</groupId>  
    <artifactId>junit-platform-suite-api</artifactId>  
    <version>1.10.0</version>  
    <scope>test</scope>  
</dependency>

<!-- JUnit 5 Parameterized Tests -->  
<dependency>  
    <groupId>org.junit.jupiter</groupId>  
    <artifactId>junit-jupiter-params</artifactId>  
    <version>5.10.0</version>  
    <scope>test</scope>  
</dependency>
```


## Diseño
- **Patrón Command**.
- **Patrón Composite**.

## Métodos
- **setUp()**: usa **@BeforeEach** o **@BeforeAll**.
- **tearDown()**: usa **@AftearEach** o **@AfterAll**

```Java title:EjemploSetUpTearDown
import org.junit.jupiter.api.*;

public class PersonaTest {  
    private Persona persona;  
  
    @BeforeEach  
    public void setUp(){  
        persona = new Persona(1L, "Juan", "Pérez", "juanperez@gmail.com", LocalDate.of(1990, 3, 2));  
    }  
  
    @AfterEach  
    public void tearDown() {  
        persona = null;  
    }
    
	// ...
}
```

# Asserts
### Aserciones en JUnit
- **assertTrue(expresión)**  
  Comprueba que la expresión evalúe a `true`.
- **assertFalse(expresión)**  
  Comprueba que la expresión evalúe a `false`.
- **assertEquals(esperado, real)**  
  Comprueba que `esperado` sea igual a `real`.
- **assertNull(objeto)**  
  Comprueba que `objeto` sea `null`.
- **assertNotNull(objeto)**  
  Comprueba que `objeto` no sea `null`.
- **assertSame(objeto_esperado, objeto_real)**  
  Comprueba que `objeto_esperado` y `objeto_real` sean el mismo objeto.
- **assertNotSame(objeto_esperado, objeto_real)**  
  Comprueba que `objeto_esperado` no sea el mismo objeto que `objeto_real`.
- **fail()**  
  Hace que la prueba falle intencionalmente.

# Suits
Es una forma de agrupar los tests 
```java title:Suite
import org.junit.platform.suite.api.SelectClasses;  
import org.junit.platform.suite.api.Suite;  
  
@Suite  
@SelectClasses({  
        PersonaTest.class,  
        TareaTest.class  
})  
public class TestsSuite {  
	// vacio
	// ejecuta los tests de persona y tarea simultaneamente
}
```

# Tests dinámicos
Es un caso de prueba generado en tiempo de ejecución.
```Java title:testsDinamicos
@TestFactory  
@DisplayName("Verifica que un grupo de personas puedan agregarse como amigos")  
public Stream<DynamicTest> testAgregarAmigos() {  
    List<Persona> nuevosAmigos = List.of(  
            new Persona(2L, "Maria", "Gomez", "mariagomez@gmail.com", LocalDate.of(1999, 3, 2)),  
            new Persona(3L, "Jose", "Pereira", "josepereira@gmail.com", LocalDate.of(2000, 5, 22)),  
            new Persona(4L, "Enrique", "Gomez", "enrique@gmail.com", LocalDate.of(2003, 1, 15))  
    );  
  
    nuevosAmigos.forEach(persona.getAmigos()::add);  
  
    return nuevosAmigos.stream()  
            .map(amigo -> DynamicTest.dynamicTest(  
                    amigo.toString(),  
                    () -> {                          Assertions.assertTrue(persona.getAmigos().contains(amigo),  
                                "El amigo " + amigo.getNombre() + " no se encuentra en la lista");  
                        System.out.println(amigo.getNombre() + " tiene: " + amigo.getEdad());  
                    }  
            ));  
}  
  
@TestFactory  
@DisplayName("Verifica que un grupo de personas puedan ser eliminadas de la lista de amigos")  
public Stream<DynamicTest> testEliminarAmigos() {  
    List<Persona> nuevosAmigos = List.of(  
            new Persona(2L, "Maria", "Gomez", "mariagomez@gmail.com", LocalDate.of(1999, 3, 2)),  
            new Persona(3L, "Jose", "Pereira", "josepereira@gmail.com", LocalDate.of(2000, 5, 22)),  
            new Persona(4L, "Enrique", "Gomez", "enrique@gmail.com", LocalDate.of(2003, 1, 15))  
    );  
  
    nuevosAmigos.forEach(persona.getAmigos()::add);  
  
    return nuevosAmigos.stream()  
            .map(amigo -> DynamicTest.dynamicTest(amigo.toString(), () -> {  
                Assertions.assertTrue(persona.getAmigos().contains(amigo), "El amigo existe");  
                persona.getAmigos().remove(amigo);  
                Assertions.assertFalse(persona.getAmigos().contains(amigo), "El amigo no fue eliminado correctamente");  
            }));  
}
```

## Tests parametrizados