Es un tipo especial de relación de **[[Agregación]]**, por ende, también es un tipo de **[[Asociación]]**. Es decir, puede incluir [[Decoradores, Adornos]] y es **estructural**. ([[Diagrama de Clases]])

También representa el **“todo”** y la/s **“partes”** pero el tiempo de vida
de las partes esta ligada al del **todo**.

Lo utilizamos en base al contexto que nos de la consigna.

Las partes se pueden crear después del todo pero cuando se destruye el todo también se destruyen las partes.
![[EjemploComposición.png]]
La **Composición** se indica como una línea entre dos clases con un rombo lleno sobre la clase que representa el “todo”.
Todo <|>----- Parte