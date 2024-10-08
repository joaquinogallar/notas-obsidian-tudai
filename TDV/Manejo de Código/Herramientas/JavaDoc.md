```java
/** Este puede ser el encabezado de una clase Java
* Dentro de los comentarios en Java pueden incluirse enlaces a otra
* clase o bien una dirección Web utilizando el Tag {@link URL}.
* <p>
* En general, se puede describir con gran precisión y en lenguaje natural
* el contenido y comportamiento del código fuente
* Por ejemplo, a los métodos se les describen uno a uno sus parámetros
* Utilizando el tag param
*
* @param param1 donde Param1 sería el nombre del primer parámetro y *
* y este texto su descripción
* @param param2 donde Param2 sería el nombre del segundo parámetro
* y este texto su descripción
* @return es utilizado para describir el dato devuelto por el método
* @see Referencia a otra clase o documento
*/
```

# Orden de los Tags de Javadoc

Al documentar código en Java utilizando Javadoc, es importante seguir un orden establecido para los diferentes tags. A continuación, se presenta el orden recomendado:

1. **@author**  
    _Uso_: Clases e interfaces únicamente.  
    _Descripción_: Indica el autor o autores del código. Este tag es **requerido**.
    
2. **@version**  
    _Uso_: Clases e interfaces únicamente.  
    _Descripción_: Especifica la versión del código. Este tag es **requerido**.
    
3. **@param**  
    _Uso_: Métodos y constructores únicamente.  
    _Descripción_: Describe los parámetros que recibe un método o constructor. Cada parámetro debe ser documentado con este tag.
    
4. **@return**  
    _Uso_: Métodos únicamente.  
    _Descripción_: Indica el valor que devuelve un método, si es aplicable (solo para métodos que no sean `void`).
    
5. **@exception**  
    _Uso_: Métodos únicamente.  
    _Descripción_: Documenta las excepciones que pueden lanzarse. El tag **@throws** es un sinónimo de **@exception** y fue agregado en Javadoc 1.2.
    
6. **@see**  
    _Uso_: Clases, interfaces, métodos, constructores y campos.  
    _Descripción_: Proporciona referencias adicionales a clases, métodos o bibliografía que pueden ser de ayuda.
    
7. **@since**  
    _Uso_: Clases, interfaces, métodos, constructores y campos.  
    _Descripción_: Indica desde qué versión de la API o del proyecto está disponible una clase, método o constructor.
    
8. **@serial**, **@serialField**, **@serialData**  
    _Uso_: Campos o métodos relacionados con la serialización.  
    _Descripción_: Describe aspectos de la serialización de un campo o el formato de los datos serializados.
    
9. **@deprecated**  
    _Uso_: Clases, métodos, constructores, campos.  
    _Descripción_: Marca un elemento como obsoleto o no recomendado para su uso, especificando si existe una alternativa.

