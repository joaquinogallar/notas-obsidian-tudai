## Definición

El **mocking** es una técnica utilizada en pruebas de software que permite crear **mocks** (objetos simulados) de componentes o dependencias de una unidad de código en prueba. Esto permite aislar la unidad que se está probando para verificar su comportamiento sin depender de las implementaciones reales de sus dependencias.

## ¿Por qué usar mocking?

1. **Aislamiento de pruebas**: Permite probar una unidad de código sin depender de sus dependencias, lo que ayuda a identificar fallos específicos en la lógica de negocio.

2. **Control sobre el comportamiento**: Los mocks permiten simular el comportamiento de las dependencias, como devolver valores específicos, lanzar excepciones, o controlar el estado del objeto simulado.

3. **Mejora la velocidad de las pruebas**: Al evitar la necesidad de instanciar componentes reales (como bases de datos, servicios web, etc.), las pruebas se ejecutan más rápidamente.

4. **Facilita la verificación de interacciones**: Se puede verificar cómo se interactúa con los mocks, como cuántas veces se llamó a un método o qué parámetros se pasaron, lo que es útil para validar el comportamiento esperado.

## Tipos de mocks

1. **Mocks**: Objetos simulados que verifican las interacciones. Se utilizan para comprobar que los métodos fueron llamados con los parámetros esperados.

2. **Stubs**: Objetos que devuelven respuestas predefinidas a llamadas específicas, pero no verifican las interacciones.

3. **Spies**: Objetos que permiten verificar llamadas a métodos en un objeto real. Se pueden usar para observar el comportamiento real del objeto y verificar las interacciones.

## Ejemplo de uso de [[Mockito]]

```java
import static org.mockito.Mockito.*;

public class UserServiceTest {

    @Test
    public void testGetUser() {
        // Crear un mock del repositorio
        UserRepository userRepositoryMock = mock(UserRepository.class);
        
        // Definir el comportamiento del mock
        when(userRepositoryMock.findById(1)).thenReturn(new User("John", "Doe"));
        
        // Crear la unidad a probar
        UserService userService = new UserService(userRepositoryMock);
        
        // Llamar al método a probar
        User user = userService.getUser(1);
        
        // Verificar interacciones y resultados
        assertEquals("John", user.getFirstName());
        verify(userRepositoryMock).findById(1); // Verifica que se llamó al método
    }
}

