
Un árbol puede estar vacío. Si no está vacío, es un conjunto de uno o más nodos, tal que existe
un nodo especial llamado raíz. Entonces un árbol no vacío tiene una raíz, y un conjunto de
árboles.

```java title:Arbol
public class Arbol {
	private int valor;
	private List<Arbol> hijos; // conjunto de árboles

	public Arbol(int valor) {
		this.valor = valor;
		hijos = new ArrayList<>();
	}
}
```

![[Arboles Y Subarboles.png]]

### Terminología

- **Hijo y Padre**:
	- Cada nodo, excepto la raíz, tiene un padre.
	- Cada nodo puede tener un número arbitrario de hijos (dependerá del tipo de árbol).
- **Hojas (o nodos externos)**:
	- Nodos sin hijos.
- **Vecino o hermano**:
	- Nodos con el mismo padre.
- **Camino**:
	- Conjunto de arcos desde un nodo padre a cualquier nodo de alguno de sus subárboles.
- **Ancestros y descendientes**:
	- Nodos que anteceden en un camino y nodos que suceden.
- **Longitud de un camino**:
	- Cantidad de arcos de un camino.
- **Profundidad de un nodo**:
	- Longitud del único camino desde la raíz a ese nodo.
- **Altura de un árbol (h)**:
	- La profundidad de la más lejana de sus hojas.

![[EjemploTerminologias.png]]


### Árboles de Expresiones

![[ArbolDeExpresion.png]]

**Hojas** → operandos (constantes o variables).
**Nodos internos** → operadores.

## Árboles Binarios

Es un árbol cuyos nodos no tienen más de 2 hijos.

![[ArbolBinario.png]]

- A1 y A2 son árboles binarios también
- La altura de un árbol binario promedio es considerablemente menor que la cantidad de nodos N (si fuera N a qué estructura se asemejaría? rta: Lista Vinculada) .

```java title:ArbolBinario
public class NodoBinario {
    private int valor;
    private NodoBinario hijoIzquierdo;
    private NodoBinario hijoDerecho;

    // Constructor
    public NodoBinario(int valor) {
        this.valor = valor;
        this.hijoIzquierdo = null;
        this.hijoDerecho = null;
    }

    // Getters y Setters
}

public class ArbolBinario {
    private NodoBinario raiz;

    // Constructor
    public ArbolBinario() {
        this.raiz = null;
    }
}
```

#### Recorridos Árbol Binario

- El recorrido más genérico de un árbol binario visita cada nodo tres veces (desde la izquierda, desde abajo y desde la derecha). Los puntos rojos indican estas visitas para el nodo D.
- Se denomina recorrido de Euler.

![[RecorridoEuler.png]]

- Usado para obtener los contenidos de los nodos en un orden determinado.
-  Son casos especiales del recorrido de Euler.
- **Recorrido Pre-orden**:
	- Imprimir el dato de la raíz.
	- Recursivamente obtener los datos del subárbol izquierdo.
	- Recursivamente obtener los datos del subárbol derecho.
- **Recorrido Post-orden**:
	- Recursivamente obtener los datos del subárbol izquierdo.
	- Recursivamente obtener los datos del subárbol derecho.
	- Imprimir el dato de la raíz.
- **Recorrido En-orden**:
	- Recursivamente obtener los datos del subárbol izquierdo.
	- Imprimir el dato de la raíz.
	- Recursivamente obtener los datos del subárbol derecho.

#### Estructuras Especiales de Árboles Binarios

![[EstructurasEspecialesDeARboles.png]]

- **Arboles Degenerados (enredaderas)** → nodos internos con sólo un hijo.
- **Balanceados** → las alturas de los dos subárboles de cualquier nodo difieren a lo sumo en 1.
- **Completos** → todos sus nodos tienen dos hijos, excepto los del último nivel que no tienen hijos. (llegan al mismo nivel)

#### Propiedades

- cantidad máxima de nodos externos = cantidad de nodos internos + 1
- cantidad máxima de nodos de **==x nivel <= 2^i==** donde i = altura/nivel
- cantidad máxima de nodos externos <= 2^altura
- log2(cantidad de nodos externos) <= altura <= cantidad de nodos internos.

![[EjemploArbolBinario.png]]

### Árbol Binario de Busqueda (ABB)

es un **árbol binario** que tiene un orden entre los nodos, utilizando el valor de la clave (la clave debe ser unica) de cada nodo como campo de ordenamiento (clave de bifurcación). Para cada nodo del ABB, **todas** las claves del **subárbol izquierdo son menores** que la de la raíz, y **todas** las del **derecho son mayores**.

![[ABB.png]]

![[ABB02.png]]

Si en nuestro dominio existieran claves repetidas, podemos asociar al nodo con dicha clave una lista de valores (llamada **lista de factoreo**). Por ej. Si la clave es la fecha de nacimiento de los alumnos de la facultad.
![[ListaFactoreo.png]]

#### Propiedades de los ABBs

- Un árbol binario completo de altura h >= 0 tiene **==N = 2^(h+1) – 1==** nodos.
- El máximo número N de nodos que puede tener un árbol binario de altura h es ==**N ≤ 2^(h+1) – 1**==.
- La altura mínima en un árbol binario de N nodos es ==**log2(𝑁 + 1) − 1 ≤ ℎ**==.