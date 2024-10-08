El diagrama de casos de uso es una representación gráfica de las **interacciones entre los actores externos y el sistema** que se está modelando. Este diagrama se utiliza para capturar los requisitos funcionales del sistema desde la perspectiva del usuario final.

Especifica el **Que**, pero no el **Como**.
### Componentes Principales

1. **Actores**:
    - Representan entidades externas que interactúan con el sistema. Pueden ser personas, otros sistemas o dispositivos.
    - Se dibujan como figuras de palo (monigotes).
	- Un actor puede ser:
		- Un humano.
		- Un hardware.
		- Otro sistema.
	- Pueden ser primarios (uno único) o secundarios (cero o muchos).
	- Un actor especial es el **clock** o **reloj** que representa un tiempo de ejecución especifico para un caso de uso.

2. **Casos de Uso**:
    - Representan funciones o servicios que el sistema proporciona a los actores.
    - Se dibujan como elipses.

3. **Relaciones**:
    - **Asociación**: Conexión directa entre un actor y un caso de uso, indicando que el actor participa en el caso de uso.
    - **Inclusión** («include»): Indica que un caso de uso incorpora explícitamente el comportamiento de otro caso de uso.
    - **Extensión** («extend»): Indica que un caso de uso puede extender el comportamiento de otro caso de uso bajo ciertas condiciones.
    - **Generalización**: Relación jerárquica que indica que un actor o un caso de uso es una especialización de otro.

### Diagramas de Casos de Uso en el Contexto del Desarrollo

Los diagramas de casos de uso son particularmente útiles en las etapas iniciales del desarrollo, como la recopilación de requisitos y la planificación. Proporcionan una visión de alto nivel del sistema y de sus interacciones, lo que permite a los equipos de desarrollo y a los interesados obtener una comprensión clara y compartida del comportamiento esperado del sistema.

### Descripción del Diagrama de Caso de Uso

**Estructura**:
- **Nombre del caso de uso**: Nombre representativo de dicha funcionalidad.
- **Descripción breve**: Descripción en un párrafo de lo que hace ese caso de uso.
- **Actor primario/secundario(s)**: Actores involucrados en el CU.
- **Trigger**: Situación por la que el caso de uso se activa.
- **Curso básico**: Flujo de ejecución ideal.
- **Cursos alternativos**: Desviaciones del flujo de ejecución ideal.
- **Precondición**: un caso de uso que se debe cumplir para que otro se de. Por ejemplo para comprar un producto debes que estar logeado.
- **Postcondición**: es una consecuencia tras un caso de uso. Por ejemplo registrarte hace que luego estes logeado.
### Sintaxis de Diagrama

**Generalización**:
![[Generalización.png]]

**Inclusión**:
![[Include.png]]

**Extensión**:
![[Extend.png]]
