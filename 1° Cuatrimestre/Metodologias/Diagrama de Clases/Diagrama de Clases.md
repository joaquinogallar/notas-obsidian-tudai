---

---
**Se utiliza para:**
- Explorar conceptos del dominio
- Analizar requerimientos
- Mostrar el diseño detallado de software orientado a objetos

**Generalmente contiene:**
- Clases
- Interfaces
- Relaciones

Se utiliza al inicio de un **Spring** o para documentar.

## Clases
Una clase es la descripción de un conjunto de objetos que comparten los mismos:
- Atributos
- Operaciones
- Semántica

En las clases de captura el vocabulario del sistema que se está desarrollando.
Representan los objetos del mundo real y elementos conceptuales.

### Clases en UML
![[ClasesUML.png]]

Como representar los distintos **atributos** y **operaciones**:
- **Public**: +
- **Private**: -
- **Protected**: #

**Clases Abstractas**: su nombre se pone en *cursiva*.

**Métodos o Atributos estáticos**: se <u>subraya</u> el nombre del método o atributo.

**Constantes**: en caso de tener que representar una constante su nombre debe ir en MAYUSCULAS. 

**Interfaces** y Clases **Abstractas**: las **interfaces** y clases **abstractas** se representan con su respectivo nombre (interface, abstract) encerrado en "<>" y arriba del nombre de la clase/interface. 

**Tipo de los atributos**: luego del nombre del atributo se debe poner ":" y el tipo (String, Integer, Persona, Auto, etc).

**Parámetros**: similar a la declaración de los atributos (pero sin accesibilidad).

**Retornos de los métodos**: luego de definir el método van ":" y el tipo que retorna.

![[Ejemplo01.png]]
![[Ejemplo02.png]]

### Relaciones entre clases
Las relaciones son conexiones entre clases. Modelan la colaboración entre clases.
Hay varios tipos:
- [[1° Cuatrimestre/Metodologias/Diagrama de Clases/Relaciones/Generalización]]
- [[Realización]]
- [[1° Cuatrimestre/Metodologias/Diagrama de Clases/Relaciones/Asociación]] (**estructural**)
- [[Agregación]] (**estructural**)
- [[Composición]] (**estructural**)
- [[Clase de Asociación]]
- [[1° Cuatrimestre/Metodologias/Diagrama de Clases/Relaciones/Dependencia]]

Algunos de estos se denominan como **relaciones estructurales**, donde podemos encontrarnos con los [[Decoradores, Adornos]].

**Dos clases A y B están relacionadas si**:
- Un objeto de la clase **A envía un mensaje a un objeto de la clase B**
- Un objeto de la clase **A crea un objeto de la clase B**
-  Un objeto de la clase **A tiene un atributo cuyo tipo es B** o que es una colección de objetos de tipo B
- Un objeto de la clase **A recibe un mensaje con un objeto de la clase B como parámetro**
- Un objeto de la clase **A define un método con un objeto de la clase B como retorno**
- La clase **A es superclase de B**
-  La clase **A implementa la clase B**