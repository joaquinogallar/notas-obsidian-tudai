**Ordenamiento Recursivo**

| Algoritmo       | Mejor caso | Promedio | Peor caso |
| --------------- | ---------- | -------- | --------- |
| BubbleSort      | O(n^2)     | O(n^2)   | O(n^2)    |
| BubbleSortAdapt | O(n)       | O(n^2)   | O(n^2)    |

Consiste en seleccionar uno de los elementos del array como valor **pivote** alrededor del cual el resto de los elementos serán reordenados. Todo lo que sea menor que el pivote es movido a la izquierda del pivote (a la partición izquierda). De forma similar todo lo que sea mayor que el pivote es movido a la partición derecha. **No necesita de una memoria auxiliar**.

**Implementaciones en Java**:
```java title:QuickSort
public class QuickSort {

    // Método para realizar la partición del array
    private int partition(int arr[], int low, int high) {
        int pivot = arr[high]; 
        int i = (low - 1); // índice del elemento más pequeño
        for (int j = low; j < high; j++) {
            // Si el elemento actual es menor o igual al pivote
            if (arr[j] <= pivot) {
                i++;

                // intercambia arr[i] y arr[j]
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        // intercambia arr[i+1] y arr[high] (o el pivote)
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;

        return i + 1;
    }

    // Método principal que implementa QuickSort
    // arr[] --> Array a ordenar,
    // low --> Índice inicial,
    // high --> Índice final
    public void sort(int arr[], int low, int high) {
        if (low < high) {
            // pi es el índice de partición, arr[pi] está ahora en el lugar correcto
            int pi = partition(arr, low, high);

            // Ordenar los elementos de manera recursiva
            sort(arr, low, pi - 1); // Antes de pi
            sort(arr, pi + 1, high); // Después de pi
        }
    }

    // Método para imprimir el array
    static void printArray(int arr[]) {
        int n = arr.length;
        for (int i = 0; i < n; ++i) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    // Método principal para probar el algoritmo
    public static void main(String args[]) {
        int arr[] = {10, 7, 8, 9, 1, 5};
        int n = arr.length;

        QuickSort ob = new QuickSort();
        ob.sort(arr, 0, n - 1);

        System.out.println("Array ordenado:");
        printArray(arr);
    }
}

```