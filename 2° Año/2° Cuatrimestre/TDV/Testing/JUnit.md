# Qué es?
Es un framework que permite realizar pruebas de clases Java de manera controlada. De esta forma evalúa si el comportamiento de los métodos de la clase es el esperado.
> Útil en prueba de Regresión. **([[Regression Test VS Retest]])**
## Diseño
- **Patrón Command**.
- **Patrón Composite**.

## Métodos
- **setUp()**: usa **@BeforeEach** o **@BeforeAll**.
- **tearDown()**: usa **@AftearEach** o **@AfterAll**

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