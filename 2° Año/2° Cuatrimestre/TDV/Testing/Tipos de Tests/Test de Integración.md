## Definición

Los **test de integración** son pruebas que se realizan para verificar cómo interactúan diferentes componentes o sistemas entre sí. Su objetivo es detectar problemas que pueden surgir cuando los módulos individuales se combinan y asegurar que funcionan juntos como se espera.

## Propósito

- **Verificar interfaces**: Comprobar que las interfaces entre diferentes módulos o sistemas están correctamente implementadas.
- **Detectar errores de integración**: Identificar problemas que pueden no ser evidentes en pruebas unitarias debido a la interacción entre componentes.
- **Asegurar funcionalidad**: Confirmar que el sistema completo cumple con los requisitos funcionales al integrar varios módulos.

## Características

- **Foco en la interacción**: Los tests de integración se centran en la interacción entre módulos, en lugar de en el comportamiento individual.
- **Niveles de integración**: Pueden realizarse a diferentes niveles, como integración de componentes, integración de sistemas, etc.
- **Pruebas automatizadas**: A menudo se utilizan pruebas automatizadas para facilitar la ejecución de pruebas de integración.

## Tipos de Test de Integración

1. **Integración de Big Bang**: Todos los componentes se integran y prueban al mismo tiempo.
2. **Integración Incremental**: Los componentes se integran y prueban uno a la vez.
3. **Integración basada en un diseño**: Se integran componentes de acuerdo con un diseño específico que define las interacciones.

## Ejemplo de Test de Integración

```java title:ejemplo
@Test
public void testIntegracionServicioYRepositorio() {
    // Dado que tengo un servicio de usuario y un repositorio de usuario
    UserService userService = new UserService(userRepository);
    
    // Cuando guardo un nuevo usuario
    User user = new User("John Doe", "john@example.com");
    userService.save(user);
    
    // Entonces el usuario debe ser recuperado correctamente del repositorio
    User retrievedUser = userRepository.findByEmail("john@example.com");
    assertEquals("John Doe", retrievedUser.getName());
}
```