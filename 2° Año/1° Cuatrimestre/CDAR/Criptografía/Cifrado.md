*"A partir de un algoritmo, sustituimos una cosa por otra"*

### Cifrado Simétrico

**Cifrado de César**: Tomamos cada letra del mensaje original y la reemplazamos por la letra que está a **N** posiciones de distancia en el abecedario.

Por ejemplo si **N = 2**
![[CifradoCesar01.png]]

**Cifrado de César combinado (Mono-Alfabético)**: en lugar de desplazar, cualquier letra puede sustituirse por cualquier otra lo que implica aumentar la cantidad de combinaciones (26! en el orden de 1027 combinaciones en lugar de 25 con Cesar tradicional).
![[CifradoCesarCombinado01.png]]

**Cifrado Poli-Alfabético**: Varios cifrados mono-alfabéticos combinados. 
- Cada posición tiene un alfabeto diferente. 
- Una misma letra que aparece en distintas posiciones del mensaje, se podría codificar de forma diferente.
![[CifradoPoliAlfabético01.png]]

Podríamos aplicar entonces el patrón de codificación: C1, C1, C2, C1, C2.
Esto lo que nos indica es el orden en el que van a ser usados los diferentes abecedarios que tenemos disponibles. Es decir por cada letra va a usar el abecedario correspondiente, la primera letra se cifra usando C1, la segunda también, pero la tercera con C2, y así con el resto del patrón.
![[cifradoCesarPoli-Alfabético.txt]]

### Cifrado Simétrico Moderno
