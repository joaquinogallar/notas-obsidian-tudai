# Qué es?
Se usa para examinar las clases, métodos, archivos, interfaces en tiempo de ejecución y también brinda la posibilidad de cambiar los tipos de los atributos.
Por ejemplo nos permite:
- Los métodos o atributos que están presentes en la case.
- El tipo que retorna un método.
- Cual es el Modifier de la clase.
- Que interfaces implementa la clase.
- Cambiar los valores public o private de los atributos.

# Cómo se usa?
Se necesita crear una clase de tipo **"Class"**.

La instancia de una clase de tipo Class es un objeto que representa una clase durante el tiempo de ejecución. Por cada clase que se tenga también se tiene un objeto de tipo Class, es decir, si tengo 10 clases tengo 10 objetos de tipo **Class**.

Este objeto **Class** contiene información particular en metadatos sobre la clase, como métodos, atributos, constructores, etc. 

## Quién crea estas clases?
**JVM** es el encargado de crear los objetos de tipo Class cada vez que una clase es cargada en tiempo de ejecución.

## Como obtenerlas
Hay 3 formas:

1. Usando el método **forName()**:
![[obtenerClass01.png]]

2. Usando **.class**:
![[obtenerClass02.png]]

3. Usando el método **getClass()**:
![[obtenerClass03.png]]

Tener en cuenta que nosotros no creamos este objeto **Class**, de eso se encarga **JVM**.

Ya teniendo el objeto Class de nuestra clase en cuestión podemos acceder a sus valores a través de métodos get. Estos métodos se encuentran en la librería 'java.lang.reflect'. 
![[metodosClass.png]]

Los métodos se pueden ejecutar mediante **Reflection**.
```Java title:testClass
public class Eagle {
	public String breed;
	private boolean canSwing;

	// Constructor
	Eagle() {
	}

	public void fly(int intParam, boolean boolParam, String strParam) {
		System.out.println("Fly intParam: " + intParam + " boolParam: " + boolParam + " strParam: " + strParam)
	}
}
```

```Java title:executeMethods
public class Main {
	public static void main(String args[]) {
		Class eagleClass = Class.forName("Eagle");
		// Ejecuta el constructor de la clase
		Object eagleObject = eagleClass.newInstance();

		// Busca el método que cumpla con los parametros dados
		Method flyMethod = eagleClass.getMethod("fly", int.class, boolean.class, String.class);
		flyMethod.invoke(eagleObject, 1, true, "hello");
	}
}
```

También podemos acceder a los Fields (fields = atributos) ya sean privados o públicos de la siguiente forma.

**Para atributos públicos**
```Java title:publicFields
public class Main {
	public static void main(String args[]) throws NoSuchFieldException, IllegalAccessException {
	
		Class eagleClass = Eagle.class;

		Eagle eagleObj = new Eagle();
		// Cuando se agrega Declared al método get se obtienen los atributos privados y publicos, sin incluir a los atributos de las clases de las que hereda (padres)
		Field field = eagleClass.getDeclaredField("breed");
		field.set(eagleObj, "eagleBrownBreed");
		System.out.println(eagleObj.breed);
	
	}
}
```

Para los atributos privados se podría pensar que se modifican de la misma forma, pero esto no es asi, ya que los atributos privados solo pueden ser accedidos por la clase en si. En este caso nos daría una **IllegalAccessException**.

**Para atributos privados**
```Java title:privateFields
public class Main {
	public static void main(String args[]) throws NoSuchFieldException, IllegalAccessException {
		
		Class eagleClass = Eagle.class;

		Eagle eagleObj = new Eagle();
		Field field = eagleClass.getDeclaredField("canSwim");
		// Da derecho a la clase (main en este caso) de cambiar los valores del atributo privado
		field.setAccessible(true);
		field.set(eagleObj, true);
	}
}
```

## Reflection of Constructor (pregunta de entrevista)

Muy importante por Singleton. Ya que esta **Reflection** rompe **Singleton**.

```Java title:eagle
public class Eagle {
	// Constructor privado (Singleton)
	private Eagle() {
	}

	public void fly() {
		// Hace algo...
	}
}
```

```Java title:breakSingleton
public class main {
	public static void main(String args[]) throws InvocationTargetException, InstantiationException, IllegalAccessException {

		Class eagleClass = Eagle.class;

		Constructor[] eagleConstructorList = eagleClass.getDeclaredConstructors();
		for(Constructor c : eagleConstructorList) {
			System.out.println("Modifier: " + Modifier.toString(c.getModifiers()));

			// Aca rompemos Singleton
			eagleConstructor.setAccesible(true);
			Eagle eagleObject = (Eagle) eagleConstructor.newInstance();
			eagleObject.fly();
		}
	}
}
```


Por estos casos no es recomendable usar **Reflection**, ya que rompe el encapsulamiento. Además de esto es lento y agrega complejidad. Evitar su uso de no ser necesario.