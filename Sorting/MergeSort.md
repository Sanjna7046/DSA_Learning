# Merge Sort

## Definition

Merge Sort is a **Divide and Conquer** algorithm that recursively divides the array into two halves, sorts each half, and then merges them into a single sorted array.

## Algorithm

1. Divide the array into two halves.
2. Recursively sort each half.
3. Merge the two sorted halves.
4. Repeat until the entire array is sorted.

<img width="460" height="402" alt="image" src="https://github.com/user-attachments/assets/ffa22c93-6352-486f-a470-eb6303c305cd" />

## Complexity

| Case | Time |
|------|------|
| Best | O(n log n) |
| Average | O(n log n) |
| Worst | O(n log n) |

**Space:** O(n)

## Properties

- In-place ❌
- Stable ✅

## Pros

- Guaranteed O(n log n) time.
- Stable sorting algorithm.
- Efficient for large datasets.

## Cons

- Requires O(n) extra space.
- More complex than simple sorting algorithms.
```cpp
void merge(int a[], int low, int mid, int high) {
    int i = low, j = mid + 1, k = 0;
    int temp[100];

    while (i <= mid && j <= high) {
        if (a[i] <= a[j]) {
            temp[k++] = a[i++];
        } else {
            temp[k++] = a[j++];
        }
    }

    while (i <= mid) {
        temp[k++] = a[i++];
    }

    while (j <= high) {
        temp[k++] = a[j++];
    }

    for (i = low, k = 0; i <= high; i++, k++) {
        a[i] = temp[k];
    }
}
void mergeSort(int a[], int low, int high) {
    if (low < high) {
        int mid = (low + high) / 2;

        mergeSort(a, low, mid);
        mergeSort(a, mid + 1, high);
        merge(a, low, mid, high);
    }
}
```
