# Qué es?
- Son un tipo de metadatos y al igual que las clases podemos acceder a esos metadatos mediante [[Reflection]].
- Es opcional, si no se usa no va a romper nada.
- Se pueden aplicar donde sea, clases, atributos, métodos, interfaces, parámetros, etc.
- Agrega lógica en donde se aplique en tiempo de ejecución.

Hay 2 tipos de anotaciones:
- Anotaciones **Predefinidas**.
- Anotaciones **Personalizadas** o definidas por el usuario.

Dentro de las **Predefinidas** tenemos:

| Used on Annotations<br>(llamadas Meta-Annotations)                                                                                                                                           | Used on Java Code<br>Como clases, metodos, etc                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **@Target**<br>- Define donde se puede usar una annotation (constructor, atributos, parámetros, métodos, etc)                                                                                | **@Deprecated**                                                                                                                                                                               |
| **@Retention**<br>- Define como la annotation va a ser almacenada en java.                                                                                                                   | **@Override**                                                                                                                                                                                 |
| **@Documentation**<br>- Muestra las anotaciones cuando se genera la **java doc**, si no se agrega entonces la anotación no se va a mostrar.                                                  | **@SupressWarnings**                                                                                                                                                                          |
| **@Inherited**<br>- Indica que una anotación en una clase puede ser heredada por sus subclases. Solo aplica a anotaciones que se usen en clases (es decir, con `@Target(ElementType.TYPE)`). | **@FunciontallInterface**<br>- Indica que la interface en la que se encuentre solo puede tener un método abstracto, si se agregan mas da error en compilación. Se puede usar en los **Type**. |
| **@Repeatable**<br>- Permite usar mas de 1 vez la misma anotación.                                                                                                                           | **@SafeVarargs**<br>- Ignora las alertas de **Heap Pollution** unicamente en métodos static o final que tengan como parámetro varargs. A partir de Java9 también funciona en métodos private. |

**Type** = Class or interface or enum.

**Heap Pollution**: es cuando un objeto de un tipo tiene una referencia en la memoria Heap de otro tipo de objeto, por ejemplo un String que tiene referencia a un Integer, si este es el caso, entonces hay heap pollution.

![[HeapPollution]]


## Como crear anotaciones
```Java title:createAnnotations
@Target({ElementType.METHOD, ElementType.CONSTRUCTOR}) // define where it can be used
@Retention(RetentionPolicy.RUNTIME) // define how the annotation will be stored
public @interface MyAnnotationName {
	String text() default "hello";
}
```

**@Retention**:
- **RetentionPolicy.SOURCE**: La anotación solo existe en el código fuente y se descarta durante la compilación. No está presente en el archivo `.class`.
- **RetentionPolicy.CLASS**: La anotación se conserva en el archivo `.class`, pero no está disponible en tiempo de ejecución. Solo es útil durante el proceso de compilación o herramientas de análisis.
- **RetentionPolicy.RUNTIME**: La anotación se conserva en el archivo `.class` y está disponible en tiempo de ejecución mediante reflexión.

![[Anotaciones sobre Anotaciones]]