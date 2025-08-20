# Algoritmo de Ordenamiento por Intercambio (Bubble Sort)

## 📌 Descripción

El ordenamiento por intercambio es un algoritmo de tipo interno y directo, muy utilizado en el ámbito educativo por su simplicidad.

Su funcionamiento se basa en recorrer repetidamente el arreglo, comparando elementos adyacentes y intercambiándolos si están en el orden incorrecto. Con cada pasada, el elemento más grande “sube” a su posición final, de forma similar a cómo una burbuja asciende en el agua.

___

## 🧩 Tipo de algoritmo

- Tipo: Ordenamiento interno
- Clasificación: Algoritmo directo
- Estabilidad: Estable (mantiene el orden de elementos iguales)
- In-place: Sí (no requiere memoria adicional significativa)

___

## ⚙️ Lógica del Algoritmo

1. Recorre el arreglo comparando cada par de elementos adyacentes.
2. Si el elemento actual es mayor que el siguiente, se intercambian.
3. Al final de cada pasada, el elemento más grande queda en la última posición.
4. Repite el proceso hasta que no se realicen más intercambios (el arreglo ya está ordenado).

> [!NOTE]  
> Aunque es muy intuitivo, no es eficiente para grandes volúmenes de datos en comparación con otros algoritmos.

![ ](../assets/bubble-sort.gif)

___

## 📊 Complejidad (Big O)

| Caso | Tiempo |
|------|--------|
| Mejor caso (ya ordenado) | O(n) (con optimización de parada) |
| Peor caso (orden inverso) | O(n²) |
| Promedio | O(n²) |
| Espacio | O(1) (in-place) |

![ ](../assets/On2.png)
___

## 🧪 Casos donde es eficiente

- Cuando se requiere un algoritmo muy simple y fácil de implementar.
- Para arreglos pequeños o casi ordenados.
- Útil en enseñanza, ya que es ideal para comprender la idea de comparación e intercambio.

___

## 💻 Código en Java

```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped;

        // Recorre el arreglo varias veces
        for (int i = 0; i < n - 1; i++) {
            swapped = false;

            // Últimos i elementos ya están en su lugar
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Intercambia arr[j] y arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }

            // Si en una pasada no hubo intercambios, el arreglo ya está ordenado
            if (!swapped) break;
        }
    }

    public static void main(String[] args) {
        int[] data = {9, 5, 1, 4, 3};
        System.out.println("Array original:");
        printArray(data);

        bubbleSort(data);

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

```shell
Array original: 9 5 1 4 3 
Array ordenado: 1 3 4 5 9 
```

___

## 🔄 Iteraciones del Bubble Sort

### 🔹 Estado inicial

```shell
  [9, 5, 1, 4, 3]
```

### 🔁 Iteración 1

- Compara 9 y 5 → intercambia.
- Compara 9 y 1 → intercambia.
- Compara 9 y 4 → intercambia.
- Compara 9 y 3 → intercambia.

```shell
  [5, 1, 4, 3, 9]
```

### 🔁 Iteración 2

- Compara 5 y 1 → intercambia.
- Compara 5 y 4 → intercambia.
- Compara 5 y 3 → intercambia.

```shell
  [1, 4, 3, 5, 9]
```

### 🔁 Iteración 3

- Compara 1 y 4 → no intercambia.
- Compara 4 y 3 → intercambia.
- Compara 4 y 5 → no intercambia.

```shell
  [1, 3, 4, 5, 9]
```

### 🔁 Iteración 4

- Compara 1 y 3 → no intercambia.
- Compara 3 y 4 → no intercambia.
- No hubo intercambios, el algoritmo termina.

### ✅ Resultado final

```shell
  [1, 3, 4, 5, 9]
```
