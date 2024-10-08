**Ordenamiento Iterativo**

| Algoritmo       | Mejor caso | Promedio | Peor caso |
| --------------- | ---------- | -------- | --------- |
| BubbleSort      | O(n^2)     | O(n^2)   | O(n^2)    |
| BubbleSortAdapt | O(n)       | O(n^2)   | O(n^2)    

Consiste en comparar pares de elementos adyacentes en un array y si están desordenados intercambiarlos hasta que estén todos ordenados. El elemento mayor sube como una burbuja hacia la posición más alta.

![[BubbleSort.png]]

**Implementaciones en Java**:
```java title:BubbleSort
// algoritmo de burbujeo clásico
public static void burbujeo(int[] A) {
	int i, j, aux;
	for (i=0; i < A.length - 1; i++) {
		for (j=0; j < A.length – i – 1 ; j++) {
			if (A[ j ] > A[ j+1 ]) {
			aux = A[ j+1 ];
			A[ j+1 ] = A[ j ];
			A[ j ] = aux;
			}	
		}
	}
}
```

```java title:BubbleSortAdapt
// algoritmo de burbujeo mejorado para algunos casos
// ej: [8, 5, 7, 9, 11, 15, 25, 32, 41, 50]
public void bubbleSortAdapt(int[] arr) {
	boolean swapped = true;
	int j = 0;
	int tmp;
	while (swapped) {
		swapped = false;
		j++;
		for (int i=0; i<arr.length - j; i++) {
				if (arr[i] > arr[i + 1]) {
				tmp = arr[i];
				arr[i] = arr[i + 1];
				arr[i + 1] = tmp;
				swapped = true;
			}
		}
	}
}
```