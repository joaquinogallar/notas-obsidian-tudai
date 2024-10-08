# Objetivos
- Para el **usuario o cliente** el objetivo es definir la necesidad de su organización, lo que se debe y no hacer.
- Comunicación entre clientes, usuarios y desarrolladores.
- Permitir iniciar la actividad de diseño.
- Soportar las actividades de prueba del sistema.
- Controlar la evolución del sistema.

---
# Especificación de requerimientos

## Qué contiene?
- Información del problema.
- Interfaz externa del sistema con su entorno.
- Propiedades y comportamiento del sistema.
- Restricciones de diseño y fabricación del producto.
- Contribución del sistema.
- Restricciones acerca de las propiedades emergentes.

## Qué NO contiene?
- Requisitos del proyecto: planificación, costes, fases, hitos, etc.
- Diseño.
- Planes de garantía del producto.

## DRU vs ERS
### DRU (Documento de Requerimientos de Usuario)
- Punto de vista del usuario/cliente/interesado.
- Sin demasiado nivel de detalle.
- Se incluye la descripción del problema actual (razones por las que el sistema de trabajo actual es insatisfactorio) y las metas que se espera lograr con la construcción del nuevo sistema.
- [**User Stories**](User%20Stories.md)

### ERS (Especificación de Requerimientos del Software)
- Punto de vista del desarrollador.
- Requisitos del software más detallados.
- Descripción de caracteristicas del sistema  y contribución al logro de los objetivos.

## Características deseables
- **Necesario**: Cuando su omisión provoca una deficiencia en el sistema a construir.
- **Conciso**: Cuando es fácil de leer y entender en cualquier momento.
- **Completo**: Cuando se proporciona la información suficiente para su compresión.
- **Consistente**: Cuando no es contradictorio con otro requerimiento.
- **No ambiguo**: Cuando tiene una única interpretación.
- **Verificable**: Cuando se puede corroborar mediante inspección, análisis demostración o pruebas.

---

# Clasificación general
## Requerimientos Funcionales
- Servicios que proveerá el sistema ante entradas esperadas y no esperadas.
- Servicios que NO debe proveer.

## Requerimientos NO Funcionales
- Hacen referencia a las propiedades emergentes de éste tales como la fiabilidad, el tiempo de respuesta, la capacidad de almacenamiento, etc.

---

# Matriz de Trazabilidad
- Vincula los requisitos del proyecto desde su origen hasta los entregables que lo satisface.
- Ayuda a asegurar que cada requerimiento agrega valor al negocio, exponiendo el vínculo entre requisitos, necesidades de negocio y objetivos de proyecto.
- Permite realizar un seguimiento durante el **ciclo de vida**, mejorando la ingeniería de requisitos al asegurar que estos sean entregados según especificaciones.

## Ejemplo
![[Matriz Trazabilidad.png]]

---

# Validación de requerimientos
### Qué significa validar?
Demostrar que los requerimientos definidos representan las intenciones/necesidades del cliente.

### Por qué?
Los **costos de errores** en los requerimientos son **altos**, por lo cual, la **validación** es muy importante.

Fijar un error de requerimiento después del desarrollo puede resultar en un costo **100 veces mayor** que fijar un error en la implementación.

## Prototipado
**Prototipado de la interfaz de usuario**: es una técnica de representación aproximada de la interfaz de usuario de un sistema de software que permite a clientes y usuarios entender más fácilmente la propuesta.

**Desechables**: se utilizan sólo para la validación delos requisitos y posteriormente se desechan. Pueden ser prototipos en papel o en software.

**Evolutivos**: Una vez utilizados para la validación de los requisitos, se mejora su calidad y se convierten progresivamente en el producto final.

**Mock-ups**: Pantallas típicamente dibujadas a mano en papel. Soporte limitado de verificación. Representan un aspecto concreto del sistema.

**Storyboards**: Evolución de los **mock-ups**. Agregan secuencia de acciones, o escenarios, que se deben realizar con el programa.

**Maquetas**: Versión simplificada del sistema software deseado. Únicamente se implementan pantallas e interconexión entre estas. Puede incluirse implentación sencilla para producir algunos datos reales.

## Inspección o Recorrido
Walkthrough asociada a la inspección de código fuente.
### Objetivos
- Detectar conflictos.
- Aumentar el conocimiento

El autor revisa el producto en detalle, y los participantes manifiestan sus opiniones sobre el mismo.

Permite al clientes y usuarios comprender el significado de cada requisito y manifestar su acuerdo o desacuerdo con los mismos cuando se aplica a [**ERS**](#ERS%20(Especificación%20de%20Requerimientos%20del%20Software)).

Permite validar de manera natural la secuencia de pasos de un caso de uso.

## Generación de Casos de Prueba
- Se basa en que los requerimentos deben ser verificados.
- Los casos de pruebas son artefactos bien definidos para la prueba de software.
- Deben conocerse los datos de entrada así como las tareas a realizar y los resultados esperados.
- Ejemplo:
	- "El sistema permitirá exportar información"