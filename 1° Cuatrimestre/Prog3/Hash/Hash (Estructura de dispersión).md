
**Motivación/Objetivo**
Se requiere un mecanismo de **acceso asociativo** (por contenido) a registros con la menor cantidad posible de accesos (una lectura solamente si fuese posible). 

### Definición
Estructura tipo "**Clave** : **Valor**"

Se define una función **h** (llamada **función de hashing**) que, dada una clave de búsqueda x determina la posición de almacenamiento de sus datos asociados.

Lleva la búsqueda a una complejidad **O(1)** o cercano. Bueno para aplicaciones con una alta frecuencia de búsquedas.

### Conceptos
**x**: es la clave de búsqueda, varia según el dominio. Es por la cual se guarda la información.

**h(x)**: [función de hashing](###Definición) previamente mencionada, convierte el elemento x (clave) en el valor asociado. La función de hashing mas utilizada es **h(x) = x mod M** ([[Modulo en calculadora]])

**M**: espacio de almacenamiento dividido en M baldes.
- Cada balde puede guardar más de una clave. Cada lugar es llamado ranura
- Generalmente se elige M como un número primo ya que la función mod dispersa los datos de manera más uniforme.

![[Hash01.png]]


**Factor de Carga ρ** (o densidad de almacenamiento): Es la proporción de espacio utilizado respecto del espacio total de almacenamiento asignado.

**ρ (rho)** = cantidad de datos / capacidad total de los baldes

![[FactorCarga01.png]]

Se dan dos situaciones dependiendo de cómo distribuye los datos la
función de hashing:
- [[Hashing Perfecto]]
- [[Hashing Puro]]


