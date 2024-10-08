Framework inspirado en Junit y Nunit.
Aplicable desde testeo de unidad hasta testeo de integración.
Test a datos.
Tests parametrizados.

Busca mejorar Junit 4 y no tanto Junit 5

Cada caso de test me lo va a generar automaticamente TestNG.

# Tags
- **suite**: Puede contener uno o mas tests
- **test**: puede contener uno o mas clases
-  **class**: una clase TestNG que puede contener uno o mas metodos (@Test)


# Anotaciones
@BeforeSuite antes de los tests
@AfterSuite despues de los test
@BeforeTest antes de cualquier 
@AfterTest
@BeforeGroups
@AfterGroups
@BeforeClass
@AfterClass
**@DataProvider** provee datos, responsable de administrar los datos. 


la diferencia con Junit es que va a ejecutar los tests a la vez, y no 1 a la vez porque ya tengo los datos precargados. Si tengo 10 tests, TestNG prueba todos los casos o gran parte a la 
vez, mientras que junit ejecuta 1 detras de otro.

En Junit no se pasan parametros en los tests, en TestNG si

las anotaciones **before** se ejecutan antes que el generador, los **after** despues

se genera un caso 1 caso de prueba por cada dato, si tengo 6 datos hardcodeados y llamo 5 veces, entonces se me generan 30 casos de prueba.
# Como usar
se puede crear un archivo **testng.xml**, no genera compilacion de codigo.

parametros, xml, modificadores
