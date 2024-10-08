- La estructura primaria se podrá expandir y contraer dinámicamente bajo algún criterio o algoritmo. Cuando la estructura primaria crece, se reorganizan todos los elementos en la tabla de hashing (operación costosa), el efecto buscado es que decrezca la longitud de las listas de rebalse (bajando así el costo de acceso).

- El crecimiento de la estructura primaria no se da continuamente, sino cuando se cumple cierta condición. Esa condición evalúa cómo es la cantidad de elementos actual respecto al tamaño de la estructura primaria.

- Se define el un **factor de carga de diseño preestablecido** (ρd).

- Se calcula el límite de crecimiento **L**, a partir del cual la estructura primaria debe crecer. Cuando la cantidad de elementos en la estructura **sea mayor o igual a L**, la estructura debe crecer (cambia M). Se calcula L como:

![[FormulaCrecimientoHashing.png]]