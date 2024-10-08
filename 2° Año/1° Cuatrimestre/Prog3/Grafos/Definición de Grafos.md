Un grafo (G) es una estructura no lineal de datos, se compone de vértices (V) y aristas (A) (o conexiones o arcos) entre esos vértices.

Formalmente definimos el grafo G=(V, A)

### Grafos Dirigidos (GD)
Si consideramos que las aristas tienen dirección (origen, destino), tendremos un Grafo Dirigido.
![[GD.png]]
### Grafos No Dirigidos (GND)
Si consideramos que las aristas **NO** tienen dirección, tendremos un Grafo No Dirigido.
![[GND.png]]
Donde la cantidad de aristas va a ser siempre par.
Es decir, **(x, y) = (y, x)

---

A su vez existen otro tipos de grafos como lo son los **grafos etiquetados** y los **grafos ponderados, rotulados o pesados**.

### Grafos Etiquetados
Es un grafo en el que en las aristas que conectan los diferentes vértices se presentan cadenas de texto.
![[GrafoEtiquetado.png]]

### Grafos Ponderados / Rotulados / Pesados
Un Grafo Ponderado es un Grafo Etiquetado pero en vez de tener cadenas de texto en sus aristas estas contienen valores numéricos (numero reales). 
![[GrafoPesado.png]]

---

### Relaciones de Adyacencia
![[Adyacencia.png]]

Los adyacentes del vértice A, serán todos aquellos vértices a los que puedo llegar partiendo desde A haciendo un solo paso (un solo arco).

En un grafo no dirigido la relación son simétricas.

### Grafo de vértice 
- El grado de un vértice en un GND es el numero de aristas que inciden sobre el **(vértices adyacentes)**.

![[VerticesGND.png]]

- El grado de un vértice en un GD es la suma de las aristas que salen **(grado de salida)** y entran **(grado de entrada)** de el.

![[VerticesGD.png]]

---
### Grafo Conectado o Conexo

![[GrafoConectado.png]]

---
### Ciclos

Un **ciclo** es un camino cerrado sin aristas repetidas (el **origen es igual a su** **destino**). Se aplica tanto para GD como GND.

![[Ciclos.png]]











¿Cómo implementamos un grafo? [[Implementación de Grafos]]


