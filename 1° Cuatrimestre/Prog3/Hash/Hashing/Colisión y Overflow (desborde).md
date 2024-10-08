Es una situación en la que un registro es asignado a una dirección (balde) que no tiene suficiente espacio para ser almacenado.

Las funciones de tipo hashing puro no está garantizado que la función envíe cada elemento a una dirección diferente: dos claves diferentes pueden tener el mismo resultado en su función de hash (SINÓNIMOS) produciendo una **colisión** en ese balde.

![[Overflow01.png]]

### Estrategias para el overflow
- Se buscan estructuras dinámicas.
- El espacio de almacenamiento se expande o reduce a partir de las bajas y altas de los datos.
- 2 técnicas:
	- **[[Hashing Separado]]** (El espacio físico primario (array) se mantiene fijo)
	- **[[Hashing Separado con Crecimiento]]** (El espacio físico primario se modifica)