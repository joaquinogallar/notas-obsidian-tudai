# Estrategias
- **Record and Playback**: Selenium IDE, SIKULI.
- **Data-driven testing**: [[2° Año/2° Cuatrimestre/TDV/Testing/TestNG|TestNG]]

## Record and Plaback
Para el desarrollo de casos de pruebas manuales automatizados son especialmente indicadas las herramientas de grabación y reproducción.

| **Ventajas**                            | **Desventajas**                                            |
| --------------------------------------- | ---------------------------------------------------------- |
| Fácil de usar                           | Alto costo de mantenimiento                                |
| Fácil / rápida ejecucion de las pruebas | Si cambia la aplicación, se debe volver a grabar la prueba |
|                                         | Los script contienen datos de entrada fijos                |

# Conceptos clave (Locators)
Clave alfanumérica de búsqueda e identificación de un elemento.

Formato general: **locatorType = argumento**

## Estrategias de localización
- id = id
  Selecciona el elemento con el atributo ***@id***.
  Ejemplo: **id = "userName"**
-  name = name
   Selecciona el primer elemento con el atributo **@name***
   Ejemplo **name = "Tandil"**
- xpath = xpathExpression
  Selecciona el elemento resultado de evaluar la expresión ***Xpath***.
  Ejemplo: **xpath = // input[@name = 'name2' and @value = 'yes']**
- link = textPattern
  Selecciona el elemento indicado en el patrón.
  Ejemplo: **link = "Login"**