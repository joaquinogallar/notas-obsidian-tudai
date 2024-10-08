Es una relación para indicar que una clase usa a otra clase. ([[Diagrama de Clases]])

Una clase A depende de otra clase B en alguno de los siguientes
casos:
- Un objeto de la clase **A envía un mensaje a un objeto de la clase B**.
- Un objeto de la clase **A crea un objeto de la clase B**.
- Un objeto de la clase **A recibe un mensaje con un objeto de la clase B como parámetro**.
- Un objeto de la clase **A define un método con un objeto de la clase B como retorno**.

Usamos dependencias para modelar conexiones del tipo: **“usa”**.

Solo se muestra si **NO existe** otro tipo de relación entre las 2 clases.
![[EjemploDependencia.png]]
La **Dependencia** se indica como una línea punteada entre dos clases con una flecha simple que indica de que clase se depende.
Clase A - - - - -> Clase B