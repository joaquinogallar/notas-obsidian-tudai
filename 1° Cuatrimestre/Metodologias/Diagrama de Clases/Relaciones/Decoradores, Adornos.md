Dentro de las **Asociaciones** y en general cualquier relación **estructural** existen los **Decoradores o Adornos**, estos agregan mas información a la relación.

Hay varios tipos:
**Nombre de relación y dirección** (o en su defecto roles). 
Para esta existen 2 formas, la primera describe la naturaleza de la relación:
![[DecoradoresEj01.png]]

y la segunda, donde se pone Rol que cumple una clase en la relación (La misma clase puede jugar el mismo o diferentes roles en otras asociaciones, por ejemplo empleado y jefe):
![[DecoradoresEj02.png]]

Otro adorno es la **Multiplicidad**, que indica cuántos elementos de una instancia se relacionan con otra, Por ejemplo:
- 0..1: entre 0 y 1 objetos
- 3..4: entre 3 y 4 objetos
- 6..*: 6 o mas objetos
- 0..1, 3..4, 6..*: cualquier numero de objetos que no sea 2 o 5
![[DecoradoresEj03.png]]

Una persona trabaja en una o muchas **empresas**, una empresa tiene muchos empleados.

Otro adorno es la **Navegabilidad** indica en que dirección se pueden enviar los mensajes. Este permite indicar restricciones en el diseño detallado.
![[DecoradoresEj04.png]]

Una relación **estructural** debe tener debe tener mínimamente Nombre de relación y dirección y Multiplicidad.
