# Algoritmo de Ordenamiento por Selección (Selection Sort)

## 📌 Descripción

El ordenamiento por selección es un algoritmo de tipo interno y directo que organiza un arreglo seleccionando, en cada pasada, el elemento más pequeño (o más grande) del conjunto restante y colocándolo en su posición correcta.

Funciona de manera similar a ordenar una fila de objetos buscando siempre el más pequeño y colocándolo al inicio, repitiendo el proceso hasta que todos estén ordenados.

___

## 🧩 Tipo de algoritmo

- Tipo: Ordenamiento interno
- Clasificación: Algoritmo directo
- Estabilidad: No estable (puede alterar el orden relativo de elementos iguales)
- In-place: Sí (no requiere memoria adicional significativa)

___

## ⚙️ Lógica del Algoritmo

1. Recorre el arreglo para encontrar el elemento mínimo.
2. Intercambia ese mínimo con el primer elemento del arreglo.
3. Repite el proceso, pero ahora desde la segunda posición.
4. Continua hasta que el arreglo esté completamente ordenado.

> [!NOTE]  
> A diferencia de otros algoritmos, el Selection Sort siempre realiza el mismo número de comparaciones, sin importar el orden inicial de los datos.

![ ](../assets/selection-sort-animation.gif)
___

## 📊 Complejidad (Big O)

| Caso | Tiempo |
|------|--------|
| Mejor caso (ya ordenado) | O(n²) |
| Peor caso (orden inverso) | O(n²) |
| Promedio | O(n²) |
| Espacio | O(1) (in-place) |

![ ](../assets/On2.png)

___

## 🧪 Casos donde es eficiente

- Arreglos pequeños donde la simplicidad es más importante que la eficiencia.
- Situaciones donde el costo de intercambiar elementos es bajo, ya que hace relativamente pocos intercambios (n - 1 en total).
- Escenarios educativos para explicar el concepto de selección y comparación.

___

## 💻 Código en Java

``` java
public class SelectionSort {
    public static void selectionSort(int[] arr) {
        int n = arr.length;

        // Recorre todo el arreglo
        for (int i = 0; i < n - 1; i++) {
            // Encuentra el índice del mínimo en el subarreglo no ordenado
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }

            // Intercambia el mínimo encontrado con el primer elemento no ordenado
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }

    public static void main(String[] args) {
        int[] data = {9, 5, 1, 4, 3};
        System.out.println("Array original:");
        printArray(data);

        selectionSort(data);

        System.out.println("Array ordenado:");
        printArray(data);
    }

    public static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}
```

___

## 🖥️ Salida esperada en consola

``` shell
Array original: 9 5 1 4 3 
Array ordenado: 1 3 4 5 9 
```

## 🔄 Iteraciones del Selection Sort

### 🔹 Estado inicial

```shell
  [9, 5, 1, 4, 3]
```

### 🔁 Iteración 1 (i = 0)

- Busca el mínimo → 1.
- Intercambia 9 con 1.

```shell
  [1, 5, 9, 4, 3]
```

### 🔁 Iteración 2 (i = 1)

- Busca el mínimo en el resto → 3.
- Intercambia 5 con 3.

```shell
  [1, 3, 9, 4, 5]
```

### 🔁 Iteración 3 (i = 2)

- Busca el mínimo en el resto → 4.
- Intercambia 9 con 4.

```shell
  [1, 3, 4, 9, 5]
```

### 🔁 Iteración 4 (i = 3)

- Busca el mínimo en el resto → 5.
- Intercambia 9 con 5.

```shell
  [1, 3, 4, 5, 9]
```

### ✅ Resultado final

```shell
  [1, 3, 4, 5, 9]
```
